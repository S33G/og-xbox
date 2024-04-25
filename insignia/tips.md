# Insignia Troubleshooting

- DO NOT CHANGE YOUR HDD KEY AFTER REGISTERING WITH THE INSIGNIA SETUP ASSISTANT!
- You must use the Register Xbox command in the Insignia setup assistant on your Xbox or in your Xemu emulated Xbox before being able to connect to Insignia.
- Do not use UnleashX for gathering network info. UnleashX, Avalaunch, and other homebrew dashboards are known to display incorrect IP info. XBMC will likely display the correct info.
- If the gateway UnleashX is displaying does not work and your computer is on the same network, use the default gateway from your computer. It should be the internal IP address of your modem/router.
- Static leases / IP reservations are not the problem and will not fix problematic dashboards from changing your network settings.
- XBMC4Xbox, older versions of XBMC Emustation, and XBMC4Gamers only support 1 Static DNS server. Once all other network-enabled dashboards are set to Static and your MS Dashboard is set to Manual DNS, you can change the network mode on these dashboards back to Default (Dashboard). You will need to correct the network settings again every time another dashboard/app changes the network settings.
- If the error "Xbox live is not responding. Please try again later." appears when you attempt to register; this is often caused by packet loss. Try changing your network cable, set the MTU on your internet connection below `1499`, and just keep trying to register. If your country option does not work, try another nearby country.
- Setup Assistant Discs like HeXEn, Rocky5's extra disc as well as apps, like NKpatcher - Settings are custom homebrew dashboards and will also change your network settings. After using them, you will need to manually change your DNS servers again.
- If you are able to sign into Insignia but are not able to join games, forward UDP Port 3074 in your router to your original Xbox console.
- If you are using EvolutionX and cannot connect, disable TSR Xbox `Admin\System\Settings\Misc` section.
