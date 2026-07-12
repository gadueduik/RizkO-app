# RizkO - Frequently Asked Questions (FAQ)

This FAQ provides answers to common questions about using RizkO, for both Desktop (Windows, macOS, Linux) and Mobile (Android) versions.

## Table of Contents
1. [General Questions](#1-general-questions)
   - [Q1.1: What is RizkO?](#q11-what-is-rizko)
   - [Q1.2: What platforms does RizkO support?](#q12-what-platforms-does-rizko-support)
   - [Q1.3: Is RizkO free to use?](#q13-is-rizko-free-to-use)
   - [Q1.4: Is this app suitable for all exchanges and all types/categories of trading?](#q14-is-this-app-suitable-for-all-exchanges-and-all-typescategories-of-trading)
2. [Data, Privacy & Storage](#2-data-privacy--storage)
   - [Q2.1: Where is my trading journal data stored? Is it uploaded to a server?](#q21-where-is-my-trading-journal-data-stored-is-it-uploaded-to-a-server)
   - [Q2.2: Where can I find the database files on my device?](#q22-where-can-i-find-the-database-files-on-my-device)
   - [Q2.3: Can I back up or transfer my database to another device?](#q23-can-i-back-up-or-transfer-my-database-to-another-device)
   - [Q2.4: Can I import my trade records from Excel?](#q24-can-i-import-my-trade-records-from-excel)
3. [Wi-Fi Synchronization (Zero-Cloud Sync)](#3-wi-fi-synchronization-zero-cloud-sync)
   - [Q3.1: How does the Wi-Fi Sync feature work?](#q31-how-does-the-wi-fi-sync-feature-work)
   - [Q3.2: Do I need an active internet connection to sync my devices?](#q32-do-i-need-an-active-internet-connection-to-sync-my-devices)
   - [Q3.3: How does the app resolve data conflicts during synchronization?](#q33-how-does-the-app-resolve-data-conflicts-during-synchronization)
   - [Q3.4: Why can't my mobile device discover the desktop host?](#q34-why-cant-my-mobile-device-discover-the-desktop-host)
4. [Crypto News Reader](#4-crypto-news-reader)
   - [Q4.1: Where does the News Reader get its articles?](#q41-where-does-the-news-reader-get-its-articles)
   - [Q4.2: Why do some news items fail to load occasionally?](#q42-why-do-some-news-items-fail-to-load-occasionally)
   - [Q4.3: How does the Relevance Scoring system work?](#q43-how-does-the-relevance-scoring-system-work)
   - [Q4.4: Can I customize my preferred news topics and search keywords?](#q44-can-i-customize-my-preferred-news-topics-and-search-keywords)
5. [TradingView Chart Integration](#5-tradingview-chart-integration)
   - [Q5.1: How do I change the coin symbol or timeframes in the chart?](#q51-how-do-i-change-the-coin-symbol-or-timeframes-in-the-chart)
   - [Q5.2: Why does the chart display a blank page or load indefinitely?](#q52-why-does-the-chart-display-a-blank-page-or-load-indefinitely)
   - [Q5.3: Does the chart theme match my application's appearance?](#q53-does-the-chart-theme-match-my-applications-appearance)
6. [Trading Calculators & Risk Management](#6-trading-calculators--risk-management)
   - [Q6.1: What calculators are available in the side panel?](#q61-what-calculators-are-available-in-the-side-panel)
   - [Q6.2: How does the Position Sizing (Risk) Calculator work?](#q62-how-does-the-position-sizing-risk-calculator-work)
   - [Q6.3: What do the three modes of the Leverage Calculator do?](#q63-what-do-the-three-modes-of-the-leverage-calculator-do)
   - [Q6.4: Can I quickly copy calculator results to paste elsewhere?](#q64-can-i-quickly-copy-calculator-results-to-paste-elsewhere)
7. [Troubleshooting & Support](#7-troubleshooting--support)
   - [Q7.1: The app crashed or is draining resources in the background. How is process lifetime managed?](#q71-the-app-crashed-or-is-draining-resources-in-the-background-how-is-process-lifetime-managed)
   - [Q7.2: Why is the "Donation" button disabled, and how can I support the developers?](#q72-why-is-the-donation-button-disabled-and-how-can-i-support-the-developers)

---

## 1. General Questions

### Q1.1: What is RizkO?
RizkO is a comprehensive, multi-platform trading assistant application built using Avalonia UI. It is designed to help crypto traders manage risk, maintain a structured trading journal, analyze performance, monitor real-time news, and view interactive charts.

### Q1.2: What platforms does RizkO support?
RizkO supports both Desktop and Mobile ecosystems:
*   **Desktop**: Windows 10/11 (64-bit), macOS 11.0 (Big Sur or later), and modern Linux distributions (such as Ubuntu 20.04+, Debian 11+, and Fedora 35+).
*   **Mobile**: Android 10 (Target SDK is Android 15/API Level 36, with minimum support down to Android 6.0/API Level 23) supporting `arm64-v8a` (physical devices) and `x86_64` (emulators) architectures.

### Q1.3: Is RizkO free to use?
Yes, RizkO is free to use. There are no subscriptions, paywalls, or mandatory accounts. You can optionally support the project via donations if you find it valuable.

### Q1.4: Is this app suitable for all exchanges and all types/categories of trading?
No, RizkO is not fully suitable or optimized for all exchanges and all types of trading out-of-the-box:
*   **Exchanges**: As an offline-first journal and calculator tool, RizkO is exchange-agnostic for manual entry or Excel imports. You can add custom exchanges and set default commissions/taxes under settings. However, it **does not support direct API integration or auto-sync** with any exchanges.
*   **Trading Categories**: It is **specifically optimized for Cryptocurrency trading** (especially leveraged spot/futures/perpetual contracts). The built-in tools, such as the position-sizing/leverage calculators, the Crypto News Reader, and the TradingView chart widget (which defaults to Binance Perpetual contracts), are tailored to crypto. While you can log traditional assets like stocks, forex, or options manually, the app does not natively support features like option chain monitoring, stock split management, dividends, or stock broker integrations.

---

## 2. Data, Privacy & Storage

### Q2.1: Where is my trading journal data stored? Is it uploaded to a server?
RizkO is designed with a **Privacy-First & Offline-First** philosophy. All of your journal entries, calculator preferences, news configurations, and application logs are stored locally on your device. Absolutely no data is uploaded to external servers or third-party cloud systems.

### Q2.2: Where can I find the database files on my device?
RizkO uses **LiteDB** (a fast, embedded NoSQL database). The databases are stored in the following locations depending on the platform:
*   **Windows**: `%LocalAppData%\RizkO\` (typically `C:\Users\<YourUsername>\AppData\Local\RizkO\`) containing `RizkO_TradingJournal.db` and `RizkO.db`.
*   **Linux**: `~/.local/share/RizkO/` or standard XDG data directories.
*   **macOS**: `~/Library/Application Support/RizkO/`.
*   **Android**: Inside the application's secure private files directory: `/data/user/0/com.rizko.app/files/`.

### Q2.3: Can I back up or transfer my database to another device?
Yes. Since the database is stored entirely in local files, you can back it up or transfer it by copying the `.db` files (primarily `RizkO_TradingJournal.db`) to a safe location or another device. Make sure to close the application before copying to avoid data corruption.

### Q2.4: Can I import my trade records from Excel?
Yes, RizkO features an Excel Import system that allows you to import historical trading records directly into the LiteDB journal. You can access this via the settings or journal menu on both desktop and mobile layouts.

---

## 3. Wi-Fi Synchronization (Zero-Cloud Sync)

### Q3.1: How does the Wi-Fi Sync feature work?
The **Universal Wi-Fi Sync** allows you to synchronize your trading journal directly between your desktop computer and your mobile phone (Android) over a local network (Wi-Fi or mobile hotspot). It works by setting up one device as a **Host** (which starts a lightweight HTTP server on port 18346 and broadcasts its presence via UDP port 18345) and the other as a **Client**. When you click "Connect & Sync," the devices communicate directly, exchanging only the changed data (delta sync) since the last synchronization.

### Q3.2: Do I need an active internet connection to sync my devices?
No. The synchronization process happens entirely within your local local area network (LAN) or Wi-Fi. As long as both devices are connected to the same Wi-Fi router or hotspot, they can synchronize data offline.

### Q3.3: How does the app resolve data conflicts during synchronization?
RizkO handles conflicts through two main strategies:
1.  **Data Fields**: Uses a **Last-Write-Wins (LWW)** strategy based on UTC timestamps (`LastModifiedAt`). The device with the newest edit will overwrite the older entry.
2.  **Screenshots & Images**: If both devices have different image attachments for the same trade entry, the receiving device will backup its local image with a timestamp suffix (e.g., `_backup_yyyyMMdd_HHmmss`) before applying the new image, preventing accidental data loss.

### Q3.4: Why can't my mobile device discover the desktop host?
This is usually caused by network isolation or firewall settings. Try the following:
*   Ensure both devices are connected to the exact same Wi-Fi network/hotspot.
*   Check if your router has "AP Isolation" or "Client Isolation" enabled, which prevents local devices from talking to each other.
*   On Windows, make sure you allow RizkO through the Windows Defender Firewall for both Private and Public networks.
*   If UDP broadcasting fails, you can manually type the Host's IP address and Port in the client app.

---

## 4. Crypto News Reader

### Q4.1: Where does the News Reader get its articles?
The News Reader aggregates real-time RSS feeds from various cryptocurrency news sites (such as CoinDesk, CoinTelegraph, and others). The fetched news is stored in a local database cache (`RizkO_Articles.db`) for up to 7 days, allowing for instant keyword search and offline reading.

### Q4.2: Why do some news items fail to load occasionally?
To protect against rate-limiting and bot-protection systems (like Cloudflare) implemented by news websites, RizkO uses an anti-rate limiting engine that applies random delays and automatic retries. If a site is temporarily inaccessible or blocking requests, the feed reader will wait and retry. Intermittent internet disconnections can also cause temporary load failures.

### Q4.3: How does the Relevance Scoring system work?
When you search for articles using keywords, the search engine scores each article based on keyword frequency, title matches, and recency. This helps prioritize the most relevant news at the top of your feed.

### Q4.4: Can I customize my preferred news topics and search keywords?
Yes. You can navigate to **Settings -> News Topics (Intents)** to add new custom keywords, delete existing ones, or reorder topics. You can also customize your startup default search topic and pages-per-load settings.

---

## 5. TradingView Chart Integration

### Q5.1: How do I change the coin symbol or timeframes in the chart?
The TradingView widget is fully interactive. By default, it loads the perpetual contract `BINANCE:BTCUSDT.P`. You can click on the symbol in the top-left corner of the chart widget to type and search for any other coin (e.g., ETHUSDT, SOLUSDT, or traditional equities). Timeframes (1m, 5m, 1h, 1D) and technical indicators can be customized directly using the TradingView top toolbar.

### Q5.2: Why does the chart display a blank page or load indefinitely?
The TradingView widget is rendered inside an embedded browser WebView. This requires:
*   An active internet connection.
*   **Desktop**: The Microsoft WebView2 runtime must be installed on Windows. It is pre-installed on Windows 11, but on older Windows 10 machines, you might need to install it manually.
*   **Android**: The system's "Android System WebView" app must be updated to the latest version via the Google Play Store.

### Q5.3: Does the chart theme match my application's appearance?
Yes, RizkO features dynamic theme synchronization. When you switch the application's appearance between Light Mode and Dark Mode in the settings, the TradingView chart widget will reload and match the corresponding background, gridline, and scale colors.

---

## 6. Trading Calculators & Risk Management

### Q6.1: What calculators are available in the side panel?
The side panel provides an interactive calculator suite designed to prepare you before placing trades on your exchange:
*   **PnL Calculator**: Estimate gross/net profit and loss, commissions, and ROI.
*   **Target TP Calculator**: Calculate target exit prices based on your entry price, leverage, and desired PnL target (in USD or %).
*   **Risk Management Calculator**: Determine your maximum position size and token quantity based on account balance, risk percentage, and Stop Loss distance.
*   **Leverage Calculator**: Calculate needed leverage, required margin, or max quantity.
*   **Commission Calculator**: Estimate fees based on maker/taker rates.
*   **Comparison Calculator**: Compare Long vs. Short trades side-by-side.

### Q6.2: How does the Position Sizing (Risk) Calculator work?
It calculates the exact amount of capital you should allocate to a trade. You enter your Total Capital, the percentage of capital you are willing to risk (e.g., 1% or 2%), your Entry Price, and your Stop Loss Price. The calculator output tells you:
*   The maximum USD amount you stand to lose (Risk Amount).
*   The maximum nominal position size (with leverage) allowed.
*   The maximum quantity of the crypto asset to buy or sell.

### Q6.3: What do the three modes of the Leverage Calculator do?
*   **Leverage Result**: Determines the leverage multiplier required to open a specific position size with your available margin (rounds up to the nearest whole integer).
*   **Required Margin**: Tells you the minimum capital you must allocate to meet the position size at a given leverage.
*   **Maximum Quantity**: Calculates the maximum asset amount you can trade given your margin and leverage.

### Q6.4: Can I quickly copy calculator results to paste elsewhere?
Yes. Each key output (Target TP and Leverage) has a dedicated copy button. It copies the clean numerical value (without units like "x" or "USD") so you can paste it directly into your exchange's trading terminal.

---

## 7. Troubleshooting & Support

### Q7.1: The app crashed or is draining resources in the background. How is process lifetime managed?
The latest version of RizkO (v1.0.4) implements a robust clean shutdown process to prevent socket locking and memory leaks.
*   **On Desktop**: Closing the main window completely kills all backend threads immediately. If you encounter issues, ensure you are running v1.0.4.
*   **On Android**: If you experience background lag, close the app from the recents screen. The app is programmed to perform a native process termination (`KillProcess`) on close to prevent background battery/memory drain.

### Q7.2: Why is the "Donation" button disabled, and how can I support the developers?
The donation button is temporarily disabled via a configuration flag in `MainMenu.axaml.cs` (`IsDonationEnabled = false`) for developmental and testing safety. Once activated in future updates, it will display public addresses for USDT (BEP-20, TRC-20, ERC-20) and links to local Indonesian payment options (Saweria, Trakteer) or PayPal. For now, you can support the developers by submitting bug reports and feedback.
