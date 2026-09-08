<div align="center">
  <img src="docs/icon.png" alt="番茄钟图标" width="128" />

# 番茄钟

**简体中文 macOS 菜单栏番茄钟**

轻量、原生、无需 Electron · Swift + WebKit · MIT 许可证

</div>

## 简介

番茄钟常驻在 macOS 菜单栏，实时显示专注或休息的剩余时间。左键点按 🍅 图标可打开计时器，右键点按可调整时长和提醒设置。

这是 [onurdilmen/pomodoro-menubar](https://github.com/onurdilmen/pomodoro-menubar) 的简体中文定制版。主界面、右键菜单、通知、语音提醒和首次启动提示均已汉化。

## 功能

- 🍅 菜单栏实时倒计时，例如 `🍅 24:57`
- ⏱️ 专注、短休息、长休息三种模式；时长可自定义
- 🔁 专注结束后自动开始休息；每完成 4 个专注，自动开始长休息
- ⌨️ 全局快捷键 `⌘⇧P`：显示或隐藏计时器
- 🔔 系统提示音、中文语音提醒和 macOS 通知，可分别开关
- 🚀 支持登录时自动启动
- 💾 时长与提醒设置会保存在本机，重启后仍然有效
- 🌑 深色界面，原生 Swift 外壳，资源占用小

## 安装

### 下载已构建版本

1. 前往本仓库的 [Releases](../../releases) 页面，下载最新的 `Pomodoro-*.dmg`。
2. 打开 DMG，将 `Pomodoro.app` 拖入“应用程序”文件夹。
3. 首次打开若被 macOS 拦截：前往“系统设置 → 隐私与安全性”，在安全性提示旁选择“仍要打开”。
4. 在菜单栏找到 `🍅 25:00`：左键打开计时器，右键打开设置。

> 本项目为个人开源构建，未使用 Apple 开发者证书公证；首次启动出现系统安全提示是正常现象。

### 从源码构建

需要 macOS 13 或更高版本，以及 Xcode Command Line Tools。

```bash
git clone git@github.com:Ewentsang/pomodoro-menubar.git
cd pomodoro-menubar
./package.sh --install
```

常用命令：

```bash
./package.sh            # 构建 Pomodoro.app
./package.sh --install  # 构建、安装到 /Applications 并启动
./package.sh --dmg      # 构建 DMG 安装包
```

## 使用方法

| 操作 | 方法 |
| --- | --- |
| 打开或关闭计时器面板 | 左键点按菜单栏图标，或按 `⌘⇧P` |
| 开始 / 暂停 | 点按按钮，或在面板内按 `Space` |
| 重置当前计时 | 点按“重置”，或在面板内按 `R` |
| 切换专注与休息模式 | 点按面板顶部的模式标签 |
| 调整时长、提醒与自动启动 | 右键点按菜单栏图标 |

默认时长为：专注 25 分钟、短休息 5 分钟、长休息 15 分钟。

自动流程为：专注结束后立即开始短休息；第 4、8、12……个专注结束后立即开始长休息；任何一次休息结束后都会自动开始下一轮专注。

## 发布新版本

推送形如 `v1.0.0` 的标签后，GitHub Actions 会自动构建 DMG 并创建 Release：

```bash
git tag -a v1.0.0 -m "发布 v1.0.0"
git push origin v1.0.0
```

为避免中文版本被上游版本覆盖，本 Fork 不启用上游的自动更新功能；请从本仓库的 Releases 页面获取新版本。

## 开源许可与致谢

本项目遵循 [MIT License](LICENSE)。原项目由 [Onur Dilmen](https://github.com/onurdilmen) 创建；本 Fork 在保留原始版权与许可证的前提下，提供简体中文界面与发布流程。
