<div align="center">
  <img width="1920" height="1080" alt="1_5_Update" src="https://github.com/user-attachments/assets/a6a51340-56a6-4e74-adc2-a16bf8be518f" />



  # Lumen by HX
  **The local search engine your PC deserves.**

  [![Version](https://img.shields.io/badge/Version-1.5.0-00E5FF.svg?style=flat-square)](#installation)
  [![Platform](https://img.shields.io/badge/Platform-Windows%2010%20%7C%2011-blue.svg?style=flat-square)](#installation)
  [![Website](https://img.shields.io/badge/Website-tools.archx.ma-white.svg?style=flat-square)](https://tools.archx.ma/lumen)
</div>

<br>

Windows Search is fundamentally broken. It relies on high-level APIs, prioritizes web results, and struggles to index heavy directories. 

**Lumen** is a native C# WinUI 3 engineered for speed and context. It reads the raw NTFS Master File Table (MFT) directly and uses FTS5 to index data inside documents.

## Architecture & Features

* **Raw MFT Parsing:** Bypasses Win32 APIs to read raw disk sectors. Indexes millions of files in seconds for sub millisecond keyword search speed.
* **In-Document Deep Search:** Utilizes a SQLite `FTS5` Virtual Table to build an inverted index of your PDFs, Word documents, and text files. Find the exact document a sentence is written in instantly.
* **Dual-Process IPC Design:** Overcomes Windows UIPI security restrictions. An invisible Admin service handles the heavy I/O, communicating via Asynchronous Named Pipes to a lightweight, standard-user UI. This allows for flawless **zero-friction drag-and-drop** directly to your desktop.
* **Memory Optimized:** Employs Windows Working Set Trimming. Idles invisibly in the background.

## Installation
<div align="center">


**[Download Lumen v1.5.0 Setup.exe](https://github.com/Tech-ware/Lumen-Releases/releases/download/1.5.0/Lumen_v1.5.0_Setup.exe)**

</div>

### Security Notice (Read Before Installing)
To achieve sub-second indexing, Lumen **requires Administrator privileges** to read the raw Master File Table. 

Because Lumen is built by an independent developer, this `.exe` does not currently possess a $200 EV Code Signing Certificate. When you launch the installer, Windows SmartScreen will flag it as an *"Unknown Publisher"*. 
*   **To proceed:** Click **More Info** -> **Run Anyway**.
*   **Verification:** You are encouraged to run the binary through VirusTotal or monitor it with a network packet sniffer (Wireshark/GlassWire). Lumen makes **0 outbound network requests**. It's offline, no network requests are made.

## Usage Guide

Once installed, Lumen boots silently into your Windows System Tray. 

*   **Summon Lumen:** Press `Alt + Space` (Customizable in Preferences).
*   **Keyword Search:** Just start typing. Lumen will instantly search file names across all mounted volumes.
*   **Smart Filters:** Click the UI chips below the search bar to instantly filter millions of results down to `Images`, `Documents`, `Videos`, etc.
*   **Context Menus:** Right-click any result to invoke the native Windows Properties dialog, copy the file, or open its directory.

## Privacy Policy

Lumen is an offline-first application. It does not contain telemetry tracking, crash reporting analytics, or external API keys.

## Links & Roadmap

*   **Official Website:**[tools.archx.ma/lumen](https://tools.archx.ma/lumen)
*   **Creator:** [@hx](https://x.com/hxthedev)
