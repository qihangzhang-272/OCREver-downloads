# OCREver 下载

这里提供 OCREver 的公开安装包和使用说明，无需申请私有仓库权限。

**本仓库仅用于分发安装包，不包含 OCREver 项目源码。公开下载不代表重新授权软件或随包模型；各组件保留原有许可。**

## 当前版本

**2026.11.12 本地模型版**：新增 SongPanda2.1、LightOnOCR-2-1B，改进版式分割，并提供书架检索、校对保存及导出。

- [打开本版完整下载页](https://github.com/qihangzhang-272/OCREver-downloads/releases/tag/v2026.11.12-local-models-qa2)
- [下载图文更新指南 PDF](https://github.com/qihangzhang-272/OCREver-downloads/releases/download/v2026.11.12-local-models-qa2/OCREver-Download-Update-Guide.pdf)

## Windows 64 位

请下载以下 **五个文件**，放在同一个文件夹，不要改名：

| 文件 | 下载 |
| --- | --- |
| OCREver-windows-amd64-portable.zip.001 | [分卷 1](https://github.com/qihangzhang-272/OCREver-downloads/releases/download/v2026.11.12-local-models-qa2/OCREver-windows-amd64-portable.zip.001) |
| OCREver-windows-amd64-portable.zip.002 | [分卷 2](https://github.com/qihangzhang-272/OCREver-downloads/releases/download/v2026.11.12-local-models-qa2/OCREver-windows-amd64-portable.zip.002) |
| OCREver-windows-amd64-portable.zip.003 | [分卷 3](https://github.com/qihangzhang-272/OCREver-downloads/releases/download/v2026.11.12-local-models-qa2/OCREver-windows-amd64-portable.zip.003) |
| OCREver-windows-amd64-portable.zip.004 | [分卷 4](https://github.com/qihangzhang-272/OCREver-downloads/releases/download/v2026.11.12-local-models-qa2/OCREver-windows-amd64-portable.zip.004) |
| Merge-Windows.cmd | [合并工具](https://github.com/qihangzhang-272/OCREver-downloads/releases/download/v2026.11.12-local-models-qa2/Merge-Windows.cmd) |

1. 双击 `Merge-Windows.cmd`，等待显示 `SUCCESS`。工具只在本地合并并校验文件。
2. 完整解压生成的 `OCREver-Windows-x64-20261112.zip`。
3. 打开解压后的 `ocrever-gui.exe`，不要删除同级的 `resources`，也不要只复制 EXE。

完整 ZIP 约 **3.83 GB**，建议预留至少 **20 GB** 空间。Windows 界面需要 Microsoft Edge WebView2 运行时。

## Mac M 系列

**仅支持 Apple Silicon（M 系列）和 macOS 14.5 及以上，不支持 Intel Mac 或 macOS 14.0 至 14.4。**

请下载以下 **四个文件**，放在同一个文件夹，不要改名：

| 文件 | 下载 |
| --- | --- |
| OCREver-arm64.dmg.001 | [分卷 1](https://github.com/qihangzhang-272/OCREver-downloads/releases/download/v2026.11.12-local-models-qa2/OCREver-arm64.dmg.001) |
| OCREver-arm64.dmg.002 | [分卷 2](https://github.com/qihangzhang-272/OCREver-downloads/releases/download/v2026.11.12-local-models-qa2/OCREver-arm64.dmg.002) |
| OCREver-arm64.dmg.003 | [分卷 3](https://github.com/qihangzhang-272/OCREver-downloads/releases/download/v2026.11.12-local-models-qa2/OCREver-arm64.dmg.003) |
| OCREver-arm64.dmg.004 | [分卷 4](https://github.com/qihangzhang-272/OCREver-downloads/releases/download/v2026.11.12-local-models-qa2/OCREver-arm64.dmg.004) |

在分卷所在文件夹打开终端，合并前先确认没有需要保留的同名 DMG：

```sh
cat OCREver-arm64.dmg.001 OCREver-arm64.dmg.002 OCREver-arm64.dmg.003 OCREver-arm64.dmg.004 > OCREver-arm64.dmg
shasum -a 256 OCREver-arm64.dmg
```

完整 DMG 约 **3.96 GB**。SHA256 应为：

```text
1f97307f1bc7a777d8ea6defb93752008fbd290f9256ce9b433386fbfc794095
```

一致后打开 DMG，将应用拖入 `Applications`。本包尚未经过 Apple Developer ID 公证，也未完成 macOS 14.5 实机窗口验收；已完成 CI 包内模型推理与最低系统版本检查。遇到系统验证提示请联系交付方，不要关闭系统安全保护。

## 更新前先备份

退出旧版，备份整个个人数据文件夹，并保留原 PDF、图片和完整 OCR 输出目录：

- Windows：`%APPDATA%\ocrever`
- Mac：`~/Library/Application Support/ocrever`

Windows 新版解压到新目录，不与旧版文件混放。确认书架、单页识别、校对保存和导出正常后，再停用旧版。完整步骤见上方图文指南。

## 使用提醒

- 四个分卷是同一个包的四部分，必须全部下载。不要把单个 `.001` 当作完整软件打开。
- 不要下载页面底部的 `Source code (zip)` 或 `Source code (tar.gz)`，它们不是应用包。
- 安装包含本地模型与运行环境，无需另装 Python。本地正文 OCR 无需平台 API Token；外部 AI 识别、摘要、翻译或复核需要可用的 API Token。
- CPU 运行大模型可能需要数分钟。复杂版面仍可能出现错字、漏字或顺序问题，需要人工校对。
- [完整包 SHA256](https://github.com/qihangzhang-272/OCREver-downloads/releases/download/v2026.11.12-local-models-qa2/SHA256.txt)

GitHub 要求单个 Release 文件小于 2 GiB，因此本版采用分卷下载。[GitHub 发布文件说明](https://docs.github.com/en/repositories/releasing-projects-on-github/about-releases#storage-and-bandwidth-quotas)
