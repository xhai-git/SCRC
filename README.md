# SCRC

Oplus 云控注入模块

## 模块介绍

SCRC 旨在不破坏 ColorOS 官方调度的前提下，通过注入云控配置，无损调用官方功能，为官方未适配/效果不佳的游戏适配风驰游戏内核

## 注意事项

- Oplus 云控注入仅支持 OPPO 及其子品牌设备
- 仅支持 ColorOS（含 realme UI）
- 建议使用ColorOS 16（Realme UI 7）较新版本系统
- 不建议使用 ColorOS 15 (Realme UI 6)
- **不支持** ColorOS 14 (Realme UI 5) 及以下系统
- 设备需支持 SCX / Hmbird CPU 调速器
- 请使用官方内核，不建议使用第三方内核 (GKI)
- 不建议刷入限频类模块
- **请勿**开启用户体检计划
- **请勿**使用任何游戏相关第三方线程模块
- **请勿**刷入任何屏蔽官调类模块
- **请勿**刷入任何第三方调度模块
- **请勿**在 Scene 中自行切换 CPU 调速器

## Oplus 云控注入适配列表
### SM8650
- 暗区突围
- 崩坏：星穹铁道
- 穿越火线：枪战王者
- 对峙2（官服/华为服）
- 第五人格
- 第五人格（官服/vivo服）
- 光遇
- 和平精英
- 火影忍者
- 金铲铲之战
- 绝区零
- 洛克王国
- 鸣潮（官服/B服/国际服）
- 逆战未来
- PUBG Mobile（全球服/日韩服/台服/越南服/印度服/测试服）
- QQ飞车
- 王者荣耀（官服/体验服/国际服）
- 无畏契约手游
- 使命召唤手游（官服/繁中服）
- 失控进化
- 三角洲行动
- 香肠派对
- 英雄联盟手游
- 萤火突击（官服/渠道服）
- 永劫无间
- 异环
- 阴阳师
- 原神（官服/B服）
- 战双帕弥什

### SM8750
- 原神

### SM8845
- 巅峰极速
- 王者荣耀

### 包名列表
#### SM8650
```
com.axlebolt.standoff2.huawei
com.axlebolt.standoff2
com.garena.game.codm
com.hottagames.yh.laohu
com.kurogame.haru.hero
com.kurogame.mingchao.bilibili
com.kurogame.mingchao
com.kurogame.wutheringwaves.global
com.levelinfinite.sgameGlobal
com.levelinfinite.sgameGlobal.midaspay
com.miHoYo.hkrpg
com.miHoYo.Nap
com.miHoYo.ys.bilibili
com.miHoYo.Yuanshen
com.netease.dwrg
com.netease.dwrg.nearme.gamecenter
com.netease.dwrg5.vivo
com.netease.l22
com.netease.onmyoji
com.netease.sky
com.netease.yhtj
com.netease.yhtj.nearme.gamecenter
com.pubg.imobile
com.pubg.krmobile
com.rekoo.pubgm
com.sofunny.Sausage
com.tencent.ig
com.tencent.igce
com.tencent.jkchess
com.tencent.KiHan
com.tencent.lolm
com.tencent.mf.uam
com.tencent.nrc
com.tencent.rmcn
com.tencent.tmgp.cf
com.tencent.tmgp.cod
com.tencent.tmgp.codev
com.tencent.tmgp.dfm
com.tencent.tmgp.nz
com.tencent.tmgp.pubgmhd
com.tencent.tmgp.sgame
com.tencent.tmgp.sgamece
com.tencent.tmgp.speedmobile
com.vng.pubgmobile
```

#### SM8750
```
com.miHoYo.Yuanshen
```

#### SM8845
```
com.netease.race
com.tencent.tmgp.sgame
```

## 关于添加云控配置

- 若需添加 Oplus 云控配置，请将文件添加至
  ```
  /data/adb/modules/scrc/encrypted_oplus-config/
  ```
- 支持 `.enc` 后缀（默认配置）以及 `.json` 后缀（明文 json）
- 若添加 `.json` 配置，请确保文件名为游戏包名，且 JSON 格式正确
 
## 关于掉风驰 / 风驰异常

- 请确保各个系统组件运行正常（如 oiface、gameopt、游戏助手、应用增强服务等）
- 若游戏助手/应用增强服务启用后仍无法正常运行，请尝试清除其数据后重试
- 请勿随意冻结系统组件，除非能够确保不会影响风驰
- 若系统环境被严重破坏，请刷机解决
- 请勿开启 Scene 核心分配（游戏中）
- KernelSU 用户请更新至最新版 KernelSU

## 关于二改
- inject 注入程序可用于其他项目
- 可使用明文 .json 文件
- 使用时需确保模块中存在以下结构
```
$MODDIR/
├── bin/
│   └── inject
└── encrypted_oplus-config/
    ├── package_name1.enc
    └── package_name2.json
```
- 使用当前模块框架时，若需添加配置/适配其他SOC平台，请在如下位置进行添加
```
$MODDIR/
└── config/
    ├── $SOC.MODEL_1/
    │   ├── package_name1.enc
    │   └── package_name2.json
    └── $SOC.MODEL_2/
        ├── package_name3.enc
        └── package_name4.json
```
- 发布二改版本请征求原作者意见，并注明原作者
