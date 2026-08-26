---
title: "一键更新Linux源工具"
description: " "
date: 2026-08-26
lastmod: 2026-08-26
cover: "https://easyimg.tytus.mobi:16666/i/3c2b242a-e667-4066-87a0-463ed505130d.jpg"
categories:
  - 教程
tags:
  - 教程
tocStartLevel: 3
tocEndLevel: 4

---
<br>

#  <i class="mdi mdi-redhat"></i>一键执行命令
选择您使用的平台:

## Platforms {.tabset}

### 国内（默认） <i class="mdi mdi-home"></i>

```
bash <(curl -sSL https://linuxmirrors.cn/main.sh)
```


### 教育网  <i class="mdi mdi-account"></i>

```
bash <(curl -sSL https://linuxmirrors.cn/main.sh) --edu
```


### 海外地区 <i class="mdi mdi-earth"></i>

```
bash <(curl -sSL https://linuxmirrors.cn/main.sh) --abroad
```

# 注意事项
>  需使用 ROOT 用户执行脚本
> 切换命令为 sudo -i 或 su root。不同系统使用的命令不同
{.is-warning}

