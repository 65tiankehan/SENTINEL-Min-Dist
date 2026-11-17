# SENTINEL MIN · Dist

本仓库只放**发布产物**，不放源码。

## 命名约定

- 资产文件名随机（`sm-<hash8>.exe`），避免被按名字直接抓取；
- 每个 Release 附 `sha256`，下载后务必校验；
- tag 与版本一致：`min-0.1.0`、`min-0.1.1` …

## 当前版本

| 版本 | 状态 | 说明 |
| --- | --- | --- |
| 0.1.15 | **当前** | 修「面板点不动」：滚动区命中坐标修正 + 开关整行可点；修「生成保镖失败」：别人家 mod 在 bot 创建回调里抛异常不再截断我们的兜底；修日志把自动 tick 记成手动按下；面板只画 Repaint 一趟 + 新增 `[perf]` 帧耗时；新增兼容台账 `compat-latest.txt`（插件清单 / 热点补丁冲突 / 干扰事件） | 全部继承 0.1.12：生成链路 `PreActive → Active` 修复、进度百分比、600 帧等待 |
| 0.1.12 | 已被 0.1.15 取代 | 修「生成保镖」最后一步卡住（`PreActive → Active`）：补 `WeaponManager.Selector.TakeMainWeapon()` 兜底、等待窗口 300→600 帧；资源加载时显示进度百分比，不再报「请求被拒」 | 全部继承 0.1.9：贵重物品四样 + 发放引擎 + 顶栏/右上角/页脚修复 |
| 0.1.9 | 已被 0.1.15 取代 | 修保镖生成在 4.1.6 上的解析（新增 `IBotGame`/`LocalGame` 路径）+ `auto-spawn` 失败重试 8 次 + 失败提示 8 秒 + 安装器 BigBrain 检测改递归（消除"装了却说没装"误报）；但生成最后一步仍可能卡在 `bot_not_active` | 玩家页新增「贵重物品」四样 + 医疗·贵重共用发放引擎；修 `_resolving` 未复位；顶栏居中、默认右上角、页脚不再被压住 |
| 0.1.8 | 已被 0.1.15 取代 | 玩家页新增贵重物品四样，但模板解析有 bug，实际发不出来 |

## 资产

| 文件 | 大小 | sha256 |
| --- | --- | --- |
| `sm-b3af5665.exe`（0.1.15） | 3,082,240 B（2.94 MB） | `b3af5665dd17f0dc85618d6bc3148f98cb12931a5c2a64fee67b96fe8104f918` |
| `sm-ef3bcd9e.exe`（0.1.12） | 3,076,096 B（2.93 MB） | `ef3bcd9e7d861e4bbc49c51c209e7dfc190a4aab08a9394fda0c481ec82bbb7b` |
| `sm-e18d4f9f.exe`（0.1.0） | 3,065,856 B（2.92 MB） | `e18d4f9ffd15d85c1fab4af9cd4e553031d5d43309c7655cda2b7e6b9ffd40dd` |

下载地址（Release `min-0.1.15`，id `447239347`，已上传 `sm-b3af5665.exe`，2026-11-16 23:40 发布）：

- 直连：`https://github.com/65tiankehan/SENTINEL-Min-Dist/releases/download/min-0.1.15/sm-b3af5665.exe`
- 镜像：`https://gh-proxy.com/https://github.com/65tiankehan/SENTINEL-Min-Dist/releases/download/min-0.1.15/sm-b3af5665.exe`

历史（Release `min-0.1.0`，id `445323103`）：`sm-e18d4f9f.exe`，直连 25 s 内无响应（GitHub CDN 抖动），镜像 `200` 且长度完全一致。国内建议直接给镜像地址。

安装器行为：

1. 双击运行，三页引导（装过一次会自动跳过）；
2. 自动探测 `E:\EFT` → `D:\EFT` → `C:\EFT` → `E:\SPT` → `D:\SPT`，也可手动换目录；
3. 一个按钮装完客户端面板与服务端模组，写 `HKCU\...\Uninstall\SENTINEL MIN`；
4. 卸载走挽留页，`BepInEx\config\SENTINEL-Min.json` 保留，重装读回原开关。

## 校验示例

```powershell
Get-FileHash .\sm-b3af5665.exe -Algorithm SHA256
# 应为 B3AF5665DD17F0DC85618D6BC3148F98CB12931A5C2A64FEE67B96FE8104F918
```

## 已发布记录

| 版本 | Release | id | 资产 | 复核 |
| --- | --- | --- | --- | --- |
| 0.1.15 | `min-0.1.15` | `447239347` | `sm-b3af5665.exe` 3,082,240 B | GitHub 侧 `digest=sha256:b3af5665…f918` 与本机哈希一致；镜像 `gh-proxy.com` `200` 且长度 3,082,240 |
| 0.1.12 | `min-0.1.12` | `447154484` | `sm-ef3bcd9e.exe` 3,076,096 B | GitHub 侧 `digest=sha256:ef3bcd9e…bb7b` 与本机哈希一致；镜像 `gh-proxy.com` `200` 且长度 3,076,096 |
| 0.1.9 | `min-0.1.9` | `447061174` | `sm-74530800.exe` 3,075,072 B | 首次上传 `sm-a6ea78ec.exe` 因安装器版本号写死 0.1.0 已撤换为 `sm-74530800.exe` |
| 0.1.0 | `min-0.1.0` | `445323103` | `sm-e18d4f9f.exe` 3,065,856 B | 直连曾 25 s 无响应（CDN 抖动），镜像 `200` 且长度一致 |
