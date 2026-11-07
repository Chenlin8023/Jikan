<p align="center">
  <img src="Resources/Banner.png" alt="Jikan 充电估算的经典胶囊与进度环两种样式" width="100%" />
</p>

<h1 align="center">Jikan</h1>

<p align="center">
  <img alt="Version" src="https://img.shields.io/badge/version-1.2.1-0a84ff?style=for-the-badge" />
  <img alt="Platform" src="https://img.shields.io/badge/platform-iOS%2014.0%E2%80%9326.0.1-111111?style=for-the-badge" />
  <a href="LICENSE"><img alt="License" src="https://img.shields.io/badge/license-GPLv3-blue?style=for-the-badge" /></a>
  <img alt="Language" src="https://img.shields.io/badge/language-Objective--C%20%26%20Logos-2b2b2b?style=for-the-badge" />
  <a href="https://havoc.app/package/jikan"><img src="https://img.shields.io/badge/available_on-Havoc-1757FF?style=for-the-badge" alt="Available on Havoc" /></a>
</p>

> 本仓库为 [waruhachi/Jikan](https://github.com/waruhachi/Jikan) 的 fork，说明文档翻译自英文原版，如有歧义以原文为准。

## 关于

Jikan 在你的锁定屏幕上显示充电时间估算。设定想要达到的电量百分比，即可查看还剩多少时间。你可以选择一个可点击查看更多电池读数的胶囊，或者日期旁的紧凑估算。

## 胶囊或日期行

经典胶囊（Classic）在显示剩余时间的同时带有充电指示。进度环（Progress Ring）在显示估算时间的同时，以环形进度展示你距离所选目标的进度。两种样式都可以在设置中预览。

在 iOS 16 或更高版本上，**改用日期行（Use Date Row Instead）**会在日期旁显示诸如「距 80% 还有 27 分钟」的估算。它也可以与现有的内联小组件共存。

## 充电估算

Apple 算法是初始默认项，并在 Jikan 确认实测输入可用后成为推荐选项。实测输入持续不可用的设备会自动改用 Jikan 算法；即使读数暂时缺失，此前已确认的 Apple 推荐仍会保留。你也可以自行选择任一算法。现有的预估功率警告只在实测输入被确认不可用后才会显示。Apple 模式使用基于 Apple iOS 26 估算器重建的充电模型，目标支持 80%、85%、90%、95% 和 100%。

Jikan 算法利用设备的充电历史与当前电池读数，支持 1% 到 100% 的任意整数百分比。

两种算法都在设备上本地计算。目标只是 Jikan 估算所指向的百分比，并不会改变手机的实际充电上限。

阅读 [Jikan 如何估算充电时间](docs/charging-estimates.md)，其中包含两种算法的细节以及 Apple 模式背后的逆向工程。

## 搭建你的读数栈

「预计时间」始终包含在内，并跟随设置中的主目标。你还可以为其他充电目标、功率、电池温度或电池电压添加估算，并按自己喜好的顺序排列这些可选读数。点击胶囊即可依次切换。

当所显示的估算达到其目标后，胶囊会自动进入下一个未完成的更高目标。其他读数保持所选状态，已完成的目标在手动切换时依然可选。只要仍有更高的未完成目标，胶囊就会保持显示。日期行估算和目标通知则继续跟随主目标。

## 外观与位置

- 在设置中开启或关闭 Jikan，更改立即生效。
- 在锁定屏幕预览中直接拖动胶囊，或使用滑块调整位置。竖屏与横屏位置分别保存。
- 调整位置时可锁定水平或垂直方向的移动。
- 调整背景不透明度，在受支持的系统上呈现液态玻璃（Liquid Glass）效果。
- 在设置中按系统的浅色或深色外观预览胶囊样式。
- 使用系统温度单位，或自行选择摄氏度 / 华氏度。
- 充电速度较慢时显示黄色充电指示。
- 达到所选百分比后，保持显示已充满状态。
- 隐藏锁屏快捷操作按钮：可始终隐藏，或仅在充电时隐藏。
- 隐藏可能与胶囊重叠的专注模式与通知计数文字：可始终隐藏，或仅在充电时隐藏。
- 隐藏滑动解锁文字：可始终隐藏，或仅在充电时隐藏。

## 与 ChargeLimiter 联动

如果你使用 [ChargeLimiter](https://havoc.app/package/chargelimiter)，请在该插件中设置充电上限，然后在 Jikan 中点击**与 ChargeLimiter 同步**。Jikan 会将该上限导入为估算目标，百分比只需输入一次。

每次修改上限后请重新点击同步。若上限不在 Apple 预设范围内，请选择 Jikan 算法。

## 本地化与开源

Jikan 内置英语、德语、瑞典语、土耳其语和越南语。翻译工作在 [Crowdin](https://crowdin.com/project/jikan) 上进行，你可以在那里改进现有翻译或申请新语言，无需使用 Git。

Jikan 基于 [GNU GPLv3 许可证](LICENSE)开源。你可以浏览代码、贡献改进，或[提交 issue](https://github.com/waruhachi/Jikan/issues)。

## 支持开发

如果你想支持我和 Jikan 的开发，可以在 [Havoc](https://havoc.app/package/jikan) 上购买。**付费版与免费版的功能与表现完全一致，不存在任何付费专属功能。**

## 截图

<p align="center">
  <img src="Resources/LockScreen.png" alt="锁定屏幕上的充电估算：胶囊样式或日期旁样式" width="49%" />
  <img src="Resources/Pill.png" alt="Jikan 胶囊样式与胶囊样式偏好设置" width="49%" />
</p>

<p align="center">
  <img src="Resources/Battery.png" alt="实时电池功率、温度与电压" width="49%" />
  <img src="Resources/Position.png" alt="竖屏与横屏的胶囊位置及位置偏好设置" width="49%" />
</p>
