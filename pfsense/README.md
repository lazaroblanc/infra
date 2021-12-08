# pfSense

## Installation
During installation it might be necessary to temporarily disable the firewall to access the web login via the WAN address (if no VPN has been setup yet for example to access it via the LAN address).

Disable the firewall

```pfctl -d```

Reenable via GUI or via

```pfctl -e```

If no or wrong hostname is set or while accessing via IP address you might need to temporarily disable HTTP_REFERER enforcement check.
Reenable via GUI: `System / Advanced / Admin Access / webConfigurator / Browser HTTP_REFERER enforcement`

```pfSsh.php playback disablereferercheck```


## Config backup
pfSense Config Backup file (encrypted)
Encryption password can be found in KeePass ("pfSense Config Backup Encryption Password")