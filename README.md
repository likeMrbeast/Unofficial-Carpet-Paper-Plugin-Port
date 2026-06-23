
# Carpet Bukkit 移植 - test2-1.0.0


## 文件列表

| 文件 | 大小 | 说明 |
|------|------|------|
| \Carpet-1.0.0.jar\ | 33KB | 核心插件，必装 |
| \Carpet-TIS-Addition-1.0.0.jar\ | 3KB | TIS 扩展 |
| \Carpet-AMS-Addition-1.0.0.jar\ | 3KB | AMS 扩展 |
| \Carpet-CCA-1.0.0.jar\ | 3KB | CCA 扩展 |
| \Carpet-GCA-1.0.0.jar\ | 3KB | GCA 扩展 |

## 安装

1. 把 \Carpet-1.0.0.jar\ 扔进 \plugins/\
2. （可选）扩展包也扔进去，自动识别注册
3. 重启服务器

## 命令

### 通用
- \/carpet\ — 查看所有规则
- \/carpet <规则名>\ — 查看规则当前值
- \/carpet <规则名> <值>\ — 设置规则

### TPS 控制
- \/tick rate <tps>\ — 设置目标 TPS
- \/tick freeze\ — 冻结 tick
- \/tick unfreeze\ — 解除冻结
- \/tick step <次数>\ — 步进 tick

### 假人
- \/player <名字> spawn\ — 生成假人
- \/player <名字> kill\ — 移除假人
- \/player <名字> <动作>\ — 控制假人

### 日志
- \/log tps\ — 实时 TPS 显示
- \/log mobcaps\ — 实体上限显示
- \/counter start/stop/reset\ — 漏斗计数器

### 工具
- \/info\ — 方块信息
- \/distance\ — 距离测量
- \/raid\ — 袭击者统计
- \/ping\ — 延迟

## 环境

Paper 1.20.4 | Java 21 | Gradle 8.5
