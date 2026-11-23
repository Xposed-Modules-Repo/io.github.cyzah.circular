# Circular

Circular 是使用 Kotlin 开发的 LSPosed 状态栏图标模块，用于自定义状态栏与下拉界面的图标样式。模块提供三合一图标、双卡排列、实时预览和细节设置。

## 功能

- 自定义电量、Wi-Fi、移动信号与网络制式文字的图标比例和粗细。
- 选择双卡信号样式：双层信号、四点分组、双卡胶囊或 DUO。
- 调整电量数字、图标内容位置，以及充电、低电量、省电和性能状态颜色。
- 在预览中调整展开动画，并模拟电量、充电、Wi-Fi、双卡等状态。
- 按 ROM 能力配置下拉显示、锁屏和息屏显示。
- 查看模块诊断信息；可选导出 SystemUI 适配包或重启 SystemUI。

## 安装与启用

1. 安装所选渠道的已签名 Circular APK。普通版在 GitHub Releases 发布，包名是 `com.cyzah.circular`。LSPosed 仓库版的包名是 `io.github.cyzah.circular`。
2. 在 LSPosed 中启用 Circular。模块作用域限定为 `com.android.systemui`。
3. 重启设备，或打开应用重启系统界面。普通版的入口在「工具」，LSPosed 仓库版的入口在「关于」。
4. 打开 Circular 设置页，在“预览”和“外观”中调整显示效果。

如果启用后遇到 SystemUI 显示异常，请先在 LSPosed 中停用模块并重启设备。重启系统界面需要 Root 授权。普通版还提供复制诊断和导出适配包，导出同样需要 Root 授权。两版可以同时安装，启用时请选择其中一版作用于 SystemUI。

## 兼容性

- 最低 Android 版本为 Android 15（API 35）；模块声明使用 LSPosed API 102。
- 实际效果取决于厂商、Android 版本和 SystemUI 实现。模块设置中的适配说明指出，三星、一加和 OPPO 的息屏显示使用系统原生图标；小米保留已适配的展开与息屏功能。独立的息屏状态栏样式不在当前适配范围内。
- 项目不承诺支持其他机型，目前不受理新增机型适配请求。请以目标设备上的实际表现为准。

## 诊断与隐私

普通版的诊断信息可能包含设备信息和模块运行状态，请在分享前检查内容。导出适配包会复制选定的 SystemUI 相关 APK，不会修改系统文件。

## 开发

两版共用 `app/src/main/` 的 Hook、设置和界面代码。普通版专属功能位于 `app/src/github/`，仓库版专属页面位于 `app/src/lspRepo/`。界面使用 Compose 和 Miuix Glass。

- [构建指南](构建指南.md)
- [测试指南](测试指南.md)
- [第三方声明](NOTICE.md)

Circular 由 Cy2ah 开发和维护。

## 参考与致谢

Circular 最初由 lu_aiden 开发的「三合一状态图标」二次修改而来。经过 Cy2ah 多次更新、重构和改版，现已发展为独立的 Circular 项目。感谢 lu_aiden 大佬提供最初的项目基础。

主题设置参考了开源项目 InstallerX Revived。 [项目仓库](https://github.com/wxxsfxyzm/InstallerX-Revived)
