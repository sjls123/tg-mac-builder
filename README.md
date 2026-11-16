# Telegram macOS build pipeline

构建 Telegram for macOS 的可运行 `.app`，源码锁定在指定 commit，本地改动通过 `LOCAL_PATCH` secret 注入。

## 用法

Actions → Build Telegram macOS → Run workflow

产物：该次运行的 Artifacts → `Telegram-macOS-app`

## 说明

- runner：`macos-26`（自带 Xcode 26.x / macOS 26 SDK，源码依赖 `NSGlassEffectView`）
- 源码：`TelegramMessenger/telegram-macos`，checkout 到 `eedc9639`
- 改动：由仓库 secret `LOCAL_PATCH` 提供，不落在仓库里
- 产物：ad-hoc 签名，`xattr -cr` 后可直接打开
