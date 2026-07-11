# SCRC

Android 调度类模块

## 注意事项

- 本模块暂时仅支持骁龙 8 Gen 3
- 本模块共包含两个部分：
  - Oplus 云控注入
  - 二改 Scene 调度
- Oplus 云控注入为游戏相关配置

## 关于二改 Scene 调度

- 若需使用二改 Scene 调度，则必须安装 Scene 9（Root 模式）
- 二改 Scene 调度包含两个版本：
  - Oplus 专用版
  - 通用版
- 不支持盗版（破解版）Scene
- Oplus 专用版仅支持 OPPO 及其子品牌设备
- Oplus 专用版仅包含日常使用配置，不包含 Scene 游戏调度配置
- Oplus 专用版可与一加风驰游戏内核兼容
- 通用版理论上支持所有设备
- 请在 Scene 中开启 **性能调节** 按钮以生效

## 关于 Oplus 云控注入

- Oplus 云控注入仅支持 OPPO 及其子品牌设备
- 仅支持 ColorOS（含 realme UI）
- 设备需支持 SCX 调速器
- 不建议使用第三方内核
- 不建议刷入其他第三方调度/限频类模块
- 不建议使用任何游戏相关第三方线程模块
- 请勿在 Scene 中自行切换 CPU 调速器
- 请确保各个系统组件运行正常

## 关于掉风驰 / 风驰异常

- 请确保各个系统组件运行正常（如 oiface、gameopt、游戏助手、应用增强服务等）
- 若游戏助手/应用增强服务启用后仍无法正常运行，请尝试清除其数据后重试
- 请不要随意冻结系统组件，除非能够确保不会影响风驰
- 若系统环境被严重破坏，请刷机解决
- 请勿开启 Scene 核心分配（游戏中）
- 使用 KernelSU 的用户，请更新至最新版

## Oplus 云控注入适配列表

- 异环
- 战双帕弥什
- 鸣潮（官服 / B 服 / 国际服）
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
- 王者荣耀（官服 / 体验服 / 国际服）
- QQ 飞车
- 火影忍者

## 关于添加云控配置

- 若需添加新的 Oplus 云控配置，请将文件复制到：
  - `/data/adb/modules/SCRC/encrypted_oplus-config/`
  - 支持 `.enc` 后缀（默认配置）以及 `.json` 后缀（可自行修改内容）
  - 若添加 `.json` 配置，请确保文件名为游戏包名，且 JSON 格式正确

## 关于二改

- 若安装 Oplus 云控注入，可在 `/data/adb/modules/SCRC/setting.conf` 中选择是否切换 CPU 调速器。

```properties
change_governor=true       # 是否启用修改调速器，填写 true 或 false
target_governor=walt       # 启用后切换的目标调速器，仅允许填写设备支持的调速器
whitelist_governor=walt,scx # 检测到这些调速器时不进行切换，可填写多个，使用 , 分隔
```

- 在同时选择**安装二改 Scene 调度**和**云控配置**后，将自动启用切换调速器，否则保持禁用。
- 若不需要自动启用，可在 `/script/scrc_setup.sh` 中移除以下代码：

```bash
if [ "$install" = "1" ]; then
  sed -i 's/^change_governor=.*/change_governor=true/' "$MODDIR/setting.conf"
  echo "已自动开启切换walt调速器（以适配二改Scene调度）"
fi
```

- 若需更改 Scene 调度配置：
  - 已安装模块：修改 `/data/adb/modules/SCRC/config/` 下的 Scene 配置文件
  - 未安装模块：修改压缩包中的
    - `scene_config/config_generic`（通用版配置）
    - `scene_config/config_oplus-specific`（Oplus 专用版配置）
- 若需添加云控配置，请将文件放入：
  - `/data/adb/modules/SCRC/encrypted_oplus-config/`
  - 二改版本仅允许使用自制云控配置；若使用他人云控配置，请注明配置来源及各游戏配置作者
- 若需发布二改版本，请先征求原作者意见，并注明原作者
- 请勿修改模块 ID 或文件（夹）名称，以免导致二进制程序无法正常工作
- 请勿修改模块名称，除非改动内容足够多
- 本模块永久免费，请勿用于牟利