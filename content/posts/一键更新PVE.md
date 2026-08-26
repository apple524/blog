---
title: "Proxmox VE 9替换国内源脚本"
description: " "
date: 2026-08-26
lastmod: 2026-08-26
cover: "https://easyimg.tytus.mobi:16666/i/2e24bb13-b2d7-4ff8-ba8b-dba97fb39709.jpg"
categories:
  - 教程
tags:
  - 教程
tocStartLevel: 3
tocEndLevel: 4
resources:
  - category: github项目
    items:
      - name: github
        url: "https://github.com/Mapleawaa/PVE-Tools-9"

---
<br>

# 项目简介
面向 Proxmox VE 9.x 的一键运维脚本，覆盖 VM 生命周期运维、宿主机网络 / 防火墙 / IPv6、GPU / PCI 直通、系统维护与第三方生态集成。

## ✨ 主要特性

🚀 一键换源 - 自动配置清华大学镜像源，大幅提升下载速度

🚫 删除订阅弹窗 - 彻底消除烦人的订阅提醒

💾 存储优化 - 智能合并 local 与 local-lvm 存储

🔄 Swap 管理 - 可选删除 Swap 分区释放更多空间

📦 系统更新 - 安全的系统升级和清理

📊 系统监控 - 实时显示系统运行状况

🔧 硬件直通 - 轻松配置 PCI 设备直通功能

⚙️ CPU 电源管理 - 灵活调整 CPU 性能模式

🌡️ 温度监控 - 实时显示 CPU 和硬盘温度

🐙 Ceph 支持 - 支持 ceph-squid 和 ceph-quincy 源

🎨 美观界面 - 彩色输出和友好的用户交互

🛡️ 安全备份 - 操作前自动备份重要文件
## 🚀 快速开始
系统要求
✅ Proxmox VE 9.0 或更高版本 （Proxmox VE 8 仅可用升级功能）

✅ Debian 13 (Trixie) 基础系统

✅ Root 权限

✅ 网络连接

cloudflare 短域名
```
bash <(curl -sSL https://pve.oowo.cc/PVE-Tools.sh)
```
中国大陆网络
```
bash <(curl -sSL https://ghfast.top/raw.githubusercontent.com/PVE-Tools/PVE-Tools-9/main/PVE-Tools.sh)
```
国际网络
```
bash <(curl -sSL https://raw.githubusercontent.com/PVE-Tools/PVE-Tools-9/main/PVE-Tools.sh)
```
本地下载运行
```
wget https://raw.githubusercontent.com/PVE-Tools/PVE-Tools-9/main/PVE-Tools.sh
chmod +x PVE-Tools.sh
sudo ./PVE-Tools.sh
```
## 📋 详细功能说明
#### 🚀 更换软件源
Debian 源: 使用 DEB822 格式配置清华大学镜像

企业源: 自动注释 PVE 企业源（此处是需付费可使用的源，普通用户无需使用此功能）

Ceph 源: 配置 Ceph 存储镜像源

无订阅源: 添加适用于社区版的免费源

CT 模板源: 加速容器模板下载

#### 🚫 删除订阅弹窗
自动修改 proxmoxlib.js 文件，彻底移除"No valid subscription"弹窗提醒。

#### 💾 存储管理
合并 local 与 local-lvm:

适用于小容量系统盘

自动备份配置

安全的 LVM 操作

删除 Swap 分区:

释放 Swap 空间给系统使用

适合内存充足的环境

自动修改 fstab 配置

#### 🔧 硬件直通配置
开启硬件直通:

自动检测 CPU 类型（Intel/AMD）

配置 IOMMU 设置

添加 VFIO 驱动模块

设置显卡和音频设备黑名单

关闭硬件直通:

恢复原始 GRUB 配置

移除 VFIO 相关设置

删除黑名单配置

#### ⚙️ CPU 电源模式
支持多种 CPU 性能模式：

Performance: 高性能模式（默认）

Powersave: 节能模式

Ondemand: 按需调频模式

Conservative: 保守调频模式

Schedutil: 负载优化模式

#### 🌡️ 温度监控
添加温度监控:

安装 lm-sensors、nvme-cli 等工具

自动检测硬件传感器

修改 PVE Web UI 显示 CPU/主板/硬盘温度

支持 NVME 和 SATA 硬盘温度显示

删除温度监控:

恢复原始 PVE Web UI 文件

移除相关工具和配置

#### 🐧 内核管理
内核版本检测:

自动检测当前系统内核版本

显示可用内核版本列表

支持 PVE 官方内核和测试版内核

内核下载安装:

从 PVE 官方仓库下载指定内核版本

自动处理依赖关系和冲突

支持内核头文件和开发包安装

内核切换配置:

安全的内核切换机制

自动更新 GRUB 引导配置

支持多内核启动选项管理

#### 🐙 Ceph 存储支持
添加 ceph-squid 源:

适用于 PVE 8/9

配置清华大学镜像源

添加 ceph-quincy 源:

适用于 PVE 7/8

配置清华大学镜像源

卸载 Ceph:

停止所有 Ceph 服务

删除 Ceph 相关软件包

清理配置文件和数据

> ⚠️ 注意事项
{.is-warning}

🔒 权限要求: 必须使用 root 权限运行

💾 数据备份: 重要操作前会自动备份配置文件

🌐 网络需求: 换源功能需要稳定的网络连接

⚡ 内存要求: 删除 Swap 前请确保内存充足

🔧 硬件直通: 需要硬件支持 IOMMU/VT-d 功能

🌡️ 温度监控: 需要硬件支持传感器检测

🐙 Ceph 功能: 请根据您的 PVE 版本选择合适的 Ceph 源