# SENTINEL MIN · Dist

本仓库只放**发布产物**，不放源码。源码在 https://github.com/65tiankehan/SENTINEL-Min 。

## 命名约定

- 资产文件名随机（`sm-<hash8>.exe`），避免被按名字直接抓取；
- 每个 Release 附 `sha256`，下载后务必校验；
- tag 与版本一致：`min-0.1.0`、`min-0.1.1` …

## 当前版本

| 版本 | 状态 | 说明 |
| --- | --- | --- |
| 0.1.0 | 首个可测版 | 三页签面板（保镖/玩家/维修）+ 保镖生成/集结/解散 + 六样医疗发放 + 原版维修附魔与耐久补满 + 安装器 |

## 资产

| 文件 | 大小 | sha256 |
| --- | --- | --- |
| `sm-32ec1f37.exe` | 3,064,832 B（2.92 MB） | `32ec1f3789fb9164ac402621ba37237f5e27618964d42211df263fa8521e6062` |

下载地址（Release `min-0.1.0`，id `445323103`）：

- 直连：`https://github.com/65tiankehan/SENTINEL-Min-Dist/releases/download/min-0.1.0/sm-32ec1f37.exe`
- 镜像：`https://gh-proxy.com/https://github.com/65tiankehan/SENTINEL-Min-Dist/releases/download/min-0.1.0/sm-32ec1f37.exe`

> 本机实测：直连 25 s 内无响应（GitHub CDN 抖动），镜像 `200` 且长度 3,064,832 B 完全一致。国内建议直接给镜像地址。

安装器行为：

1. 双击运行，三页引导（装过一次会自动跳过）；
2. 自动探测 `E:\EFT` → `D:\EFT` → `C:\EFT` → `E:\SPT` → `D:\SPT`，也可手动换目录；
3. 一个按钮装完客户端面板与服务端模组，写 `HKCU\...\Uninstall\SENTINEL MIN`；
4. 卸载走挽留页，`BepInEx\config\SENTINEL-Min.json` 保留，重装读回原开关。

## 校验示例

```powershell
Get-FileHash .\sm-32ec1f37.exe -Algorithm SHA256
# 应为 32EC1F3789FB9164AC402621BA37237F5E27618964D42211DF263FA8521E6062
```
