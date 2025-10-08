# Xbox Custom Dashboards Guide

## Introduction

Custom dashboards replace or supplement the stock Microsoft Dashboard on a modified Xbox. They provide enhanced functionality, including file management, FTP servers, media playback, and homebrew application launching.

## Microsoft Dashboard (MS Dash)

The original dashboard that comes with every Xbox.

### Features
- Game disc launching
- Music ripping and playback
- Settings management
- Xbox Live (now defunct, use Insignia)
- Memory management
- Audio/video settings

### Limitations
- No homebrew support
- Limited media format support
- No FTP capability
- No file management
- Region locked

### Version History
- **Dashboard 4920:** Original release version
- **Dashboard 5530:** Auto-updater patch
- **Dashboard 5659:** Security updates
- **Dashboard 5838:** Final official release

### Preservation
Keep MS Dashboard accessible:
- Some games require it
- System updates need it
- Recovery purposes
- Xbox Live/Insignia compatibility

## UnleashX

One of the most popular lightweight custom dashboards.

### Features
- **File Manager:** Full filesystem navigation
- **FTP Server:** Built-in network file transfer
- **Game Launcher:** Automatic game detection
- **Skinnable Interface:** Customizable appearance
- **Low Memory Footprint:** Fast and responsive
- **Settings Manager:** Network, video, audio config
- **Backup Tools:** EEPROM and save management

### Configuration
Located in `E:\Dashboard\UnleashX\config.xml`

**Key settings:**
```xml
<Network>
    <SetupNetwork>
        <Type>Static</Type>
        <Ip>192.168.1.100</Ip>
        <Subnetmask>255.255.255.0</Subnetmask>
        <Defaultgateway>192.168.1.1</Defaultgateway>
        <DNS1>192.168.1.1</DNS1>
    </SetupNetwork>
    <FTP>
        <Enable>Yes</Enable>
        <User>xbox</User>
        <Password>xbox</Password>
    </FTP>
</Network>
```

### Skins
Popular UnleashX skins:
- **BlueX:** Clean, modern look
- **Avalaunch Clone:** Mimics Avalaunch appearance
- **Minimal:** Simple, fast-loading
- **Xbox 360 Style:** Modern Xbox aesthetic

**Skin location:** `E:\Dashboard\UnleashX\Skins\`

### Advantages
- Very stable
- Fast loading
- Low resource usage
- Easy configuration
- Active community support

### Disadvantages
- Basic media playback
- Limited codec support
- No advanced features
- Development discontinued

## XBMC (Xbox Media Center)

The most feature-rich media center dashboard for Xbox.

### Variants

**XBMC4Xbox:**
- Last official XBMC port for Xbox
- Version 3.5.3 final
- Basic media center features
- Emulator support

**XBMC4Gamers:**
- Community-maintained fork
- Enhanced game launching
- Artwork scraping
- Synopsis database
- Active development
- Recommended version

**XBMC Emustation:**
- Emulation-focused build
- RetroArch integration
- Kodi-style interface
- Game artwork

### Features

**Media Playback:**
- Video: AVI, MP4, MKV, XviD, DivX
- Audio: MP3, AAC, FLAC, OGG, WMA
- Images: JPG, PNG, BMP, GIF
- Subtitles: SRT, SUB, SSA

**Network Capabilities:**
- SMB/CIFS file sharing
- FTP server
- HTTP streaming
- UPnP/DLNA client
- RSS feeds
- Weather information

**Organization:**
- Media library management
- Metadata scraping
- Cover art download
- Movie/TV show organization
- Music library with tags

**Gaming Features (XBMC4Gamers):**
- Automatic game scanning
- Cover art scraping
- Synopsis database
- Trainer support
- Save game management
- Multiple launcher modes

### Configuration

**Main config:** `E:\XBMC\system\UserData\guisettings.xml`

**Network setup:**
1. Settings → Network
2. Configure network type (Static/DHCP)
3. Enable FTP server
4. Set FTP credentials

**Media sources:**
1. Videos/Music/Pictures → Add Source
2. Browse to folder or network location
3. Set content type
4. Configure scraper

### Skins

Popular XBMC skins:
- **PM3.HD (Default):** Classic XBMC look
- **Confluence:** Clean, modern
- **Alaska:** Minimalist design
- **MediaStream:** Media-focused
- **Night:** Dark theme

**Skin location:** `E:\XBMC\skin\`

### Add-ons

**Useful add-ons:**
- **ROM Collection Browser:** Emulator frontend
- **Advanced Launcher:** Custom app launching
- **Xbox Trainers:** In-game cheats
- **Script modules:** Various utilities

**Add-on location:** `E:\XBMC\scripts\` or `E:\XBMC\plugins\`

### Advantages
- Comprehensive media support
- Beautiful interface
- Extensive customization
- Active development (XBMC4Gamers)
- Large community
- Frequent updates

### Disadvantages
- Higher memory usage
- Slower loading than UnleashX
- Complex configuration
- Can be overwhelming for beginners

## Evolution X (EvoX)

One of the original custom dashboards, classic and reliable.

### Features
- File manager
- FTP server
- System information
- BIOS flashing
- Skin support
- Game launching
- Settings management

### Configuration
Config file: `E:\evoxdash.ini`

**Example configuration:**
```ini
[Network]
SetupNetwork = Yes
StaticIP = Yes
Ip = 192.168.1.100
Subnetmask = 255.255.255.0
Defaultgateway = 192.168.1.1
DNS1 = 192.168.1.1

[FTP]
Enable = Yes
Password = xbox
```

### Skins
- Classic green theme
- Various community skins available
- Limited compared to modern dashboards

### Advantages
- Very stable
- Low resource usage
- Simple interface
- BIOS flashing tools
- Historical significance

### Disadvantages
- Development ceased
- Limited features vs. modern dashboards
- Basic media support
- Dated interface

## Avalaunch

Feature-rich dashboard with advanced capabilities.

### Features
- **Advanced file manager:** Copy, move, delete with queues
- **Network support:** FTP, SMB sharing
- **Game launching:** Automatic detection
- **Skin engine:** Highly customizable
- **DVD playback:** Basic support
- **System utilities:** Diagnostics, monitoring
- **Settings:** Comprehensive configuration

### Configuration
Located in XML config files on E:\ partition

**Network setup:**
- Static IP recommended
- FTP enabled by default
- SMB server support

### Advantages
- Very customizable
- Powerful file manager
- Good game launching
- Professional appearance

### Disadvantages
- Development discontinued
- Steeper learning curve
- Some bugs never fixed
- Less community support than XBMC

## Dashboard Comparison

| Feature | MS Dash | UnleashX | XBMC4Gamers | EvoX | Avalaunch |
|---------|---------|----------|-------------|------|-----------|
| **Ease of Use** | ★★★★★ | ★★★★☆ | ★★★☆☆ | ★★★★☆ | ★★★☆☆ |
| **Media Playback** | ★★☆☆☆ | ★★☆☆☆ | ★★★★★ | ★★☆☆☆ | ★★★☆☆ |
| **File Management** | ☆☆☆☆☆ | ★★★★☆ | ★★★☆☆ | ★★★☆☆ | ★★★★★ |
| **Game Launching** | ★★★★★ | ★★★★☆ | ★★★★★ | ★★★☆☆ | ★★★★☆ |
| **Customization** | ☆☆☆☆☆ | ★★★☆☆ | ★★★★★ | ★★☆☆☆ | ★★★★☆ |
| **FTP Server** | ☆☆☆☆☆ | ★★★★★ | ★★★★☆ | ★★★★☆ | ★★★★☆ |
| **Resource Usage** | ★★★★★ | ★★★★★ | ★★☆☆☆ | ★★★★★ | ★★★★☆ |
| **Active Development** | ☆☆☆☆☆ | ☆☆☆☆☆ | ★★★★★ | ☆☆☆☆☆ | ☆☆☆☆☆ |

## Multi-Dashboard Setup

Many users run multiple dashboards on one Xbox.

### Common Configurations

**Basic Setup:**
- MS Dashboard (default)
- UnleashX (main custom dash)

**Advanced Setup:**
- MS Dashboard (default/recovery)
- XBMC4Gamers (media & games)
- UnleashX (quick file management)

**Power User Setup:**
- MS Dashboard (system/recovery)
- XBMC4Gamers (primary interface)
- UnleashX (utilities)
- EvoX (BIOS flashing)

### Dashboard Switching

**Method 1: Shortcuts**
Create .xbe shortcuts in each dashboard to launch others

**Method 2: Dashboard Loader**
Use dashboard manager to select on boot

**Method 3: Controller Combo**
Some softmods support button combos at boot:
- No buttons: Default dash
- Eject button: Alternative dash
- Both triggers: MS Dashboard

### Installation Paths

Standard dashboard locations:
- **MS Dashboard:** C:\xboxdash.xbe (original)
- **UnleashX:** E:\Dashboard\UnleashX\default.xbe
- **XBMC:** E:\XBMC\default.xbe
- **EvoX:** E:\evoxdash.xbe
- **Avalaunch:** E:\Avalaunch\default.xbe

## Dashboard Installation

### Installing UnleashX

1. Download UnleashX dashboard files
2. FTP to Xbox
3. Create folder: E:\Dashboard\UnleashX\
4. Upload all files to this folder
5. Edit config.xml for network settings
6. Add shortcut in current dashboard
7. Launch to test

### Installing XBMC4Gamers

1. Download latest XBMC4Gamers build
2. FTP to Xbox
3. Upload to E:\XBMC\
4. Configure network in settings
5. Set up media sources
6. Install desired skin
7. Configure game launching

### Setting Default Dashboard

**Via Softmod Configuration:**
1. Edit C:\evoxdash.xbe or softmod loader
2. Point to desired dashboard .xbe file
3. Reboot to apply

**Via ConfigMagic:**
1. Launch ConfigMagic
2. Navigate to Dashboard Settings
3. Browse to desired .xbe
4. Save configuration
5. Reboot

## Dashboard Maintenance

### Regular Tasks

**Clean cache:**
- Delete X:\, Y:\, Z:\ contents periodically
- Improves performance
- Frees disk space

**Update dashboards:**
- Check for new XBMC4Gamers releases
- Backup config before updating
- FTP new files over old

**Backup configs:**
- Save dashboard configurations to PC
- Document custom settings
- Keep skin backups

### Troubleshooting

**Dashboard won't load:**
- Check file integrity
- Verify .xbe file present
- Check free disk space
- Review error logs

**FTP not working:**
- Verify network settings
- Check FTP enabled in config
- Test with different FTP client
- Restart dashboard

**Slow performance:**
- Clear cache partitions
- Remove unused skins/add-ons
- Check for file corruption
- Ensure adequate free space

**Video playback issues:**
- Update XBMC build
- Check codec support
- Reduce video quality/bitrate
- Enable hardware acceleration

## Recommended Setup for Different Users

### Beginner
**Primary:** UnleashX
- Easy to use
- Simple configuration
- Good documentation
- Stable

### Media Enthusiast  
**Primary:** XBMC4Gamers
- Best media support
- Beautiful interface
- Artwork scraping
- Network streaming

### Retro Gamer
**Primary:** XBMC4Gamers or XBMC Emustation
- Emulator integration
- ROM management
- Artwork support
- Save states

### Developer/Tinkerer
**Primary:** UnleashX
**Secondary:** EvoX
- File management
- BIOS tools
- System access
- Quick operations

## Resources

### Downloads
- [XBMC4Gamers Releases](https://github.com/Rocky5/XBMC4Gamers/releases)
- [UnleashX Archive](http://www.xbox-scene.com/)
- Dashboard skin repositories

### Documentation
- [XBMC4Gamers Wiki](https://github.com/Rocky5/XBMC4Gamers/wiki)
- UnleashX config guides
- Dashboard forums

### Community
- [r/originalxbox Discord](https://discord.gg/originalxbox)
- Xbox-Scene Forums
- ConsoleMods.org

## Conclusion

Choosing the right dashboard depends on your needs:
- **Simple file management:** UnleashX
- **Media center:** XBMC4Gamers
- **Classic experience:** Evolution X
- **Advanced features:** Avalaunch

Most users benefit from multi-dashboard setups, using XBMC4Gamers as primary with UnleashX as backup.

---

*For educational purposes only. Respect copyright and intellectual property rights.*
