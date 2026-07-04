## SCRC
Android 调度类模块

## 注意事项

- 本模块暂时仅支持骁龙8gen3
- 本模块共包含两个部分，oplus云控注入 以及 二改Scene调度
- oplus云控注入为游戏相关配置

**关于二改Scene调度：**
- 若需使用二改Scene调度，则必须安装 Scene9（root模式）
- 二改Scene调度包含两个版本，oplus专用版及通用版
- 不支持盗版（破解版）Scene
- oplus专用版仅支持OPPO及其子品牌的设备
- oplus专用版不包含Scene调度游戏配置，仅包含日常使用配置
- oplus专用版可与一加风驰游戏内核兼容
- 通用版理论上支持所有设备
- 请在Scene中开启 “性能调节” 按钮以生效

**关于oplus云控注入：**
- oplus云控注入仅支持OPPO及其子品牌的设备
- 仅支持ColorOS系统（含realmeUI）
- 同时要求设备支持scx调速器
- 不建议使用第三方内核
- 不建议刷入其余任何额外的第三方调度/限频类模块
- 不建议使用任何游戏相关的第三方线程模块
- 请勿在Scene中自行切换CPU调速器
- 请确保各个系统组件运行正常

## oplus云控注入适配列表
- 异环
- 站双帕弥什
- 鸣潮（官服/B服/国际服）
- 崩坏：星穹铁道
- 原神
- 绝区零
- 阴阳师
- PUBG Mobile
- 金铲铲之战
- 英雄联盟手游
- 穿越火线：枪战王者
- 无畏契约手游
- 三角洲行动
- 和平精英
- 王者荣耀（官服/体验服/国际服）
- QQ飞车

## 额外说明
- 若需添加新的oplus云控配置，请将文件复制到/data/adb/modules/SCRC/encrypted_oplus-config/目录
  - 同时支持.enc后缀（默认配置）以及.json后缀（可自行修改内容）
  - 若需添加.json配置，请确保文件名为游戏包名，且json格式合规
- 若安装oplus云控注入，可在/data/adb/modules/SCRC/setting.conf中选择是否切换CPU调速器
  - change_governor：是否切换CPU调速器（true/false）
  - target_governor：切换的目标CPU调速器
  - whitelist_governor：检测到这些调速器时不切换（可填入多个，用","隔开）
  - 若同时安装 二改Scene调度，则默认change_governor=true
- 若需更改Scene调度配置，请在如下路径中修改
  - 若已安装模块，可在/data/adb/modules/SCRC/config/路径进行修改
  - 若未安装，可在.zip/scene_config/config_generic(通用版配置) 或 config_oplus-specific(oplus专用版配置)进行修改
- 若需发布二改版本，请先征求原作者意见，并注明原作者
  - 请勿修改模块ID/文件(夹)名，避免造成二进制程序无法正常工作
