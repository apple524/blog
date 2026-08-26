---
title: "Rocky网站配置https"
description: " "
date: 2026-08-26
lastmod: 2026-08-26
cover: "https://easyimg.tytus.mobi:16666/i/140cb008-c3fd-4891-87e6-a8dd4666a3c5.jpg"
categories:
  - 教程
tags:
  - 教程
tocStartLevel: 3
tocEndLevel: 4

---
<br>

配置 HTTPS（Let's Encrypt）<br>
安装 Certbot<br>
CentOS 7：<br>
```sudo yum install -y certbot python2-certbot-nginx```<br>
CentOS Stream 8+ / Rocky Linux 8+：<br>
```sudo dnf install -y certbot python3-certbot-nginx```<br>

申请并自动配置 SSL 证书<br>
```
sudo certbot --nginx -d www.your-domain.com -d your-domain.com
```<br>
验证证书自动续期<br>
```
sudo certbot renew --dry-run```<br>

