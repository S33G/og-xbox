# Xbox BIOS Guide

## What is the Xbox BIOS?

The BIOS (Basic Input/Output System) is the firmware that initializes the Xbox hardware during boot. On original Xbox consoles, the BIOS is stored in a flash memory chip on the motherboard.

## Stock vs. Custom BIOS

### Stock BIOS (Microsoft)
- **Original firmware** shipped with Xbox
- **Locked features:** Cannot run unsigned code
- **Region locked:** Games must match console region
- **Limited functionality:** No homebrew support
- **Versions:** Various versions (1.0, 1.1, etc.) corresponding to dashboard versions

### Custom BIOS
- **Modified firmware** created by community
- **Unsigned code execution:** Runs homebrew, backups, emulators
- **Region free:** Play games from any region
- **Enhanced features:** Fan control, boot options, network settings
- **No Xbox Live:** Custom BIOS incompatible with original Xbox Live (use Insignia instead)

## Popular Custom BIOS Options

### EvoX M8/M8plus
**History:** One of the earliest and most popular custom BIOS files

**Features:**
- Region free
- Fan speed control
- Multiple boot bank support
- Dashboard selection
- Compatible with all Xbox versions
- Well-tested and stable

**Versions:**
- **M8:** Original release
- **M8plus:** Enhanced version with additional features
- **M8plus_16:** For 1MB BIOS chips

**Recommended for:** General use, beginners, stability

### X2 BIOS (X2 4983, X2 5035)
**History:** Developed for the Xecuter modchips, but works with TSOP

**Features:**
- Advanced configuration menu
- Multiple font support
- Boot animation customization
- Auto-detection of dashboards
- LED color control
- Fan management

**Versions:**
- **X2 4977:** Earlier version
- **X2 4983:** Popular stable version  
- **X2 5035:** Latest version with most features

**Recommended for:** Users wanting customization options

### iND-BiOS
**History:** Independent BIOS created by community developers

**Features:**
- Extremely small size (256KB versions available)
- Fast boot times
- Simple configuration
- Multiple boot options
- Good compatibility

**Versions:**
- **iND 5003:** Standard version
- **iND 5004:** Updated version
- **iND 5005:** Latest release

**Recommended for:** Advanced users, minimalist setups

### Cerbios
**History:** Modern, actively developed BIOS

**Features:**
- **Modern development:** Still being updated
- **Open source:** Code available for review
- **Feature-rich:** Advanced configuration
- **Good documentation:** Well-documented features
- **Wide compatibility:** Works on all Xbox versions

**Versions:**
- Regularly updated
- Check GitHub for latest release

**Recommended for:** Users wanting modern, supported BIOS

### XROMWELL
**History:** Linux-focused BIOS

**Features:**
- Linux booting support
- Open source
- Educational purposes
- Limited gaming functionality

**Recommended for:** Linux enthusiasts, developers

## BIOS Installation Methods

### Method 1: TSOP Flashing
Flash BIOS directly to motherboard chip

**Requirements:**
- TSOP unlock points bridged
- Softmod or modchip
- BIOS flashing tool

**Advantages:**
- No additional hardware needed
- Permanent modification
- Reliable

**Disadvantages:**
- Requires soldering (for unlock points)
- Risk if flashed incorrectly
- Not available on Xbox 1.6

**See:** [TSOP Flashing Guide](../tsop/README.md)

### Method 2: Modchip
Install modchip with custom BIOS

**Requirements:**
- Modchip hardware
- Soldering skills
- BIOS file

**Advantages:**
- Can switch between BIOS banks
- Doesn't modify original BIOS
- Works on all Xbox versions including 1.6
- Recovery options

**Disadvantages:**
- Requires modchip purchase
- Soldering required
- More complex installation

**Popular modchips:**
- OpenXenium (open source)
- Aladdin XT Plus2
- Xecuter 2/3
- Modxo (Raspberry Pi Pico based)

### Method 3: Softmod with BIOS Flash
Some softmods allow BIOS flashing

**Requirements:**
- Active softmod
- Compatible BIOS file
- BIOS flash utility

**Advantages:**
- No hardware modifications
- Easy to attempt
- Reversible

**Disadvantages:**
- Risky (can brick console)
- Not all softmods support it
- No recovery if failed
- Not recommended for 1.6

## BIOS Configuration

### Boot Configuration

Most custom BIOS files allow boot order configuration:

1. **First boot:** Usually dashboard on C:\ or E:\
2. **Second boot:** Alternative dashboard
3. **Third boot:** MS Dashboard (fallback)

### Fan Control

Custom BIOS can control fan behavior:

**Options:**
- **Stock:** Microsoft's original fan curve
- **Custom speeds:** Manual percentage (e.g., 50%, 100%)
- **Temperature-based:** Adjust based on CPU/GPU temp
- **Always high:** 100% for maximum cooling

**Recommendation:** 
- Stock for normal use
- Higher speeds if overheating
- Custom speeds for noise reduction (ensure adequate cooling)

### LED Control

Many BIOS allow custom LED colors:

**Configuration:**
- Boot sequence colors
- Standby colors
- Running colors
- Eject button LED

### Network Settings

Some BIOS include network pre-configuration:
- Static IP address
- Gateway settings
- DNS servers

## BIOS Banks and Recovery

### What are BIOS Banks?

Many modchips and some TSOP flashes support multiple BIOS banks:

**256KB BIOS chip:**
- 2 banks × 256KB = 512KB total
- Switch between two different BIOS

**1MB BIOS chip:**
- Up to 4 banks × 256KB = 1MB total
- Multiple BIOS selections

### Bank Switching

**Hardware method:**
- Some modchips have physical switch
- Toggle to select bank

**Software method:**
- Dashboard utility switches bank
- Reboot to apply

**Recovery benefit:**
- Bank 1: Primary BIOS
- Bank 2: Backup/Recovery BIOS
- If Bank 1 fails, switch to Bank 2

## BIOS Flashing Process

### Safety Precautions

⚠️ **Critical warnings:**
- Wrong BIOS can brick console
- Ensure BIOS matches Xbox version
- Never power off during flash
- Have EEPROM backup
- Have recovery plan (modchip/TSOP)

### Pre-Flash Checklist

- [ ] Backup EEPROM
- [ ] Verify BIOS file is correct version
- [ ] Check MD5/SHA hash of BIOS
- [ ] Ensure stable power supply
- [ ] Have recovery method ready
- [ ] Read instructions completely

### Flashing via Softmod/Dashboard

1. **Download BIOS file**
   - Get from trusted source
   - Verify it's for your Xbox version
   - Check file size (typically 256KB or 1MB)

2. **Transfer to Xbox**
   - FTP BIOS file to E:\BIOS\
   - Or use USB/DVD method

3. **Launch flash utility**
   - Evolution X BIOS flash
   - ConfigMagic
   - Or other BIOS flash tool

4. **Select BIOS**
   - Navigate to BIOS file
   - Confirm selection

5. **Flash BIOS**
   - Start flash process
   - **Do not power off or reset!**
   - Wait for completion message

6. **Verify flash**
   - Tool will usually verify
   - Check for success message

7. **Reboot**
   - Power cycle Xbox
   - Watch boot process
   - Verify new BIOS loaded

### Flashing via Modchip Programmer

1. **Remove modchip** (if already installed)
2. **Connect to programmer**
   - Use USB programmer device
   - Connect modchip flash pins

3. **Run programmer software**
   - Select BIOS file
   - Choose chip type
   - Start programming

4. **Verify programming**
   - Read back and compare
   - Ensure successful write

5. **Reinstall modchip**
   - Place in Xbox
   - Test boot

## BIOS Compatibility

### Xbox Version Compatibility

| Xbox Version | TSOP Flash | Modchip | BIOS Support |
|--------------|------------|---------|--------------|
| **1.0** | ✓ Yes | ✓ Yes | All BIOS |
| **1.1** | ✓ Yes | ✓ Yes | All BIOS |
| **1.2** | ✓ Yes | ✓ Yes | All BIOS |
| **1.3** | ✓ Yes | ✓ Yes | All BIOS |
| **1.4** | ✓ Yes | ✓ Yes | All BIOS |
| **1.5** | ✓ Yes | ✓ Yes | All BIOS |
| **1.6** | ✗ No | ✓ Yes | 1.6-specific BIOS |

**Note:** Xbox 1.6 has different hardware (Xcalibur video chip) and requires 1.6-compatible BIOS

### BIOS File Sizes

- **256KB:** Single bank BIOS
- **512KB:** Dual bank (2 × 256KB)
- **1MB:** Four bank (4 × 256KB) or single 1MB BIOS

### RAM Upgrade Compatibility

If you've upgraded to 128MB RAM:
- Ensure BIOS supports 128MB
- Most modern BIOS (M8+, X2, Cerbios) support it
- Check BIOS documentation

## Troubleshooting

### Console won't boot after BIOS flash

**Symptoms:**
- Black screen
- FRAG (Flashing Red and Green)
- No video output

**Solutions:**
1. **Check modchip connection** (if using modchip)
2. **Switch BIOS bank** (if multi-bank)
3. **Reflash BIOS** (if possible)
4. **Install modchip** (for TSOP recovery)
5. **EEPROM restore** (if corrupted)

### Error 21 after BIOS flash

**Cause:** HDD lock/unlock mismatch

**Solutions:**
1. Use BIOS with proper HDD unlock support
2. Restore EEPROM backup
3. Use compatible BIOS version

### No video output

**Causes:**
- BIOS doesn't match Xbox version (especially 1.6)
- Video settings incompatible
- Corrupt BIOS flash

**Solutions:**
1. Try different video cable (composite, component)
2. Flash compatible BIOS
3. Check for 1.6-specific BIOS if using 1.6

### Dashboard not loading

**Causes:**
- BIOS looking for dashboard in wrong location
- Missing dashboard files
- Boot order misconfigured

**Solutions:**
1. Install dashboard to default location
2. Reconfigure BIOS boot settings
3. Check dashboard file integrity

## Advanced BIOS Topics

### Custom BIOS Building

Some advanced users create custom BIOS builds:

**Tools:**
- BIOS editors
- Hex editors
- Graphics tools for boot logos

**Modifications:**
- Custom boot animations
- Personalized text
- Modified settings defaults
- Combined features from multiple BIOS

⚠️ **Warning:** Advanced topic, risk of creating non-bootable BIOS

### BIOS Dumping

Extract BIOS from Xbox for backup or analysis:

**Methods:**
1. **ConfigMagic:** Can dump active BIOS
2. **FTP:** Download from flash memory
3. **Hardware reader:** EEPROM programmer

**Uses:**
- Backup original BIOS
- Analysis and learning
- Verify BIOS version

## BIOS Recommendations by Use Case

### General Gaming (Recommended: M8plus)
- Stable and reliable
- Good compatibility
- Easy configuration
- Well-documented

### Maximum Features (Recommended: X2 5035 or Cerbios)
- Advanced options
- Customization
- Modern features
- Active development (Cerbios)

### Quick Boot (Recommended: iND-BiOS)
- Minimal size
- Fast startup
- No-frills approach

### Xbox 1.6 (Recommended: X2 5035.67 or Cerbios)
- 1.6-specific builds
- Xcalibur chip support
- Latest compatibility

### Development/Linux (Recommended: XROMWELL)
- Linux booting
- Development features
- Educational use

## Legal and Ethical Considerations

### Legal Status
- BIOS modification is legal for personal use in most jurisdictions
- Installing custom BIOS for homebrew is generally acceptable
- Using modified BIOS for piracy is illegal
- Distribution of copyrighted BIOS files may be illegal

### Best Practices
- Use custom BIOS for homebrew and preservation
- Support developers by purchasing games
- Don't distribute copyrighted material
- Respect intellectual property

## Resources

### BIOS Downloads
- Community forums (with caution)
- GitHub repositories (Cerbios, etc.)
- Modchip manufacturer sites

### Documentation
- [ConsoleMods.org - Xbox BIOS](https://consolemods.org/wiki/Xbox:BIOS)
- Cerbios GitHub documentation
- Xbox-Scene archives

### Tools
- Evolution X BIOS flasher
- ConfigMagic
- Modchip programmers
- BIOS editors

## Frequently Asked Questions

**Q: Can I go back to stock BIOS?**
A: Yes, reflash original Microsoft BIOS (if you have backup)

**Q: Will custom BIOS damage my Xbox?**
A: No, properly flashed BIOS is safe. Improper flash can brick console.

**Q: Which BIOS is best?**
A: M8plus for beginners, X2 5035/Cerbios for features, depends on needs

**Q: Can I use Xbox Live with custom BIOS?**
A: Original Xbox Live is discontinued. Use Insignia with compatible BIOS.

**Q: Do I need modchip for custom BIOS?**
A: No, can TSOP flash (except 1.6). Modchip is safer but requires installation.

**Q: What if BIOS flash fails?**
A: Need recovery method (modchip, second BIOS bank, or TSOP reflash)

**Q: Can softmod BIOS be removed?**
A: If TSOP flashed, need to reflash. Modchip can be removed/disabled.

## Conclusion

Custom BIOS unlocks the full potential of the original Xbox. Choose the right BIOS for your needs, follow safety procedures, and always maintain backups.

**Key Takeaways:**
- M8plus: Best for beginners
- X2/Cerbios: Best for features  
- Always backup EEPROM
- Use recovery method
- Match BIOS to Xbox version

---

*For educational purposes only.*

## Sources
- [ConsoleMods.org Wiki](https://consolemods.org/wiki/Xbox:BIOS)
- [Cerbios GitHub](https://github.com/Cerbrus/Cerbios)
- Xbox-Scene Community
- Original Xbox subreddit
