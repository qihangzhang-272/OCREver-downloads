# OCREver 下载

这里提供 OCREver 的公开安装包和使用说明，无需申请私有仓库权限。

**本仓库仅用于分发安装包，不包含 OCREver 项目源码。公开下载不代表重新授权软件或随包模型；各组件保留原有许可。**

## 当前版本

- **Windows 2026.11.18**：[自定义服务更新](https://github.com/qihangzhang-272/OCREver-downloads/releases/tag/v2026.11.18-provider-setup)，可从服务商获取模型列表并测试启用。
- **Mac 2026.11.18**：[自定义服务更新](https://github.com/qihangzhang-272/OCREver-downloads/releases/tag/v2026.11.18-provider-macos)，支持 M 系列和 macOS 14.5 及以上。

## Windows 64 位

请下载以下 **三个文件**，放在同一个文件夹，不要改名：

| 文件 | 下载 |
| --- | --- |
| OCREver-Windows-x64-20261118.zip.001 | [分卷 1](https://github.com/qihangzhang-272/OCREver-downloads/releases/download/v2026.11.18-provider-setup/OCREver-Windows-x64-20261118.zip.001) |
| OCREver-Windows-x64-20261118.zip.002 | [分卷 2](https://github.com/qihangzhang-272/OCREver-downloads/releases/download/v2026.11.18-provider-setup/OCREver-Windows-x64-20261118.zip.002) |
| Merge-Windows.cmd | [合并工具](https://github.com/qihangzhang-272/OCREver-downloads/releases/download/v2026.11.18-provider-setup/Merge-Windows.cmd) |

1. 双击 `Merge-Windows.cmd`，等待显示 `SUCCESS`。工具只在本地合并并校验文件。
2. 完整解压生成的 `OCREver-Windows-x64-20261118.zip`。
3. 打开解压后的 `ocrever-gui.exe`，不要删除同级的 `resources`，也不要只复制 EXE。

完整 ZIP 约 **3.6 GiB**，建议预留至少 **20 GB** 空间。Windows 界面需要 Microsoft Edge WebView2 运行时。

## Mac M 系列

**仅支持 Apple Silicon（M 系列）和 macOS 14.5 及以上，不支持 Intel Mac 或 macOS 14.0 至 14.4。**

请下载以下 **四个文件**，放在同一个文件夹，不要改名：

| 文件 | 下载 |
| --- | --- |
| OCREver-arm64.dmg.001 | [分卷 1](https://github.com/qihangzhang-272/OCREver-downloads/releases/download/v2026.11.18-provider-macos/OCREver-arm64.dmg.001) |
| OCREver-arm64.dmg.002 | [分卷 2](https://github.com/qihangzhang-272/OCREver-downloads/releases/download/v2026.11.18-provider-macos/OCREver-arm64.dmg.002) |
| OCREver-arm64.dmg.003 | [分卷 3](https://github.com/qihangzhang-272/OCREver-downloads/releases/download/v2026.11.18-provider-macos/OCREver-arm64.dmg.003) |
| OCREver-arm64.dmg.004 | [分卷 4](https://github.com/qihangzhang-272/OCREver-downloads/releases/download/v2026.11.18-provider-macos/OCREver-arm64.dmg.004) |

在分卷所在文件夹打开终端，合并前先确认没有需要保留的同名 DMG：

```sh
cat OCREver-arm64.dmg.001 OCREver-arm64.dmg.002 OCREver-arm64.dmg.003 OCREver-arm64.dmg.004 > OCREver-arm64.dmg
shasum -a 256 OCREver-arm64.dmg
```

对照 [Mac 发布页](https://github.com/qihangzhang-272/OCREver-downloads/releases/tag/v2026.11.18-provider-macos) 上的 SHA256，一致后打开 DMG，将应用拖入 `Applications`。本包未经过 Apple 公证。遇到系统验证提示请联系交付方。

## 更新前先备份

退出旧版，备份整个个人数据文件夹，并保留原 PDF、图片和完整 OCR 输出目录：

- Windows：`%APPDATA%\ocrever`
- Mac：`~/Library/Application Support/ocrever`

Windows 新版解压到新目录，不与旧版文件混放。确认书架、单页识别、校对保存和导出正常后，再停用旧版。

## 使用提醒

- Windows 有两个分卷，Mac 有四个。请下载对应系统的全部分卷，不要只打开 `.001`。
- 不要下载页面底部的 `Source code (zip)` 或 `Source code (tar.gz)`，它们不是应用包。
- 安装包含本地模型与运行环境，无需另装 Python。本地正文 OCR 无需平台 API Token；外部 AI 识别、摘要、翻译或复核需要可用的 API Token。
- CPU 运行大模型可能需要数分钟。复杂版面仍可能出现错字、漏字或顺序问题，需要人工校对。
- Windows 合并工具会校验新版 ZIP；Mac 的校验值见对应发布页。[旧版下载](https://github.com/qihangzhang-272/OCREver-downloads/releases/tag/v2026.11.12-local-models-qa2)仍可使用。

GitHub 要求单个 Release 文件小于 2 GiB，因此本版采用分卷下载。[GitHub 发布文件说明](https://docs.github.com/en/repositories/releasing-projects-on-github/about-releases#storage-and-bandwidth-quotas)
