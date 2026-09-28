# Office 功能组件 · Office Runtime

Documents、Presentations、Spreadsheets 共用一个 Office 组件。安装一次即可启用原生排版预览与受支持的编辑操作。

One shared component provides native-layout previews and supported editing operations for Documents, Presentations and Spreadsheets.

## 安装 · Install

1. 使用带有 Office 工作台的 Artemis 客户端，打开任一 Office 插件。
2. 点击“升级 Office 功能”→“在线安装”。三个插件会共享本次安装。
3. 安装后点击“管理 Office 配置”可检查更新或卸载；有新版本时会显示更新按钮。

离线使用时，从 [macOS arm64 · Office Runtime 1.0.0](https://github.com/EurekaRaider/ArtemisRelease/releases/tag/office-runtime-v1.0.0) 或 [Windows x64 · Office Runtime 1.0.1](https://github.com/EurekaRaider/ArtemisRelease/releases/tag/office-runtime-v1.0.1) 下载对应平台的 `.artemis-office` 文件并在客户端导入，无需解压或选择 JSON。已安装时，“离线更新 / 修复”收起在管理面板下方。

In an Office-enabled Artemis client, open an Office plugin and choose **Upgrade Office features → Install online**. After installation, **Manage Office configuration** provides update checks and removal. For offline use, download the matching macOS arm64 (1.0.0) or Windows x64 (1.0.1) release and import its `.artemis-office` asset without extracting it; offline maintenance is available in the installed component’s management panel.

## 支持范围 · Support

- 当前公开组件：macOS arm64 / Apple Silicon 1.0.0，以及 Windows x64 1.0.1。
- 使用 Artemis v1.6.9 或更新版本，客户端需包含 Office 工作台及对应平台的可信发布目录。
- 增强编辑受宿主支持策略约束；原生引擎覆盖原文件保持禁用。完整复杂格式保真尚未宣称通过。
- 卸载恢复 Lite 并释放组件空间，保留用户文档。

Published runtimes are **1.0.0 for macOS arm64 / Apple Silicon** and **1.0.1 for Windows x64**. Use Artemis v1.6.9 or later with the Office workbench and the trusted catalog for your platform. Native overwrite of originals remains disabled, and full complex-format fidelity is not claimed. Uninstalling restores Lite and preserves user documents.

## 发布源 · Release source

- [macOS arm64 · 1.0.0 / Assets and release notes](https://github.com/EurekaRaider/ArtemisRelease/releases/tag/office-runtime-v1.0.0)
- [Windows x64 · 1.0.1 / Assets and release notes](https://github.com/EurekaRaider/ArtemisRelease/releases/tag/office-runtime-v1.0.1)
- [安装及更新目录 / Installation and update catalog](https://raw.githubusercontent.com/EurekaRaider/ArtemisRelease/main/office-runtime/catalog.json)

组件由宿主验证 Ed25519 清单签名、下载摘要、逐文件摘要及平台原生信任。公共目录不能为客户端添加可信密钥。主程序 CD 只读验证已有的固定版本资产。

The host verifies Ed25519 manifest signatures, archive and file hashes, and platform-native trust. The public feed cannot add trusted client keys. Main application builds reuse and verify the immutable runtime assets.
