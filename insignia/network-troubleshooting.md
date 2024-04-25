# Network Troubleshooting for Insignia
If the MS dashboard connection test shows 4 green lights and you still cannot connect to Xbox Live inside a game, try using the Setup Assistant to clear tickets. If that does not work, you likely have a bad game rip.

Follow these troubleshooting steps if you are having connection issues to Insignia and you use any homebrew dashboard:

1. Go to your MS Dash or XBMC network settings, take a picture of, or write down your current network settings.
2. Go into UnleashX or XBMC and change your network setting from DHCP to Static, save, then restart the dashboard.
3. Back in UnleashX or XBMC network settings, use your documented network settings to fill out IP address, Subnet Mask, and Gateway.
4. For DNS settings, use 46.101.64.175 for Primary and `8.8.8.8` or `1.1.1.1` or any other valid DNS server for Secondary, save then restart UnleashX or XBMC.
5. Go to your MS dash to verify those settings match your documented settings and the DNS servers from step 4.
6. If the settings in your MS dash do not match the settings you put into UnleashX, change IP Addresses and DNS Server configuration to manual and use the addresses you recorded in step 1, and the DNS servers from step 4.
7. Do a connection test to verify your settings, then enjoy Insignia!
8. If you are still unable to connect to Insignia in games after your network settings are valid, try using the Insignia Setup Assistant and use the Clear Ticket Cache option.
9. If you are still unable to connect to Insignia in games after using the Setup Assistant, try an Account Recovery from the Xbox Live menu. Make sure to use the unique and fake credit card number from your profile under Recovery Info on [http://insignia.live/](http://insignia.live/)

Backup DNS in case the main DNS server is down: `129.80.250.17`
