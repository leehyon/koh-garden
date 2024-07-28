---
title: Install Gitea on Debian
draft: false
tags:
  - install
  - linux
---

本教程介绍如何在 Debian 12 安装 Gitea。

## Preparation

Gitea 支持 SQLite，PostgreSQL 和 MySQL/MariaDB 作为数据库后端。
我们将使用 SQLite 作为 Gitea 的数据库。

> [!note]
> SQLite 是一种轻量级的嵌入式数据库引擎，它将数据库存储在单一的文件中，不需要独立运行。而 MySQL 是一种客户端/服务器模式的数据库管理系统。
> SQLite 的场景和应用请参考 👉 [Appropriate Uses For SQLite](https://www.sqlite.org/whentouse.html)

确保 Debian 上已安装 Git 和 SQLite

```bash
sudo apt update
sudo apt -y install git sqlite3
```

接下来，讲使用二进制文件进行安装。
## Download

从 [downloads page](https://dl.gitea.com/gitea/) 下载需要的版本：

- `linux-amd64` 适用于 64-bit 的 Intel/AMD 平台

或者使用 `wget` 来下载，下载完成后，将其移动到 `/usr/local/bin/gitea` 目录。

```bash
VERSION=1.21.0
wget -O gitea https://dl.gitea.com/gitea/${VERSION}/gitea-${VERSION}-linux-amd64
chmod +x gitea
cp gitea /usr/local/bin/gitea
```

## Server configuration

**创建用户来运行 Gitea**（推荐使用 `git` 名称）

```bash
# On Ubuntu/Debian:  
adduser \  
	--system \  
	--shell /bin/bash \  
	--gecos 'Git Version Control' \  
	--group \  
	--disabled-password \  
	--home /home/git \  
	git
```

**创建工作路径**

```bash
mkdir -p /var/lib/gitea/{custom,data,log}  
chown -R git:git /var/lib/gitea/  
chmod -R 750 /var/lib/gitea/  
mkdir /etc/gitea  
chown root:git /etc/gitea  
chmod 770 /etc/gitea
```

> [!warning]
> 为了让 Web 安装程序可以写入配置文件，我们临时为 `/etc/gitea` 路径授予了组外用户 `git` 写入权限。建议在安装结束后将配置文件的权限设置为只读。
> ```bash
> chmod 750 /etc/gitea  
> chmod 640 /etc/gitea/app.ini
> ```

**创建 systemd 服务**

Gitea 提供已配置的 [gitea.service](https://github.com/go-gitea/gitea/blob/release/v1.20/contrib/systemd/gitea.service) 文件。通过 `wget` 将该文件下载到`/etc/systemd/system/`目录。
或者手动创建相应的文件，并拷贝内容：

```bash
sudo nano /etc/systemd/system/gitea.service
```

修改 `user`，`home` 目录以及其他必须的初始化参数，如果使用自定义端口，则需修改 `PORT` 参数，反之如果使用默认端口则需删除 `-p` 标记。

激活 Gitea 并将它作为系统自启动服务：

```bash
sudo systemctl enable gitea  
sudo systemctl start gitea
```

## Upgrade

通过停止程序，替换 `/usr/local/bin/gitea` 并重启来更新到新版本。直接替换可执行程序时不要更改或使用新的文件名称，以避免数据出错。
建议使用 `systemd` 作为服务管理器，使用 `systemctl restart gitea` 安全地重启程序。

## More

如果 Debian 正在运行运行 UFW 防火墙，则需要允许 3000 端口的连接。

```bash
sudo ufw allow 3000/tcp
```

打开浏览器，输入`http://127.0.0.1:3000`，将数据库设置的为以下参数：

- Database Type: SQLite3
- `/var/lib/gitea/data/gitea.db`
- Repository Root Path: `/home/git/gitea-repositories`
- Git LFS Root Path: `/var/lib/gitea/data/lfs`
- Run As Username: git
- SSH Server Port: 22

完成后，您将被重定向到登录页面。点击`立即注册`。 第一个注册用户将自动添加到管理员组。

最后运行命令`sudo chmod 750 /etc/gitea` 将 Gitea 配置文件的权限更改为只读。
