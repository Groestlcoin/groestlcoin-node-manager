# Groestlcoin Node Manager

Groestlcoin Node Manager (GNM) is a lightweight dashboard and control system for your Groestlcoin node. Check out [ElextrumX Dashboard](https://github.com/Groestlcoin/electrumx-dashboard) if you run an Electrumx Server.

## Features

- Extensive dashboard with general information about the node, connected peers and the blockchain
- Create rules to manage your peers
  - Ban, disconnect or log peers that waste resources or are slow
  - Set global events that trigger the execution of rules, run rules manually or set up a cron job
- Overview of all connected peers including country, ISP, client, traffic usage, supported services...
  - Ban or disconnect peers
  - Manage a list of web hoster to detect if peer is hosted or private
- Overview of all banned peers
  - Unban specific peers
  - Export/Import your ban list
  - Generate iptables rules (reject banned peers at OS level)
- Overview of the last received blocks
- Overview of the last received forks (orphaned blocks)
- Overview of the memory pool and containing transactions
- Overview of the wallet (no functionality, information only)

## Requirements

- Groestlcoin Core 2.19.1
- Apache Web Server (sudo apt install apache2)
- PHP 7.2 (sudo apt install php libapache2-mod-php)
- cURL extension for Apache (sudo apt-get install php-curl)
- Docker (Alternative to Web Server and PHP)

Restart apache after packages are installed: `sudo systemctl restart apache2`

## Installation

1. [Download](https://github.com/Groestlcoin/groestlcoin-node-manager/releases) Groestlcoin Node Manager or clone this repository.
2. Make sure `groestlcoind` is running. If you use `groestlcoin-qt` make sure `server=1` is set in the `groestlcoin.conf` file. Optional: `txindex=1` is required in your `groestlcoin.conf` for the Blocks page. Start `groestlcoind` once with the `-reindex` param (this might take a while).
3. Copy `src/Config.sample.php` and remove `.sample`. Open `src/Config.php` and enter your Groestlcoin Core RPC credentials and set the GNM password.

If you want to use Docker you can skip to the Docker section.

4. Make sure the GNM folder is in your web servers folder (e.g. `/var/www/html/`). If the server is publicly accessible, I recommend renaming the GNM folder to something unique. Although GNM is password protected and access can be limited to a specific IP, there can be security flaws and bugs.
5. Open the URL to the folder in your browser and login with the password chosen in `src/Config.php`.
6. Optional: Read the Security section for.

### Docker
Run can either run `docker-compose up -d` or `docker run -d -p 8000:80 -n gnm -v ${PWD}:/var/www/html php:7.4-apache` in the GNM folder. GNM should now be accessible under http://localhost:8000. You can change the port in `docker-compose.yml` or the terminal command (`8000:80`). The GNM folder is mounted as volume in Docker. So can edit your config and update GNM at any time. Don't forget to set the right RPC IP in `src/Config.php`.

## Security

- All pages and control functionality are only accessible for logged-in users. The only exception is if you use the Rules cron job functionality. But a password based token is required and the functionality is only able to apply rules.
- Access to GNM is by default limited to localhost. This can be expanded to a specific IP or disabled. If disabled, make sure to protect the GNM folder (.htaccess or rename it to something unique that an attacker will not guess). An attacker could "guess" your password, since there is no build-in brute force protection.
- The `data` folder contains your rules, rule logs and geo information about your peers. Make sure to protect (e.g. `chmod -R 770 data`) this sensitive information if your web server is publicly accessible. The previously mentioned IP protection doesn't work here. If you use `Apache` you are fine, since the folder is protected with `.htaccess` (make sure `AllowOverride All` is set in your Apache config file).

## Roadmap

- [ ] Improve project structure
- [ ] Improve OOP
- [ ] Improve error handling
- [ ] Import rules functionality
- [ ] More help icons
- [ ] Use popover for help
- [ ] Display expanded peer/block info (popup)
- [ ] More customization settings
- [ ] Highlight suspicious peers
