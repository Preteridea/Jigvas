# JIGVAS

JIGVAS 是一款面向 macOS 的采集画布应用：把图片、文字与文件汇集到一张画布上，自由整理、排版并导出。

## 获取

- 官网：https://www.jigvas.com
- 当前版本：**0.3.3**（build 19，2026-11-15，安全修复 + Developer ID 签名公证版）
- 安装包：[JIGVAS-0.3.3-20261115.dmg](downloads/JIGVAS-0.3.3-20261115.dmg)
- 校验文件：[SHA256SUMS.txt](downloads/SHA256SUMS.txt)
- SHA-256：`0d570c5fedea7f0fc140e11422c7bb8b3b2d0c83d59cdd2430ce04937d74686d`

下载后在 `downloads/` 目录执行 `shasum -a 256 -c SHA256SUMS.txt` 校验完整性。

## 0.3.3 安全修复

- 授权码改为 Ed25519 非对称签名票据，由 App 原生层校验签名、设备指纹与有效期；客户端不再包含任何可用于签发授权码的材料。
- 发布包不再包含授权码生成器、调试接口与试用次数重置入口。
- 启动时校验核心资源完整性，被改动将拒绝加载。
- 本版本已用 Developer ID Application 证书签名，通过 Apple 公证并 staple 票据；Gatekeeper 判定为 accepted。签名与票据让「改内核后重签绕过完整性校验」不再可行。
- **0.3.2 及更早版本已作废**：旧授权码在 0.3.3 中全部失效，请改用本版本。仓库历史中仍存有已作废的旧包，请勿下载使用。

## 安装

打开 DMG，把 `JIGVAS` 拖入「应用程序」；也可下载官网提供的 ZIP 直接解压运行。

本版本已通过 Apple **Developer ID 签名 + 公证 + staple**，Gatekeeper 判定为 accepted。首次打开时 macOS 只会提示一次「这是从互联网下载的 App，确定要打开吗？」，点「打开」即可；**不需要**去「系统设置 → 隐私与安全性」放行，也不需要执行 `xattr -dr com.apple.quarantine`。后续启动不再提示。

> 说明：macOS 15 Sequoia 起「右键 → 打开」的旧办法已失效，但已公证版本不受影响。

## 关于本仓库

这里只保存对外发布物（安装包、校验和、发布说明），不托管开发仓库。开发源码、授权签发私钥与 Ji 角色资产均不在此仓库。

## 环境与反馈

- 平台：macOS，Apple Silicon
- 反馈：hello@jigvas.com
