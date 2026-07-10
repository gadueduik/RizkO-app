# RizkO

RizkO is a desktop and mobile trading journal and analytics application designed to help traders record, track, and analyze their trading performance. Built on the Avalonia UI framework, it offers a fast, modern, and cross-platform experience.

## Key Features

- **Trading Journal**: Record your daily trades with details such as entry/exit prices, position sizes, assets, status, notes, and attachments like trade screenshots.
- **Performance Analytics**: Track your progress with interactive charts, including Cumulative PnL, Daily PnL, and account growth statistics.
- **Trading Calculators**: Access built-in calculators to compute PnL, evaluate account health, and project future account growth based on various scenarios.
- **Excel Import**: Import trade history directly from external Excel files with custom column mapping and flexible trade closure detection rules.
- **Multi-Currency Support**: Manage accounts in different currencies with built-in currency conversion and exchange rate configuration.
- **Local Network Sync (Wi-Fi)**: Bidirectionally sync database journal entries and screenshot files between devices (PC-to-PC, PC-to-Android, or Android-to-Android) on the same local Wi-Fi/LAN network securely.
- **Market News and RSS**: View external market news and feeds directly inside the application.
- **Auto-Update**: Receive automatic updates for standalone desktop releases directly from GitHub.

## How to Use

1. **Launch the Application**: Run the executable file (RizkO.exe on Windows, the corresponding binary on Linux, or install the APK on Android).
2. **Configure Settings**: Set your preferred base currency, import/export options, and configure other preferences.
3. **Manage Accounts**: Create one or more trading accounts by specifying the initial balance and currency.
4. **Record Trades**: 
   - Add entries manually using the Trading Journal form, or
   - Bulk-import trades using the Excel Import tool by mapping your Excel columns to the application's fields.
5. **Analyze Performance**: Open the Dashboard, Journal List, or Calculators to monitor your trading metrics, growth, and overall performance.

---

## System Requirements

### Desktop (Windows & Linux)
- **Operating System**:
  - Windows: Windows 10 (Build 19041 or higher) / Windows 11
  - Linux: Ubuntu 20.04+, Debian 10+, Fedora 32+ (with glibc 2.27+)
- **Processor**: Intel/AMD dual-core 1.6 GHz or faster
- **Memory (RAM)**: 2 GB minimum (4 GB or higher recommended)
- **Storage**: 100 MB of free disk space (SQLite database size varies depending on trade logs and screenshot attachments)
- **Graphics**: Direct3D 11 / OpenGL 3.0 / Vulkan compatible GPU for hardware UI rendering
- **Software Runtime**: .NET 10.0 Runtime (included in self-contained builds)
- **Network**: Active Wi-Fi/LAN network adapter for local syncing

### Mobile (Android)
- **Operating System**: Android 5.0 (Lollipop, API level 21) or higher
- **Memory (RAM)**: 1 GB minimum (2 GB recommended)
- **Storage**: 50 MB of free storage space
- **Network**: Active Wi-Fi or portable Hotspot/Tethering for syncing

---

## Local Wi-Fi Sync Guide

RizkO's local Wi-Fi sync feature allows you to copy and merge your trading database and screenshot files between devices on the same local network without using any third-party cloud servers.

### Prerequisites
1. Both devices must be connected to the **same network** (Wi-Fi, LAN, or portable Hotspot/Tethering).
2. If hosting on a Windows PC, ensure that **Windows Defender Firewall** allows incoming traffic on port `18346`. Run the following command in PowerShell as Administrator to open the port:
   ```powershell
   New-NetFirewallRule -DisplayName "RizkO Local Sync" -Direction Inbound -Action Allow -Protocol TCP -LocalPort 18346
   ```

### Step-by-Step Sync Instructions:

#### Step 1: Set up the Host (Server)
- On the device that will act as the host server (e.g. your PC), navigate to the **Sync** page from the sidebar menu.
- Select the **Host Server** role.
- (Optional) Configure the Device Name and Port in the settings card.
- Click **Start Host**. The server status will change to *Running* (Green) and show the local IP address and a dynamic 6-digit **Pairing PIN**.

#### Step 2: Connect the Client
- On the second device (e.g. your Android phone), navigate to the **Sync** page.
- Select the **Connect (Client)** role.
- Click **Scan** to automatically discover hosts on the network, or manually input the Host IP address shown on the Host screen.
- Enter the 6-digit **Pairing PIN** displayed on the host.
- Click **Connect & Sync**.

#### Step 3: Subsequent Syncs (Trusted Devices)
- Once successfully paired, the device will be added to the **Trusted Devices** list.
- For future syncs, you don't need to re-enter a PIN. Simply start the host, select the device under Discovered Hosts or Trusted Devices on the Client, and click **Connect & Sync**.
