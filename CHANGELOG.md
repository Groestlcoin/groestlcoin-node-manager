# Groestlcoin Node Manager Changelog

## 1.1.0 - 2020-12-19

The release brings some new features and a few bug fixes.

- [**New**] You can click on countries and clients in the main page to see a filtered peer list
- [**New**] There is now a mobile menu
- [**Improved**] Hover over the traffic of a peer to see more detailed traffic information
- [**Improved**] Rules ignore by default all whitelisted peers
- [**Fixed**] Geo settings GUI
- [**Fixed**] Geo data file cleanup
- [**Fixed**] Peer list with deactivated geo data

## 1.0.0 - 2020-12-13

Three years after the first release, 1.0.0 is finally out :partying_face:

- [**New**] On the Main (Global Peer Distribution next to the help icon) and the Peers page (next to the help icon) is a small refresh icon displayed if Geo API calls were made
- [**Improved**] Link to block explorer that displays forks
- [**Improved**] Updated hoster detection list
- [**Improved**] Dynamic services detection
- [**Fixed**] Compatibility with Groestlcoin Core 2.20.1
- [**Fixed**] Country flag icons
- [**Fixed**] Compatibility with IP-API.com limits
- [**Fixed**] Peer geo data
- [**Fixed**] Forks counter
- [**Fixed**] PHP Error namespace
- [**Fixed**] Wallet page

## 0.6.0 Beta - 2020-05-12

This will delete your `src\Config.php`. Copy the `src\Config.php.example`, remove `.example` and change your settings. Starting this release, `git pull` will not mess with your `src\Config.php` anymore.

- [**New**] Config.php.example to avoid git conflicts, git ignores Config.php
- [**New**] Proxy icon on main page if proxy is set
- [**Improved**] Modern favicon
- [**Improved**] More sensible units on main and blocks page
- [**Improved**] Show full peer client and isp on hover
- [**Improved**] Use wallet rpc calls only on wallet page
- [**Improved**] Wallet, peer and block page layout
- [**Fixed**] Ban information if zero bans
- [**Fixed**] Block fee calculation (Thanks to [TotalBuzzKit](https://github.com/drkskwlkr))

## 0.5.0 Beta - 2020-04-29

Please delete `data/geodatapeers.inc` to avoid any peer information issues

- [**New**] Display node uptime on start page
- [**New**] You can now execute your rules via command line. `php /path/to/your/index.php yourtoken` (see rules page for more information)
- [**Improved**] Better protection against XSS and other attacks
- [**Improved**] Layout improvements
- [**Fixed**] Block voting detection
- [**Fixed**] Execute rules
- [**Fixed**] Session error
- [**Fixed**] Saving geodata fpr new peers
- [**Fixed**] Various asset imports
- [**Fixed**] Removed unused .js files
- [**Fixed**] Removed unused variables

## 0.4.1 Beta - 2020-04-27

### Improved

- Peer page styling
- Hoster list
- Code cleanup

### Fixed

- Wallet page information
- External links
- GeoTracing GUI setting
- Soft fork dection (for >0.19.0.1)
- Network detection
- Various client stats

## 0.4.0 Beta - 2020-01-07

### New

- Display blockchain size on main page

### Improved

- New icons for some information
- Add tooltips for peer icons
- Simplify wallet code
- Update hoster list

## 0.3.0 Beta - 2019-06-16

### New

- AsicBoost dectection for blocks
- Icon for monitoring/spying nodes (like bitnodes)

### Improved

- Remove duplicate files
- Simplify code

### Fixed

- Ipv6 detection
- Multiple IPs

## 0.2.0 Beta - 2018-07-12

### New

- Wallet Overview

## 0.1.0 Beta - 2017-08-03

### First Release
