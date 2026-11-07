# A-me Course Helper

<p align="center">
  <strong>A browser userscript designed for online learning platforms used by the School of Foreign Studies.</strong>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Version-8.2-blue.svg" />
  <img src="https://img.shields.io/badge/Platform-Web-green.svg" />
  <img src="https://img.shields.io/badge/Language-JavaScript-yellow.svg" />
  <img src="https://img.shields.io/badge/License-MIT-orange.svg" />
</p>

[简体中文](README.md) | [English](README_EN.md)

## 📖 Introduction

**A-me Course Helper** is a JavaScript-based browser userscript designed to improve the video playback experience on online learning platforms used by the School of Foreign Studies.

By monitoring video playback states, detecting CAPTCHA dialogs, and identifying course chapters, the script provides features such as video status monitoring, automatic playback attempts, chapter completion notifications, and randomized chapter navigation delays.

The project is lightweight and requires no additional server or database. Simply install a userscript manager to get started.

## ✨ Features

- **Video Status Monitoring**: Monitors video playback, pause, buffering, and completion states in real time.
- **Automatic Playback Attempts**: Attempts to start video playback using the browser's playback API when the video is ready.
- **Status Panel**: Displays the assistant's current status in a floating panel at the bottom-right corner of the webpage.
- **CAPTCHA Detection**: Detects CAPTCHA dialogs on course pages and provides countdown notifications.
- **Chapter Detection**: Automatically identifies the current chapter and the next available chapter.
- **Randomized Chapter Navigation**: Waits for a random period of 2–6 seconds after a video ends before navigating to the next chapter.
- **Randomized Countdown**: Generates a random 5–10 second countdown after a CAPTCHA dialog appears, then attempts to click the relevant button. (For automatic CAPTCHA filling, Mieru-OCR is required. It is available in the Microsoft Edge Add-ons store.)
- **Error Handling**: Handles video changes, playback failures, and timer-related issues.
- **Lightweight Operation**: Uses periodic checks to avoid excessive DOM scanning and unnecessary resource consumption.

## 🖥️ Requirements

| Item | Requirement |
|---|---|
| Browser | Chrome / Microsoft Edge and other Chromium-based browsers |
| Userscript Manager | Tampermonkey |
| Scripting Language | JavaScript |
| Target Platforms | Duxing and Chaoxian online course platforms |
| Execution Environment | Runs locally in the browser |

## 📦 Installation

### 1. Install Tampermonkey

Install Tampermonkey for your browser:

- [Google Chrome Extension](https://chromewebstore.google.com/detail/tampermonkey/dhdgffkkebhmkfjojejmpbldmpobfkfo)
- [Microsoft Edge Add-ons](https://microsoftedge.microsoft.com/addons/)

### 2. Create a Userscript

1. Open Tampermonkey in your browser.
2. Go to the Dashboard.
3. Click **Create a new script**.
4. Copy the provided JavaScript source code into the editor.
5. Save and enable the script.

### 3. Open the Course Platform

Visit one of the following platforms:

- https://swxy.duxingkej.com/
- https://swxy.chaoxoanxingkeji.com/

Once you enter a course page, the assistant will initialize automatically.

## ⚙️ Configuration

The script provides several configurable options near the top of the source code:

```javascript
const VIDEO_SELECTOR = '#videoContent video';
const CAPTCHA_SELECTOR = '#video-captcha';

const CHAPTER_SELECTOR =
    '.detmain-navlist a[href*="/user/node?nodeId="]';

const CHECK_INTERVAL = 1000;

const CAPTCHA_MIN_DELAY = 5000;
const CAPTCHA_MAX_DELAY = 10000;

const AUTO_NEXT_MIN_DELAY = 2000;
const AUTO_NEXT_MAX_DELAY = 6000;
```

| Configuration | Default Value | Description |
|---|---:|---|
| `CHECK_INTERVAL` | 1000ms | Interval between page checks |
| `CAPTCHA_MIN_DELAY` | 5000ms | Minimum CAPTCHA countdown duration |
| `CAPTCHA_MAX_DELAY` | 10000ms | Maximum CAPTCHA countdown duration |
| `AUTO_NEXT_MIN_DELAY` | 2000ms | Minimum delay before navigating to the next chapter |
| `AUTO_NEXT_MAX_DELAY` | 6000ms | Maximum delay before navigating to the next chapter |

You can modify these values according to your needs.

## 📂 Project Structure

```text
a-me-Course-Helper/
│
├── a-me.user.js       # Main userscript
├── README.md          # Chinese documentation
├── README_EN.md       # English documentation
└── LICENSE            # Open-source license
```

## 📝 Changelog

### v8.2

- Added randomized chapter navigation delays.
- Added a random 2–6 second delay after chapter completion.
- Added a randomized 5–10 second CAPTCHA countdown notification.
- Improved timer management.
- Improved status panel notifications.
- Updated version identifiers.

### v8.0

- Refactored video status monitoring.
- Added CAPTCHA dialog detection.
- Added a floating playback status panel.
- Added next-chapter detection.
- Added automatic chapter navigation after video completion.
- Improved automatic playback error handling.

## ⚠️ Disclaimer

1. This project is intended solely for JavaScript learning, browser userscript development, and personal research.
2. Users must comply with the terms of service and applicable rules of the target course platforms.
3. This project does not provide CAPTCHA cracking or bypass functionality. Users must complete CAPTCHA verification themselves.
4. This project is not officially affiliated with, endorsed by, or associated with the target course platforms or their operators.
5. Users are solely responsible for any consequences arising from the use of this project.
6. Do not use this project to disrupt normal platform operations, interfere with other users, or circumvent platform security mechanisms.

## 📄 License

This project is licensed under the **MIT License**.

You are free to use, modify, and distribute this project, provided that the original copyright notice and license file are retained.

---

<p align="center">
  Made with ❤️ by A-me
</p>
