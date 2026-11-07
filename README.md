# A-me的网课助手(不懂的地方自己去网上搜索)

<p align="center">
  <strong>一款面向涉外学院网课平台的浏览器用户脚本</strong>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Version-8.2-blue.svg" />
  <img src="https://img.shields.io/badge/Platform-Web-green.svg" />
  <img src="https://img.shields.io/badge/Language-JavaScript-yellow.svg" />
  <img src="https://img.shields.io/badge/License-MIT-orange.svg" />
</p>

[简体中文](README.md) | [English](README_EN.md)

## 📖 项目简介

**A-me的网课助手** 是一个基于 JavaScript 编写的浏览器用户脚本，主要用于优化涉外学院在线课程的播放体验。

项目通过监听页面视频状态、检测验证码弹窗以及识别课程章节，实现视频状态监测、自动播放尝试、章节结束提醒和随机延迟章节切换等功能。

本项目采用轻量化设计，无需额外服务器或数据库，安装用户脚本管理器即可使用。

## ✨ 功能特性

- **视频状态监测**：实时监测视频播放、暂停、缓冲及结束状态。
- **自动播放尝试**：视频准备就绪后尝试调用浏览器播放接口。
- **播放状态面板**：在网页右下角显示助手运行状态。
- **验证码检测**：自动识别课程页面中的验证码弹窗，并提供倒计时提示。
- **章节识别**：自动获取当前章节及下一章节信息。
- **随机延迟切换**：视频结束后随机等待 2～6 秒，再切换到下一章节。
- **随机倒计时**：验证码出现后随机生成 5～10 秒倒计时，然后随机点击按钮（注意自动填充验证码需要搭配Mieru-OCR，可以在EDGE扩展商店中找到）。
- **异常处理**：针对视频切换、播放失败和计时器重复等情况进行处理。
- **轻量化运行**：采用定时检测机制，避免高频 DOM 扫描。

## 🖥️ 运行环境

| 项目 | 要求 |
|---|---|
| 浏览器 | Chrome / Edge 等 Chromium 浏览器 |
| 脚本管理器 | Tampermonkey（篡改猴） |
| 脚本语言 | JavaScript |
| 目标平台 | 读行和超贤课程平台 |
| 运行方式 | 浏览器本地运行 |

## 📦 安装方法

### 1. 安装 Tampermonkey

根据浏览器类型安装 Tampermonkey：

- [Chrome 扩展](https://chromewebstore.google.com/detail/tampermonkey/dhdgffkkebhmkfjojejmpbldmpobfkfo)
- [Microsoft Edge 扩展](https://microsoftedge.microsoft.com/addons/)

### 2. 创建用户脚本

1. 打开浏览器中的 Tampermonkey。
2. 进入管理面板。
3. 点击创建新脚本。
4. 将项目提供的 JavaScript 源码复制进去。
5. 保存并启用脚本。

### 3. 打开课程平台

访问：

https://swxy.duxingkej.com/
https://swxy.chaoxoanxingkeji.com/

进入课程页面后，助手将自动初始化。

## ⚙️ 配置说明

脚本顶部提供了常用配置项：

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

| 配置项 | 默认值 | 说明 |
|---|---:|---|
| CHECK_INTERVAL | 1000ms | 页面检测间隔 |
| CAPTCHA_MIN_DELAY | 5000ms | 验证码倒计时最短时间 |
| CAPTCHA_MAX_DELAY | 10000ms | 验证码倒计时最长时间 |
| AUTO_NEXT_MIN_DELAY | 2000ms | 下一章节最短等待时间 |
| AUTO_NEXT_MAX_DELAY | 6000ms | 下一章节最长等待时间 |

## 📂 项目结构

```text
a-me-Course-Helper/
│
├── a-me.user.js     # 用户脚本主程序
├── README.md          # 项目说明文档
└── LICENSE            # 开源许可证
```

## 📝 更新日志

### v8.2

- 新增随机章节切换等待时间。
- 章节结束后随机等待 2～6 秒。
- 新增验证码 5～10 秒随机倒计时提示。
- 优化计时器管理。
- 优化状态面板提示。
- 调整版本标识。

### v8.0

- 重构视频状态检测逻辑。
- 新增验证码弹窗识别。
- 新增播放状态面板。
- 新增下一章节识别。
- 新增视频结束后的自动章节跳转。
- 优化自动播放异常处理。

## ⚠️ 免责声明

1. 本项目仅供 JavaScript 学习、浏览器脚本开发及个人研究使用。
2. 使用者应遵守目标课程平台的用户协议及相关规定。
3. 本项目不提供验证码破解或绕过功能，验证码需要用户自行完成。
4. 本项目与目标课程平台及其运营方不存在官方合作关系。
5. 使用本项目产生的任何后果由使用者自行承担。
6. 请勿将本项目用于破坏平台正常运行、干扰其他用户或规避平台安全机制的行为。

## 📄 License

本项目采用 MIT License 开源协议。

你可以自由使用、修改和分发本项目，但请保留原作者版权声明及许可证文件。

---

<p align="center">
  Made with ❤️ by A-me
</p>
