# Carpet Plugin Suite

将 Carpet Fabric 模组移植为 Bukkit/Leaves 服务器插件。

适用于 Paper 1.20.4 / Leaves 1.20.4 / Folia · JDK 17+

---

## 架构

```
Carpet/                 ← 核心插件（必装）
  ├─ 规则引擎 + /carpet 命令
  ├─ 事件处理器（45+ 规则）
  ├─ ExtensionManager（自动发现扩展）
  └─ config.yml

Carpet-AMS/             ← 可选扩展
Carpet-TIS/             ← 可选扩展
Carpet-CCA/             ← 可选扩展
Carpet-GCA/             ← 可选扩展
```

扩展依赖 `Carpet` 核心（plugin.yml 中声明 `depend: [Carpet]`），启动时核心自动扫描所有注册了 `CarpetExtension` 接口的插件并注册。

## 命令

| 命令 | 权限 | 说明 |
|---|---|---|
| `/carpet` | carpet.admin | 列出所有规则及当前值（绿=开，灰=关） |
| `/carpet <规则名>` | carpet.admin | 查看单条规则的描述和可选值 |
| `/carpet <规则名> <值>` | carpet.admin | 设置规则值 |
| `/carpetlog <文本>` | carpet.admin | 发送 Carpet 日志广播 |

Tab 自动补全规则名和可选值。

## 核心规则

> 大部分默认关闭，需手动开启。规则值会持久化到 `config.yml`。

### 生存/机械

| 规则 | 默认值 | 说明 |
|---|---|---|
| `silk-touch-spawner` | false | 精准采集获取刷怪笼（带实体类型 Lore） |
| `portable-crafting` | false | 右键空气打开合成台 |
| `tnt-duplication` | false | TNT 爆炸时生成额外 TNT |
| `flippin-cactus` | false | 仙人掌可翻转方块 |
| `xp-no-cooldown` | false | 经验球无拾取冷却 |
| `lead-fix` | false | 拴绳不会断裂 |
| `custom-nether-portals` | false | 自定义传送门（任意大小） |
| `universal-bonemeal` | false | 下界/末地也可使用骨粉 |
| `dispenser-mine-block` | false | 发射器挖掘面对的方块 |
| `hopper-speed` | 4 | 漏斗传输速度（tick） |
| `piston-push-limit` | 12 | 活塞最大推动方块数 |
| `fill-limit` | 32768 | /fill 最大方块数 |

### 修复/优化

| 规则 | 默认值 | 说明 |
|---|---|---|
| `creative-no-clip` | false | 创造模式穿墙飞行 |
| `anti-creeper-grief` | false | 阻止苦力怕破坏地形 |
| `structure-block-tools` | false | 结构方块坐标提示 |
| `placement-rotation-fix` | false | 放置方向修正 |

### 用法示例

```
/carpet silk-touch-spawner true
/carpet portable-crafting true
/carpet creative-no-clip true
/carpet xp-no-cooldown true
/carpet hopper-speed 2
```

## 扩展功能

### Carpet-AMS

| 规则 | 说明 |
|---|---|
| `anti-afk` | 防 AFK 踢出 |
| `keep-inventory` | 死亡不掉落（含经验） |
| `walk-on-snow` | 雪地行走加速 |
| `logout-spot` | 记录登出位置，上线自动传送 |
| `xp-drop` | 双倍经验掉落 |

### Carpet-TIS

| 规则 | 说明 |
|---|---|
| `creative-nether-water` | 创造模式下界放水 |
| `void-trading` | 虚空环境允许交易 |
| `repeater-silk-touch` | 精准采集获取中继器 |
| `trail` | 玩家身后粒子轨迹 |

### Carpet-CCA

| 规则 | 说明 |
|---|---|
| `fast-leaf-decay` | 快速树叶消失 |
| `farm-protection` | 防止农田被踩踏 |
| `string-duper` | 活塞推绊线复制线 |

### Carpet-GCA

| 规则 | 说明 |
|---|---|
| `sign-editing` | 潜行右键重新编辑告示牌 |
| `iron-farm` | 打开村民交易栏时显示村民坐标 |
| `rail-duper` | 铁轨复制 |
| `fast-leaf-decay` | 快速树叶消失 |
| `farm-protection` | 防踩农田 |

## 部署

1. **必备：** 放入 `Carpet-1.0.0.jar`
2. **可选：** 放入 `Carpet-AMS.jar`、`Carpet-TIS.jar` 等扩展
3. 重启服务器

## 构建

**前置：** JDK 17+，Gradle（项目自带 wrapper）

```powershell
.\gradlew.bat build
```

输出于各模块 `build/libs/` 目录。

### 镜像源

`gradle/wrapper/gradle-wrapper.properties` 已配置腾讯云镜像，国内可直接拉取。
