# SENTINEL MIN · Dist

本仓库只放**发布产物**，不放源码。源码在 https://github.com/65tiankehan/SENTINEL-Min 。

## 命名约定

- 资产文件名随机（`sm-<hash8>.exe`），避免被按名字直接抓取；
- 每个 Release 附 `sha256`，下载后务必校验；
- tag 与版本一致：`min-0.1.0`、`min-0.1.1` …

## 当前版本

| 版本 | 状态 | 说明 |
| --- | --- | --- |
| 0.1.9 | **当前** | 修保镖生成在 4.1.6 上的解析（新增 `IBotGame`/`LocalGame` 路径）+ `auto-spawn` 失败重试 8 次 + 失败提示 8 秒 + 安装器 BigBrain 检测改递归（消除"装了却说没装"误报） | 玩家页新增「贵重物品」（比特币 / 显卡 / 劳力士 / LEDX，各 0~3 件）+ 医疗·贵重共用发放引擎；修 `_resolving` 未复位导致贵重一件发不出；顶栏居中三段式、面板默认右上角、页脚不再被压住 |
| 0.1.8 | 已被 0.1.9 取代 | 玩家页新增贵重物品四样，但模板解析有 bug，实际发不出来 |
| 0.1.0 | 首个可测版 | 三页签面板（保镖/玩家/维修）+ 保镖生成/集结/解散 + 六样医疗发放 + 原版维修附魔与耐久补满 + 安装器 |

## 资产

| 文件 | 大小 | sha256 |
| --- | --- | --- |
| `sm-a6ea78ec.exe`（0.1.9） | 3,075,072 B（2.93 MB） | `a6ea78ec6cbc8acb1e29c2fdcb7628abf17b4c8f981080fea4bc473afc122208` |
| `sm-e18d4f9f.exe`（0.1.0） | 3,065,856 B（2.92 MB） | `e18d4f9ffd15d85c1fab4af9cd4e553031d5d43309c7655cda2b7e6b9ffd40dd` |

下载地址（Release `min-0.1.9`，id `447061174`，已上传 `sm-a6ea78ec.exe`，2026-11-16 21:1x 发布）：

- 直连：`https://github.com/65tiankehan/SENTINEL-Min-Dist/releases/download/min-0.1.9/sm-a6ea78ec.exe`
- 镜像：`https://gh-proxy.com/https://github.com/65tiankehan/SENTINEL-Min-Dist/releases/download/min-0.1.9/sm-a6ea78ec.exe`

历史（Release `min-0.1.0`，id `445323103`）：`sm-e18d4f9f.exe`，直连 25 s 内无响应（GitHub CDN 抖动），镜像 `200` 且长度完全一致。国内建议直接给镜像地址。

安装器行为：

1. 双击运行，三页引导（装过一次会自动跳过）；
2. 自动探测 `E:\EFT` → `D:\EFT` → `C:\EFT` → `E:\SPT` → `D:\SPT`，也可手动换目录；
3. 一个按钮装完客户端面板与服务端模组，写 `HKCU\...\Uninstall\SENTINEL MIN`；
4. 卸载走挽留页，`BepInEx\config\SENTINEL-Min.json` 保留，重装读回原开关。

## 校验示例

```powershell
Get-FileHash .\sm-a6ea78ec.exe -Algorithm SHA256
# 应为 A6EA78EC6CBC8ACB1E29C2FDCB7628ABF17B4C8F981080FEA4BC473AFC122208
```

## 已发布记录

| 版本 | Release | id | 资产 | 复核 |
| --- | --- | --- | --- | --- |
| 0.1.9 | `min-0.1.9` | `447061174` | `sm-a6ea78ec.exe` 3,075,072 B | 直连 `200` + `content-length` 一致；镜像 `gh-proxy.com` 亦 `200` 同长度；GitHub 侧 `digest=sha256:a6ea78ec…122208` 与本机哈希一致 |
| 0.1.0 | `min-0.1.0` | `445323103` | `sm-e18d4f9f.exe` 3,065,856 B | 直连曾 25 s 无响应（CDN 抖动），镜像 `200` 且长度一致 |