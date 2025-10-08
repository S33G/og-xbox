# Xbox Networking & FTP Guide

## Introduction

Setting up networking on a modified Xbox enables file transfer, media streaming, online gaming through Insignia, and remote management. This guide covers network configuration, FTP setup, and troubleshooting.

## Network Hardware

### Built-in Ethernet

All original Xbox consoles include:
- **10/100 Mbps Ethernet port**
- **Integrated network controller**
- **Auto-negotiation** of speed/duplex
- **Wake-on-LAN** support (with some modifications)

### No Wi-Fi

The Xbox does not have built-in wireless networking. Options include:
- **Ethernet cable** (recommended)
- **Powerline adapters** (ethernet over electrical wiring)
- **Wireless bridge** (connects to Wi-Fi, provides ethernet port)
- ❌ **USB Wi-Fi adapters** do not work on Xbox

## Network Configuration Methods

### DHCP (Automatic)

**How it works:**
- Xbox requests IP from router
- Router assigns IP, gateway, DNS automatically
- Simplest configuration

**Advantages:**
- Easy setup
- No manual configuration
- Works out of the box

**Disadvantages:**
- IP address may change
- Makes FTP connection less reliable
- Some dashboards poorly implement DHCP

**When to use:**
- Testing network connectivity
- Temporary connections
- One-time file transfers

### Static IP (Recommended)

**How it works:**
- Manually assign IP address
- Configure gateway and DNS
- Xbox always uses same IP

**Advantages:**
- Consistent IP address
- Reliable FTP connections
- Better for network services
- Easier to manage

**Disadvantages:**
- Requires manual configuration
- Need to know network settings
- Risk of IP conflicts if not managed

**When to use:**
- Permanent setups
- Regular FTP usage
- Insignia gaming
- Media server access

## Network Settings

### Required Information

To configure static IP, you need:

1. **IP Address** for Xbox
   - Example: 192.168.1.100
   - Must be in your network range
   - Must not conflict with other devices

2. **Subnet Mask**
   - Usually: 255.255.255.0
   - Defines network size

3. **Default Gateway**
   - Your router's IP address
   - Usually: 192.168.1.1 or 192.168.0.1
   - Find in router settings or PC network info

4. **DNS Server**
   - Usually same as gateway: 192.168.1.1
   - Or use public DNS: 8.8.8.8 (Google)
   - Required for name resolution

### Finding Your Network Settings (PC)

**Windows:**
```
1. Open Command Prompt
2. Type: ipconfig
3. Note:
   - IPv4 Address (your PC's IP)
   - Subnet Mask
   - Default Gateway
   - DNS Servers
```

**Mac:**
```
1. System Preferences > Network
2. Select active connection
3. Click "Advanced"
4. Note TCP/IP and DNS settings
```

**Linux:**
```
1. Open terminal
2. Type: ip addr show
3. Type: ip route show
4. Note network information
```

## Configuring Network on Xbox

### Via UnleashX

1. Launch UnleashX dashboard
2. Navigate to **Settings** > **Network**
3. Select **Static IP** (or Manual)
4. Enter network information:
   - IP Address: 192.168.1.100 (example)
   - Subnet Mask: 255.255.255.0
   - Gateway: 192.168.1.1
   - DNS: 192.168.1.1
5. Save settings
6. Reboot Xbox
7. Verify connection in network settings

### Via XBMC/XBMC4Gamers

1. Launch XBMC
2. Navigate to **System** > **Settings** > **Network**
3. Select **Network Setup**
4. Choose **Manual Configuration**
5. Enter network details:
   - IP Address: 192.168.1.100
   - Netmask: 255.255.255.0
   - Default Gateway: 192.168.1.1
   - DNS Server: 192.168.1.1
6. Save configuration
7. Test connection (Settings > Network > Network Status)

### Via Evolution X

1. Launch EvoX dashboard
2. Edit **evoxdash.ini** via Settings or FTP
3. Find **[Network]** section:
   ```ini
   [Network]
   SetupNetwork = Yes
   StaticIP = Yes
   Ip = 192.168.1.100
   Subnetmask = 255.255.255.0
   Defaultgateway = 192.168.1.1
   DNS1 = 192.168.1.1
   ```
4. Save file
5. Reboot Xbox

### Via ConfigMagic

1. Launch ConfigMagic
2. Navigate to **Network Settings**
3. Select **Static IP Configuration**
4. Enter all network parameters
5. Save to EEPROM (optional)
6. Reboot

## FTP (File Transfer Protocol)

### What is FTP?

FTP allows transferring files between Xbox and PC:
- **Upload** games, saves, applications to Xbox
- **Download** EEPROM backups, saves from Xbox
- **Manage** files on Xbox remotely
- **Edit** configuration files

### FTP Server on Xbox

Most custom dashboards include built-in FTP server:

**UnleashX:**
- Automatic FTP server
- Configured in config.xml
- Default credentials: xbox/xbox
- Port 21

**XBMC/XBMC4Gamers:**
- Enable in Network Settings
- Settings > Network > Services > FTP
- Default credentials: xbox/xbox
- Port 21

**Evolution X:**
- Enabled by default
- Configured in evoxdash.ini
- Default credentials: xbox/xbox
- Port 21

### FTP Client Software

**Recommended FTP clients:**

**FileZilla (Free, cross-platform):**
- Download: https://filezilla-project.org
- User-friendly GUI
- Supports drag-and-drop
- Queue management

**WinSCP (Windows, Free):**
- Download: https://winscp.net
- Explorer-like interface
- Supports both FTP and SFTP
- Powerful file operations

**Cyberduck (Mac/Windows, Free):**
- Download: https://cyberduck.io
- Clean interface
- Bookmark management
- Good for Mac users

**Command Line FTP:**
- Built into Windows/Mac/Linux
- Good for quick transfers
- No GUI needed

### Connecting via FTP

**FileZilla Example:**

1. Open FileZilla
2. Enter connection details:
   - **Host:** 192.168.1.100 (Xbox IP)
   - **Username:** xbox
   - **Password:** xbox
   - **Port:** 21
3. Click "Quickconnect"
4. Accept any security warnings
5. Browse Xbox filesystem

**Command Line Example:**
```
ftp 192.168.1.100
Username: xbox
Password: xbox
```

### FTP Default Credentials

Most dashboards use:
- **Username:** xbox
- **Password:** xbox

**Change default password:**
- Edit dashboard config file
- Important for network security
- Prevents unauthorized access

## Xbox Directory Structure (FTP)

### Standard Partitions

**C:\\ (System - ~500MB)**
- Dashboard files
- System files
- BIOS (read-only on some systems)
- Configuration files
- ⚠️ **Caution:** Don't delete unless certain

**E:\\ (Games/Data - Varies)**
- User data
- Games
- Saves
- Applications
- Dashboards
- Media files

**F:\\ (Extended partition 1 - Optional)**
- Additional storage
- Games
- Media

**G:\\ (Extended partition 2 - Optional)**
- Additional storage on large drives (>137GB)
- Games
- Media

**X:\\ (BIOS - Runtime)**
- Active during boot
- Cannot modify while running

**Y:\\ and Z:\\ (Cache)**
- Temporary files
- Game caches
- Can safely delete contents

**F:\\ (DVD Drive)**
- Disc contents when inserted

### Important Directories

**C:\\xboxdash.xbe**
- Original Microsoft Dashboard

**E:\\UDATA**
- Game saves (standard location)

**E:\\TDATA**
- Game title data

**E:\\Backup**
- EEPROM backups (common location)

**E:\\Apps**
- Homebrew applications

**E:\\Emulators**
- Emulator installations

**E:\\Games**
- Backup games

**E:\\XBMC** or **E:\\Dashboard**
- Custom dashboard locations

## File Transfer Best Practices

### Upload Speed

- **Network speed:** 100 Mbps max (12.5 MB/s)
- **Actual speeds:** Usually 5-10 MB/s
- **Large files:** Be patient, can take time

### Transfer Tips

1. **Use wired connection** for reliability
2. **Close other network apps** to maximize speed
3. **Transfer during dashboard idle** (not while gaming)
4. **Verify file integrity** after large transfers
5. **Keep FTP client updated**

### Avoiding Corruption

- Don't interrupt transfers
- Ensure stable power
- Verify file sizes after transfer
- Test files before deleting source

## Network Services

### SMB/CIFS (Windows File Sharing)

XBMC supports SMB for network shares:

**Add network source:**
1. XBMC > Videos/Music > Files
2. Add Source > Browse
3. Add Network Location
4. Enter: smb://192.168.1.50/share
5. Enter credentials if needed
6. Access shared media

### HTTP Streaming

XBMC can stream from HTTP sources:
- Web servers
- NAS devices
- Media servers

### UPnP/DLNA

XBMC supports UPnP media servers:
- Windows Media Player
- Plex
- Other DLNA servers

## Insignia (Xbox Live Replacement)

### What is Insignia?

- Community-run Xbox Live replacement
- Free online gaming
- System Link over internet
- Game stat tracking

### Network Setup for Insignia

1. **Configure DNS** to point to Insignia:
   - Primary DNS: Use Insignia DNS
   - Check insignia.live for current IPs

2. **Register Xbox:**
   - Must use Insignia Setup Assistant
   - Creates online profile
   - One-time setup

3. **Port forwarding** (for hosting games):
   - Forward UDP port 3074 to Xbox IP
   - Configure in router settings

See: [Insignia documentation](../insignia/tips.md) for detailed setup

## Troubleshooting

### Cannot Connect via FTP

**Symptoms:** FTP client can't reach Xbox

**Causes and solutions:**

1. **Wrong IP address**
   - Verify Xbox IP in dashboard
   - Ping Xbox from PC: `ping 192.168.1.100`

2. **FTP not enabled**
   - Check dashboard FTP settings
   - Ensure FTP server is running

3. **Network cable issue**
   - Check cable connection
   - Try different cable
   - Check router port

4. **Firewall blocking**
   - Temporarily disable PC firewall
   - Add FTP client to firewall exceptions
   - Allow port 21

5. **Wrong subnet**
   - Ensure PC and Xbox on same network
   - Check subnet mask matches

### Slow FTP Speeds

**Causes and solutions:**

1. **Network congestion**
   - Close other network apps
   - Reduce simultaneous transfers

2. **Bad cable**
   - Try different ethernet cable
   - Use Cat5e or Cat6 cable

3. **Router issues**
   - Restart router
   - Check router settings
   - Update router firmware

4. **Xbox HDD slow**
   - Fragmented drive
   - Failing hard drive
   - Consider HDD upgrade

### Network Settings Not Saving

**Symptoms:** Settings revert after reboot

**Causes and solutions:**

1. **Multiple dashboards** changing settings
   - Set all dashboards to same network config
   - Or set to "Dashboard Default" in other dashboards

2. **EEPROM not updated**
   - Some settings need EEPROM write
   - Use ConfigMagic to save to EEPROM

3. **Corrupt config file**
   - Manually edit config file via FTP
   - Restore from backup

### Can't Access Network Shares

**XBMC SMB issues:**

**Causes and solutions:**

1. **SMB version mismatch**
   - Enable SMB v1 on Windows 10/11
   - Configure NAS for SMB v1 compatibility

2. **Credentials incorrect**
   - Use correct username/password
   - Check share permissions

3. **Network discovery disabled**
   - Enable network discovery on PC
   - Check firewall settings

### DNS Not Working

**Symptoms:** Can't resolve names, only IP works

**Causes and solutions:**

1. **Wrong DNS server**
   - Use router IP as DNS
   - Or use 8.8.8.8 (Google DNS)

2. **Dashboard DNS bug**
   - Some dashboards have DNS issues
   - Use IP addresses instead of names
   - Update dashboard

## Advanced Networking

### Static DHCP Reservation

Better than static IP for some users:

**How it works:**
- Configure router to always give same IP to Xbox
- Xbox still uses DHCP
- IP address remains consistent

**Setup:**
1. Find Xbox MAC address (in dashboard network info)
2. Log into router admin panel
3. Find DHCP reservation or static lease
4. Add Xbox MAC address with desired IP
5. Save router settings
6. Reboot Xbox

### Custom DNS for Content Filtering

**Use cases:**
- Block ads
- Parental controls
- Security

**Setup:**
- Configure DNS to filtering service
- Examples: OpenDNS, Cloudflare Family

### Network Boot (Advanced)

Some modded Xboxes support network booting:
- Boot from network image
- Requires special configuration
- Advanced topic

## Security Considerations

### Change Default FTP Password

**Why:**
- Default xbox/xbox is widely known
- Anyone on network can access
- Potential data loss or malicious access

**How:**
Edit dashboard config to change FTP password

### Firewall

Consider network firewall if sharing network with untrusted devices

### VPN

Some users run Xbox traffic through VPN:
- Configure VPN on router
- Or on PC if using internet sharing
- Useful for Insignia in some regions

## Network Tools

### Dashboard Network Tools

**Network Settings Viewer:**
- See current IP, gateway, DNS
- Test connectivity
- Verify configuration

**Speed Test:**
- Some dashboards include speed test
- Verify network performance

### PC Tools for Troubleshooting

**Ping:**
```
ping 192.168.1.100
```
Tests basic connectivity

**Traceroute:**
```
tracert 192.168.1.100  (Windows)
traceroute 192.168.1.100  (Mac/Linux)
```
Shows network path

**Port Scanner:**
- Verify FTP port 21 open
- Check for other services

**Wireshark:**
- Packet capture and analysis
- Advanced troubleshooting
- See network traffic

## Recommended Network Setup

### Home Gaming Setup

```
Xbox: 192.168.1.100 (Static)
Subnet: 255.255.255.0
Gateway: 192.168.1.1 (Router)
DNS: 192.168.1.1
FTP: Enabled, changed password
```

### Media Center Setup

```
Xbox: 192.168.1.100 (Static)
Subnet: 255.255.255.0  
Gateway: 192.168.1.1
DNS: 192.168.1.1
SMB: Configured for NAS access
Media Shares: Mounted in XBMC
```

### Insignia Gaming Setup

```
Xbox: 192.168.1.100 (Static)
Subnet: 255.255.255.0
Gateway: 192.168.1.1
DNS: Insignia DNS servers
Port Forwarding: UDP 3074 → 192.168.1.100
```

## Resources

### Documentation
- [Insignia Setup Guide](../insignia/tips.md)
- Dashboard network configuration docs
- Router-specific port forwarding guides

### Tools
- [FileZilla FTP Client](https://filezilla-project.org)
- [WinSCP](https://winscp.net)
- Network scanning tools

### Community
- r/originalxbox Discord
- Xbox-Scene forums
- ConsoleMods.org

## Conclusion

Proper network setup enables the full potential of a modified Xbox. Use static IP for reliability, FTP for file management, and enjoy network features like media streaming and Insignia gaming.

**Key Points:**
- Static IP is more reliable than DHCP
- Default FTP credentials: xbox/xbox
- Change FTP password for security
- Use FileZilla or WinSCP for transfers
- Configure properly for Insignia gaming

---

*For educational purposes only.*
