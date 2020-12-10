# Format Guideline

> This is based on _Windows 10 Pro 20H2_.

## BIOS Settings

* Ai Tweaker
  - Memory Frequency: **DDR4-3600MHz**
  - DRAM Voltage: **_1.3_**
  - DRAM Timing Control
    + DRAM CAS# Latency: **_18_**
    + Trcdrd: **_20_**
    + Trcdwr: **_20_**
    + DRAM RAS# PRE Time: **_20_**
    + DRAM RAS# ACT Time: **_38_**
    + Cmd2T: **1T**
* Advanced
  - CPU Configuration
    + SVM Mode: **Enabled**

## Remove OEM Partition

Open _CMD_ by pressing <kbd>Shift</kbd> + <kbd>F10</kbd> and execute `diskpart`.

```cmd
list disk
select disk <your disk number>
clean
convert gpt
create partition efi size=100
create partition msr size=16
create partition primary
format quick fs=ntfs
exit
```

## OS Settings

### Drivers

* [ASUS TUF B450M-PRO GAMING](https://www.asus.com/us/Motherboards/TUF-B450M-PRO-GAMING/HelpDesk_Download/) (Chipset)

### Windows Settings

* System
  - Power & sleep
    + Additional power settings → Choose or customize a power plan: **AMD Ryzen™ High Performance**
    + Screen → When plugged in, turn off after: **15 minutes**
    + Screen → When plugged in, PC goes to sleep after: **2 hours**
  - Remote Desktop
    + Enable Remote Desktop: **On**
  - About
    + Rename this PC: **_xxx-desktop_**
* Personalization
  - Colors
    + Choose your color: **Dark**
  - Themes
    + Desktop icon settings: **Computer, Recycle Bin, Users's Files**
  - Start
    + Show recently added apps: **Off**
    + Show most used apps: **Off**
    + Show suggestions occasionally in Start: **Off**
* Apps
  - Default Apps
    + Web browser: **Google Chrome**
* Accounts
  - Sign-in options
    + Privacy → Use my sign-in info to automatically finish setting up my device after an update or restart: **Off**
* Time & Language
  - Date & time
    + Time zone: **(UTC+09:00) Seoul**
  - Region
    + _이 항목은 반드시 모든 프로그램 설치 및 세팅을 완료하고 가장 마지막에 수행할 것_
    + Additional date, time & regional settings → Region → Administrative → Change system locale: **Korean (Korea)**
  - Language
    + Preferred languages → Add a language: **Korean**
    + Keyboard → Override for default input method: **Korean - Microsoft IME**
* Ease of Access
  - Keyboard
    + Use Sticky Keys → Allow the shortcut key to start Sticky Keys: **Uncheck**
    + Use Toggle Keys → Allow the shortcut key to start Toggle Keys: **Uncheck**
    + Use Filter Keys → Allow the shortcut key to start Filter Keys: **Uncheck**
* Privacy
  - Activity history
    + Store my activity history on this device: **Uncheck**
    + Store my activity history to Microsoft: **Uncheck**
    + Show activities from these accounts: **Off**

### Fonts

https://github.com/nbsp1221/fonts-setup

### Uninstall Default Apps

* 3D Viewer
* Feedback Hub
* Microsoft Solitaire Collection
* Mixed Reaality Portal
* Office
* OneNote
* Paint 3D
* Skype
* Spotify
* Tips
* Weather

### Folder Options

File Explorer 열기 → 왼쪽 상단의 File 클릭 → Change folder and search options

* General
  - Open File Explorer to: **This PC**
  - Privacy
    + Show recently used files in Quick access: **Uncheck**
    + Show frequently used folders in Quick access: **Uncheck**
* View
  - Hidden files and folders: **Show hidden files, folders, and drives**
  - Hide extensions for known file types: **Uncheck**

### [Fix Right-Click Context Menu](https://www.top-password.com/blog/fix-windows-10-opens-right-click-context-menu-to-left-side/)

Open `shell:::{80F3F1D5-FECA-45F3-BC32-752C152E456E}`

* Other
  - Handedness: **Left-handed**

### [Windows Subsystem for Linux (WSL) 2](https://docs.microsoft.com/en-us/windows/wsl/install-win10)

1. Open _PowerShell_ as _Administrator_ and run.

```powershell
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
```

2. Restart your PC.
3. Run the following command in _PowerShell_ to set WSL 2 as the default version when installing a new Linux distribution.

```powershell
wsl --set-default-version 2
```

### [WSL Settings](https://github.com/nbsp1221/wsl-setup)

```shell
git clone https://github.com/nbsp1221/wsl-setup.git
cd wsl-setup
./wsl-setup.sh
```

## Programs

### Utility

* [Bandizip](https://en.bandisoft.com/bandizip/)
* [Everything](https://www.voidtools.com/) - 빠른 파일 검색
* [CrystalDiskInfo / CrystalDiskMark](https://crystalmark.info/en/download/) - HDD / SSD 정보 확인 및 속도 측정
* [CPU-Z](https://www.cpuid.com/softwares/cpu-z.html) - 컴퓨터 사양 확인
* [HWMonitor](https://www.cpuid.com/softwares/hwmonitor.html) - 하드웨어 온도 측정
* [Docker](https://hub.docker.com/editions/community/docker-ce-desktop-windows/) - WSL 2 전용으로 사용할 것
* [VMware Workstation](https://www.vmware.com/products/workstation-player/workstation-player-evaluation.html)
* [Process Hacker](https://processhacker.sourceforge.io/downloads.php) - 프로세스 관리
* [Autoruns](https://docs.microsoft.com/en-us/sysinternals/downloads/autoruns) - 시작 프로그램 관리

### Messenger

* [KakaoTalk](https://www.kakaocorp.com/service/KakaoTalk?lang=en)
* [Telegram](https://desktop.telegram.org/)
* [Discord](https://discord.com/)

### Game

* [Steam](https://store.steampowered.com/about/)
* [Minecraft](https://www.minecraft.net/en-us/download)

### Development

* [Visual Studio](https://visualstudio.microsoft.com/)
* [Visual Studio Code](https://code.visualstudio.com/#alt-downloads)

## Program Settings

### NVIDIA Control Panel

* Menu bar
  - Desktop
    + Show Notification Tray Icon: **Uncheck**
* 3D Settings
  - Manage 3D Settings
    + Power management mode: **Prefer maximum performance** ([GPU 100% freezing issue](https://quasarzone.com/bbs/qf_hwjoin/views/293887))

### OneDrive

* OneDrive 폴더 경로 수정: **_D:\OneDrives\OneDrive_**
* 트레이 아이콘 오른쪽 클릭 → Settings
  - Backup
    + Screenshots → Automatically save screenshots I capture to OneDrive: **Uncheck**

### Google Chrome

* Appearance
  - Show home button: **_https://www.naver.com/_**
  - Show bookmarks bar: **On**
  - Customize fonts
    + Standard font: **Noto Sans CJK KR**
    + Serif font: **NanumMyeongjo**
    + Sans-serif font: **Noto Sans CJK KR**
    + Fixed-width font: **D2Coding**

### Visual Studio Code

```json
{
  "debug.javascript.codelens.npmScripts": "never",
  "editor.fontFamily": "Iosevka, D2Coding, monospace",
  "editor.fontSize": 18,
  "editor.tabSize": 2,
  "terminal.integrated.fontFamily": "'Iosevka Fixed', D2Coding, monospace",
  "terminal.integrated.fontSize": 18,
  "terminal.integrated.shell.windows": "C:\\Windows\\System32\\wsl.exe",
  "workbench.iconTheme": "vscode-icons",
  "[c]": {
    "editor.tabSize": 4
  },
  "[cpp]": {
    "editor.tabSize": 4
  },
  "[python]": {
    "editor.tabSize": 4
  }
}
```

### Windows Terminal

```json
{
  "$schema": "https://aka.ms/terminal-profiles-schema",
  "defaultProfile": "{2c4de342-38b7-51cf-b940-2309a097f518}",
  "copyOnSelect": false,
  "copyFormatting": false,
  "multiLinePasteWarning": false,
  "profiles": {
    "defaults": {
      "fontFace": "Iosevka Fixed",
      "fontSize": 14
    },
    "list": [
      {
        "guid": "{2c4de342-38b7-51cf-b940-2309a097f518}",
        "name": "Ubuntu",
        "source": "Windows.Terminal.Wsl",
        "hidden": false,
        "startingDirectory": "//wsl$/Ubuntu/home/retn0"
      },
      {
        "guid": "{0caa0dad-35be-5f56-a8ff-afceeeaa6101}",
        "name": "Command Prompt",
        "commandline": "cmd.exe",
        "hidden": false
      },
      {
        "guid": "{61c54bbd-c2c6-5271-96e7-009a87ff44bf}",
        "name": "Windows PowerShell",
        "commandline": "powershell.exe",
        "hidden": false
      },
      {
        "guid": "{b453ae62-4e3d-5e58-b989-0a998ec441b8}",
        "name": "Azure Cloud Shell",
        "source": "Windows.Terminal.Azure",
        "hidden": true
      }
    ]
  },
  "schemes": [],
  "actions": [
    { "command": { "action": "copy", "singleLine": false }, "keys": "ctrl+c" },
    { "command": "paste", "keys": "ctrl+v" },
    { "command": "find", "keys": "ctrl+shift+f" },
    { "command": { "action": "splitPane", "split": "auto", "splitMode": "duplicate" }, "keys": "alt+shift+d" }
  ]
}
```
