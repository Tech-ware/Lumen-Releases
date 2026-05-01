<div align="center">
  <img src="https://github.com/user-attachments/assets/d4e7cc71-26c9-4679-af67-de7297dcc2d7" alt="Lumen Logo" width="512">


  # Lumen by HX
  **The local, ML-powered search engine your PC deserves.**

  [![Version](https://img.shields.io/badge/Version-1.3.0-00E5FF.svg?style=flat-square)](#installation)
  [![Platform](https://img.shields.io/badge/Platform-Windows%2010%20%7C%2011-blue.svg?style=flat-square)](#installation)
  [![Website](https://img.shields.io/badge/Website-tools.archx.ma-white.svg?style=flat-square)](https://tools.archx.ma/lumen)
</div>

<br>

Windows Search is fundamentally broken. It relies on high-level APIs, prioritizes web results, and struggles to index heavy directories. 

**Lumen** is a native C# WinUI 3 replacement engineered for speed and context. It bypasses the operating system to read the raw NTFS Master File Table (MFT) directly, and utilizes local Machine Learning models (ONNX Runtime) to search your images and documents by semantic meaning. 

Zero cloud telemetry. Zero lag. 100% on-device inference.

## Architecture & Features

* **Raw MFT Parsing:** Bypasses Win32 APIs to read raw disk sectors. Indexes 2,000,000+ files in under 5 seconds for 0ms keyword search latency.
* **Multimodal Local AI:** Runs quantized `all-MiniLM` and `CLIP` neural networks entirely on your CPU. Type `? a modern sports car` and Lumen mathematically connects your thought to the visual pixels inside your local `.jpg` and `.png` files.
* **In-Document Deep Search:** Utilizes a SQLite `FTS5` Virtual Table to build an inverted index of your PDFs, Word documents, and text files. Find the exact document a sentence is written in instantly.
* **Dual-Process IPC Design:** Overcomes Windows UIPI security restrictions. An invisible Admin service handles the heavy I/O and neural networks, communicating via Asynchronous Named Pipes to a lightweight, standard-user UI. This allows for flawless **zero-friction drag-and-drop** directly to your desktop.
* **Memory Optimized:** Employs Windows Working Set Trimming. Idles invisibly in the background at ~18MB of RAM, reserving memory allocation strictly for active Neural Network inference.

## Installation
<div align="center">
<img width="768" alt="1_3_Update" src="https://github.com/user-attachments/assets/4548ce3d-557d-44a6-ac0d-86a3ecc90896" />


**[Download Lumen v1.3.0 Setup.exe](https://github.com/Tech-ware/Lumen-Releases/releases/download/1.3.0/Lumen_v1.3.0_Setup.exe)**

</div>

### Security Notice (Read Before Installing)
To achieve sub-second indexing, Lumen **requires Administrator privileges** to read the raw Master File Table. 

Because Lumen is built by an independent developer, this `.exe` does not currently possess a $200 EV Code Signing Certificate. When you launch the installer, Windows SmartScreen will flag it as an *"Unknown Publisher"*. 
*   **To proceed:** Click **More Info** -> **Run Anyway**.
*   **Verification:** You are encouraged to run the binary through VirusTotal or monitor it with a network packet sniffer (Wireshark/GlassWire). Lumen makes **0 outbound network requests**. Your data never leaves your silicon.

## Usage Guide

Once installed, Lumen boots silently into your Windows System Tray. 

*   **Summon Lumen:** Press `Alt + Space` (Customizable in Settings).
*   **Keyword Search:** Just start typing. Lumen will instantly search file names across all mounted volumes.
*   **Semantic AI Search:** Prefix your search with a question mark (`?`). 
    *   *Example:* `? architectural blueprints`
    *   Lumen will analyze the semantic meaning of your query against your local index and return relevant Images and Documents, sorted by AI Confidence scoring.
*   **Smart Filters:** Click the UI chips below the search bar to instantly filter millions of results down to `Images`, `Documents`, `Videos`, etc.
*   **Context Menus:** Right-click any result to invoke the native Windows Properties dialog, copy the file, or open its directory.

## Privacy Policy

Lumen is an offline-first application. It does not contain telemetry tracking, crash reporting analytics (unless explicitly opted-in via Sentry), or external API keys. Vector embeddings and FTS5 data are stored locally in an encrypted format at `%LocalAppData%\LumenByHX\LumenBrain.db`.

## Links & Roadmap

*   **Official Website:**[tools.archx.ma/lumen](https://tools.archx.ma/lumen)
*   **Creator:** [@hx](https://x.com/hxthedev)

*Lumen Next (Pro Features including Local OCR, Semantic Video Search, and Network Drive indexing) are currently in development.*
