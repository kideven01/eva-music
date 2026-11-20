# Eva 音乐

基于开源项目 [MusicFree](https://github.com/maotoumao/MusicFree) 二次开发的安卓音乐播放器，把界面整体重做为「汽水音乐」式的暗色沉浸风格，并改名为 **Eva 音乐**。

- 包名：`fun.eva.music`（可与原版 MusicFree 共存安装）
- 版本：0.6.2-eva（React Native 0.76.5）
- 最低系统：Android 7.0（API 24）
- 许可：AGPL-3.0（沿用上游协议）

## 下载安装

在 [Releases](../../releases) 页面下载最新构建的 `app-universal-release.apk`（或 `app-arm64-v8a-release.apk`），传到手机点击安装即可。

> 安装包使用工程内置的 debug 证书签名，仅用于个人侧载安装；如需上架应用商店，请自行配置正式 keystore。

## 构建方式

本仓库通过 GitHub Actions 构建：工作流下载源码归档 → `npm install` → Gradle `assembleRelease` → 上传 APK 并附到 Release。

- 手动触发：Actions → `Build Eva Music APK` → Run workflow，可传入自定义源码地址。
- 本地构建：`npm install --legacy-peer-deps`，然后 `cd android && ./gradlew assembleRelease`。

## 界面改版要点

- 设计令牌 `src/constants/designTokens.ts`：圆角 8/12/18/24/32/999rpx、间距 6~64rpx、字阶 display 44 / headline 38。
- 暗色主题：页面 `#0A0A0C`、卡片 `#141418`、面板 `#191920`、强调色青柠 `#D9FF54`。
- 首页：发现导航 + 「今日精选」大图 hero + 横向胶囊入口 + 双列封面歌单墙 + 悬浮迷你播放栏。
- 播放页：封面模糊铺底 + 四段暗场渐变 + 560rpx 圆角封面 + 青柠主控与滑杆。
- 歌单详情：色晕头部 + 230rpx 封面 + 曲目胶囊 + 青柠「播放全部」。
- 已关闭上游 MusicFree 的更新检查，避免提示下载原版。

## 源码

AGPL-3.0 要求分发二进制时提供完整对应源码，因此构建用的源码归档同时作为 Release 附件（`Eva-music-source.zip`）提供。

## 致谢与声明

界面改造与二次开发基于 MusicFree（作者 猫头猫）。原项目版权与 AGPL-3.0 协议保持不变，二次分发请保留出处：https://github.com/maotoumao/MusicFree
