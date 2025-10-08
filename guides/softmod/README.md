# Xbox Softmodding Guide

## Related Guides

This is a comprehensive guide to Xbox softmodding and the ENDGAME exploit. For specific topics, see:

- **[Custom Dashboards Guide](dashboards.md)** - Detailed guide to UnleashX, XBMC, Evolution X, and Avalaunch
- **[BIOS Guide](bios.md)** - Custom BIOS options, flashing, and configuration
- **[HDD Upgrade Guide](hdd-upgrade.md)** - Hard drive replacement and partition management
- **[Networking & FTP Guide](networking-ftp.md)** - Network configuration, FTP setup, and file transfer
- **[Emulators & Homebrew Guide](emulators-homebrew.md)** - Retro gaming emulation and homebrew applications

## What is Softmodding?

Softmodding is the process of modifying an Xbox console without the need for hardware modifications (like installing a modchip). This is accomplished by exploiting vulnerabilities in certain game save files to run unsigned code on the Xbox. Once softmodded, an Xbox can run homebrew applications, custom dashboards, emulators, and backup games.

## ENDGAME Exploit

ENDGAME is one of the most reliable and modern softmod exploits available for the original Xbox. It was developed by the Xbox community and represents years of refinement in softmodding techniques.

### Advantages of ENDGAME
- Works on all Xbox versions (1.0 through 1.6)
- Does not require specific game discs
- Can be installed via USB memory stick
- More reliable than older exploit methods
- Easier installation process
- Includes automatic EEPROM backup

### Prerequisites
- Original Xbox console (any version)
- USB flash drive (formatted to FAT32)
- PC with internet connection
- [ENDGAME exploit files](https://github.com/XboxDev/endgame-exploit)

## Game Save Exploits

Before ENDGAME, softmodding required specific game discs with exploitable save files. These exploits are still used in some scenarios:

### Splinter Cell Exploits
**Games that work:**
- Tom Clancy's Splinter Cell (original)
- Tom Clancy's Splinter Cell: Pandora Tomorrow
- Tom Clancy's Splinter Cell: Chaos Theory

**How it works:**
The game loads a corrupted save file that contains executable code. When the game attempts to load this save, it executes the embedded softmod installer.

**Installation steps:**
1. Copy the exploited save file to a memory card or transfer via Action Replay
2. Launch Splinter Cell
3. Load the exploited save ("Linux" save)
4. The softmod installer will launch automatically

### 007: Agent Under Fire
This game was one of the earliest exploited for Xbox softmodding.

**Installation steps:**
1. Copy the exploited save to memory card
2. Launch 007: Agent Under Fire
3. Load the "Linux" save file
4. Follow on-screen installer instructions

### MechAssault
Popular for its reliability and widespread availability.

**Installation steps:**
1. Copy exploited save to Xbox hard drive or memory card
2. Launch MechAssault
3. Load campaign and select the "Linux" save
4. Installer will launch

### Tony Hawk's Pro Skater 4
Another commonly used exploit game.

**Installation steps:**
1. Transfer exploited save to Xbox
2. Launch Tony Hawk's Pro Skater 4
3. Load the modified career save
4. Exploit triggers and launches installer

## Softmod Installation Process

### Method 1: ENDGAME (Recommended)

1. **Prepare USB drive:**
   - Format USB drive to FAT32
   - Copy ENDGAME exploit files to root of drive

2. **Prepare Xbox:**
   - Ensure Xbox is on dashboard
   - Remove any game discs

3. **Install ENDGAME:**
   - Insert USB drive into Xbox controller port (may need adapter)
   - Navigate to Memory settings
   - Copy ENDGAME save to Xbox hard drive
   - Launch the exploit through the dashboard

4. **Run installer:**
   - ENDGAME will automatically backup your EEPROM
   - Follow on-screen prompts to install softmod
   - Select dashboard preference (UnleashX, XBMC, etc.)

### Method 2: Traditional Game Save Exploit

1. **Obtain exploit game and save:**
   - Purchase one of the exploitable games
   - Download corresponding exploit save
   - Transfer save to Xbox via memory card or Action Replay

2. **Launch exploit:**
   - Insert game disc
   - Load the exploit save file
   - Softmod installer launches

3. **Configure softmod:**
   - Follow installer prompts
   - Backup EEPROM (critical step!)
   - Install custom dashboard
   - Configure FTP settings

## EEPROM Management

### What is the EEPROM?
The EEPROM (Electrically Erasable Programmable Read-Only Memory) is a small chip on the Xbox motherboard that contains:
- HDD key (locks hard drive to specific console)
- Region code
- Serial number
- Video settings
- Parental control settings

### Why Backup EEPROM?
**Critical:** The EEPROM backup is essential for:
- Hard drive replacement
- Console recovery after softmod corruption
- TSOP flashing
- Modchip installation recovery

### How to Backup EEPROM

**Via Softmod:**
1. Most softmod installers automatically backup EEPROM
2. EEPROM.bin is saved to C:\backup\ or E:\backup\
3. Always copy this file to PC for safekeeping
4. Store multiple copies in different locations

**Via ConfigMagic:**
1. Launch ConfigMagic from dashboard
2. Select "Backup EEPROM"
3. EEPROM saved to E:\backup\eeprom.bin
4. FTP file to PC immediately

**Via Xbox EEPROM Utility:**
1. Use [dx4m/Xbox-EEPROM-Utility](https://github.com/dx4m/Xbox-EEPROM-Utility)
2. Can read EEPROM via I2C or from backup files
3. Extracts HDD key and other critical information

### EEPROM Restoration
If your EEPROM becomes corrupted:
1. Boot to modchip or TSOP (if flashed)
2. Use ConfigMagic or similar tool
3. Restore EEPROM.bin from backup
4. Reboot console

## Custom Dashboards

After softmodding, you can install custom dashboards that provide enhanced functionality:

### UnleashX
- Lightweight and fast
- Clean interface
- Supports skins
- Built-in FTP server
- File manager
- Game launching

### XBMC (Xbox Media Center)
- Now maintained as XBMC4Xbox and XBMC4Gamers
- Full media center capabilities
- Video/music/photo playback
- Network streaming
- Emulator launcher
- Skin support

### Evolution X (EvoX)
- One of the original custom dashboards
- File management
- FTP capabilities
- System information
- BIOS flashing tools

### Avalaunch
- Feature-rich dashboard
- Advanced file management
- Network capabilities
- Customizable interface
- DVD playback

## FTP Setup

FTP (File Transfer Protocol) allows you to transfer files between your PC and Xbox over a network.

### Network Setup
1. Connect Xbox to router via Ethernet
2. Boot to custom dashboard
3. Navigate to Network Settings
4. Configure network:
   - **Automatic (DHCP):** Easiest, automatically assigns IP
   - **Static IP:** Manual configuration, more reliable

### Recommended Static IP Settings
```
IP Address: 192.168.1.100 (or similar)
Subnet Mask: 255.255.255.0
Gateway: 192.168.1.1 (your router IP)
DNS: 192.168.1.1
```

### FTP Credentials
Most dashboards use default credentials:
- **Username:** xbox
- **Password:** xbox

### FTP Clients
Recommended FTP clients for PC:
- **FileZilla** (Free, cross-platform)
- **WinSCP** (Windows, supports SFTP)
- **Cyberduck** (Mac/Windows)

### FTP Connection
1. Open FTP client
2. Enter Xbox IP address
3. Port: 21
4. Username: xbox
5. Password: xbox
6. Connect

### Xbox Directory Structure
- **C:\** - System partition (250MB, don't modify unless necessary)
- **E:\** - Game partition (rest of HDD, user data)
- **F:\** - DVD drive
- **X:\** - BIOS partition (active)
- **Y:\** - Cache partition
- **Z:\** - Cache partition

## BIOS Flashing via Softmod

Some softmods allow BIOS flashing without a modchip:

### Compatible BIOS Files
- **M8plus** - Popular, supports all Xbox versions
- **EvoX M8** - Classic choice
- **X2 5035** - Feature-rich
- **iND-BiOS** - Lightweight

### Flashing Process
1. Download BIOS file (.bin format)
2. FTP to E:\BIOS\
3. Launch BIOS flash utility from dashboard
4. Select BIOS file
5. Confirm flash operation
6. **Warning:** Incorrect BIOS can brick console
7. Wait for completion
8. Reboot

### Safety Precautions
- Ensure BIOS is compatible with Xbox version
- Verify file integrity (MD5 checksum)
- Never power off during flash
- Keep EEPROM backup accessible
- Have recovery method ready (modchip)

## Softmod Recovery

### Common Issues

**Black screen on boot:**
- Check video cable connection
- Try different video output setting
- Boot to original MS dashboard (hold eject during boot on some softmods)

**FRAG (Flashing Red and Green):**
- Indicates boot failure
- Often EEPROM or HDD corruption
- May need modchip for recovery

**Error 21 (HDD locked):**
- HDD key mismatch
- Restore EEPROM backup
- Use EEPROM reader if backup unavailable

### Recovery Methods

**Method 1: Boot to MS Dashboard**
- Hold eject button during power on
- If successful, can reinstall softmod

**Method 2: Hotswap**
- Advanced technique to unlock HDD
- Requires PC and IDE adapter
- Swap HDD while running to trick Xbox
- **Risky:** Can damage hardware

**Method 3: EEPROM Restore**
- Use backup EEPROM.bin
- Boot via modchip if available
- Use ConfigMagic to restore

**Method 4: Modchip Installation**
- Install modchip for recovery boot
- Reflash TSOP or reinstall softmod
- Can bypass most softmod issues

## Upgrading Hard Drive

One major benefit of softmodding is the ability to upgrade to larger hard drives.

### HDD Requirements
- IDE interface (PATA)
- 3.5" form factor
- 8GB minimum, 2TB maximum (with F/G partition support)
- Compatible drives listed at [xboxdrives.x-pec.com](https://xboxdrives.x-pec.com/?p=list)

### Upgrade Methods

**Method 1: Chimp (Recommended)**
1. Install Chimp bootable disc tool
2. Connect new HDD to Xbox
3. Clone existing drive to new drive
4. Swap drives
5. Boot and verify

**Method 2: XboxHDM**
1. Use PC with XboxHDM software
2. Lock new drive with EEPROM key
3. Install softmod files to new drive
4. Install in Xbox

**Method 3: FATXplorer (PC)**
1. Connect drives to PC
2. Use FATXplorer to clone and expand
3. Lock drive with EEPROM
4. Install in Xbox

### Partition Expansion
After cloning to larger drive:
1. Use partition manager (XBPartitioner)
2. Expand E partition
3. Create F and G partitions for extra space
4. Reboot and verify

## Legal and Safety Considerations

### Legal Notice
- Softmodding is legal for running homebrew
- Running pirated games is illegal
- Educational purposes only
- Modifications void warranty

### Safety Tips
- Always backup EEPROM first
- Store multiple EEPROM copies
- Don't delete system files unless certain
- Keep original game saves
- Use surge-protected power
- Ensure proper ventilation
- Replace clock capacitor (especially v1.0-1.5)

## Tools and Software

### Essential Tools
- [Rocky5's Softmod Tool](https://github.com/Rocky5/Xbox-Softmodding-Tool) - Comprehensive installer
- [ENDGAME Exploit](https://github.com/XboxDev/endgame-exploit) - Modern exploit method
- [ConfigMagic](http://www.xbox-scene.com/) - System configuration tool
- [Xbox EEPROM Utility](https://github.com/dx4m/Xbox-EEPROM-Utility) - EEPROM management

### Useful Dashboards
- [XBMC4Gamers](https://github.com/Rocky5/XBMC4Gamers) - Enhanced XBMC
- [UnleashX](http://www.xbox-scene.com/) - Lightweight dashboard
- [Evolution X](http://www.xbox-scene.com/) - Classic dashboard

### HDD Tools
- [Chimp](http://www.xbox-scene.com/) - HDD cloning
- [XboxHDM](https://sourceforge.net/projects/xboxhdm/) - PC-based HDD preparation
- [XBPartitioner](http://www.xbox-scene.com/) - Partition manager

## Additional Resources

### Community Forums
- [Xbox-Scene Forums](https://www.xbox-scene.com/)
- [Ogxbox Reddit](https://www.reddit.com/r/originalxbox/)
- [AssemblerGames Archives](https://www.assembler-games.com/)

### Video Tutorials
- MrMario2011's Xbox Softmodding Series
- Mrmario2011 ENDGAME Tutorial
- Blaine Locklair's Xbox Guides

### Documentation
- [ConsoleMods Wiki - ENDGAME](https://consolemods.org/wiki/Xbox:ENDGAME)
- [Xbox-Scene Tutorials](https://www.xbox-scene.com/)
- [Original Xbox Subreddit Wiki](https://www.reddit.com/r/originalxbox/wiki/)

## Troubleshooting

### Softmod won't install
- Verify game disc is compatible version
- Ensure save file is correctly transferred
- Try different exploit game
- Check USB drive formatting (FAT32)

### Can't connect via FTP
- Verify network cable connection
- Check IP address configuration
- Ensure FTP server is enabled in dashboard
- Try static IP instead of DHCP
- Disable firewall on PC temporarily

### Games won't launch
- Verify disc is clean
- Check region compatibility
- Update dashboard
- Try different dashboard

### Poor performance after softmod
- Clear cache partitions
- Reduce dashboard features
- Check for file corruption
- Verify adequate free space

## Frequently Asked Questions

**Q: Will softmodding damage my Xbox?**
A: No, if done correctly. Always backup EEPROM first.

**Q: Can I still play Xbox Live?**
A: Original Xbox Live is discontinued. Use [Insignia](https://insignia.live/) for online play.

**Q: Can I remove a softmod?**
A: Yes, boot to MS dashboard and delete softmod files, or reinstall with stock EEPROM.

**Q: Do I need a specific Xbox version?**
A: No, softmods work on all versions (1.0-1.6).

**Q: What's the difference between softmod and TSOP?**
A: Softmod is software-only; TSOP flashing modifies BIOS chip directly (requires soldering).

**Q: Can I upgrade RAM with just a softmod?**
A: No, RAM upgrade requires physical soldering and BIOS support.

**Q: Is ENDGAME better than other exploits?**
A: Yes, ENDGAME is more reliable and easier to use than older game save exploits.

**Q: What size HDD can I use?**
A: Up to 2TB with proper formatting and partitioning tools.

## Conclusion

Softmodding opens up the full potential of the original Xbox without requiring hardware modifications. With proper preparation and following safety guidelines, anyone can successfully softmod their Xbox and enjoy homebrew applications, emulators, and enhanced functionality.

**Remember:**
- Always backup EEPROM
- Store backups safely
- Follow instructions carefully
- Join community forums for support
- Respect copyright laws

---

*This guide is for educational purposes only. Always respect intellectual property rights and local laws.*

## Sources

- [ConsoleMods.org - Xbox ENDGAME](https://consolemods.org/wiki/Xbox:ENDGAME)
- [XboxDev - ENDGAME Exploit](https://github.com/XboxDev/endgame-exploit)
- [Rocky5's Softmodding Tool](https://github.com/Rocky5/Xbox-Softmodding-Tool)
- Xbox Scene Community
- Original Xbox Reddit Community
