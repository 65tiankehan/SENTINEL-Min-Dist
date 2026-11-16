# SENTINEL MIN · Dist

本仓库只放**发布产物**，不放源码。源码在 https://github.com/65tiankehan/SENTINEL-Min 。

## 命名约定

- 资产文件名随机（`sm-<hash8>.exe`），避免被按名字直接抓取；
- 每个 Release 附 `sha256`，下载后务必校验；
- tag 与版本一致：`min-0.1.0`、`min-0.1.1` …

## 当前版本

| 版本 | 状态 | 说明 |
| --- | --- | --- |
| 0.1.8 | **当前** | 玩家页新增「贵重物品」（比特币 / 显卡 / 劳力士 / LEDX，各 0~3 件）+ 医疗·贵重共用发放引擎；修 `_resolving` 未复位导致贵重一件发不出；顶栏居中三段式、面板默认右上角、页脚不再被压住 |
| 0.1.7 | 已被 0.1.8 取代 | 玩家页新增贵重物品四样，但模板解析有 bug，实际发不出来 |
| 0.1.0 | 首个可测版 | 三页签面板（保镖/玩家/维修）+ 保镖生成/集结/解散 + 六样医疗发放 + 原版维修附魔与耐久补满 + 安装器 |

## 资产

| 文件 | 大小 | sha256 |
| --- | --- | --- |
| `sm-3e12fc5c.exe`（0.1.8） | 3,073,536 B（2.93 MB） | `3e12fc5ca3c249c47d29030371ec1e9dbe8057c3b827fbc920bec830cb13cd0b` |
| `sm-e18d4f9f.exe`（0.1.0） | 3,064,832 B（2.92 MB） | `e18d4f9ffd15d85c1fab4af9cd4e553031d5d43309c7655cda2b7e6b9ffd40dd` |

下载地址（Release `min-0.1.8`，需先在 GitHub 建 release 并上传 `sm-3e12fc5c.exe`）：

- 直连：`https://github.com/65tiankehan/SENTINEL-Min-Dist/releases/download/min-0.1.8/sm-3e12fc5c.exe`
- 镜像：`https://gh-proxy.com/https://github.com/65tiankehan/SENTINEL-Min-Dist/releases/download/min-0.1.8/sm-3e12fc5c.exe`

历史（Release `min-0.1.0`，id `445323103`）：`sm-e18d4f9f.exe`，直连 25 s 内无响应（GitHub CDN 抖动），镜像 `200` 且长度完全一致。国内建议直接给镜像地址。

安装器行为：

1. 双击运行，三页引导（装过一次会自动跳过）；
2. 自动探测 `E:\EFT` → `D:\EFT` → `C:\EFT` → `E:\SPT` → `D:\SPT`，也可手动换目录；
3. 一个按钮装完客户端面板与服务端模组，写 `HKCU\...\Uninstall\SENTINEL MIN`；
4. 卸载走挽留页，`BepInEx\config\SENTINEL-Min.json` 保留，重装读回原开关。

## 校验示例

```powershell
Get-FileHash .\sm-3e12fc5c.exe -Algorithm SHA256
# 应为 3E12FC5CA3C249C47D29030371EC1E9DBE8057C3B827FBC920BEC830CB13CD0B
```
