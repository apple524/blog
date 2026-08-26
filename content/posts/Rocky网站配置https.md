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

配置 HTTPS（Let's Encrypt）
安装 Certbot
CentOS 7：
```sudo yum install -y certbot python2-certbot-nginx```
CentOS Stream 8+ / Rocky Linux 8+：
```sudo dnf install -y certbot python3-certbot-nginx```

申请并自动配置 SSL 证书
```
sudo certbot --nginx -d www.your-domain.com -d your-domain.com
```
验证证书自动续期
```
sudo certbot renew --dry-run```

