### Docker 环境安装

https://linuxmirrors.cn/
```
bash <(curl -sSL https://linuxmirrors.cn/docker.sh)
```

启动服务
```
systemctl start docker
service docker start
```

### 使用

1. 创建 compose.yml 文件粘贴复制 执行 docker compose pull 下载
2. 修改 compose.yml 文件 执行 docker compose up 下载
3. 创建 conf.d/00_.conf 文件 配置默认的nginx站点
4. 创建 html/public/index.html 文件
5. 为站点创建证书

### 常用命令
```
# nginx logs
docker logs web -f
docker exec -it web nginx -t
docker exec -it web nginx -s reload

```

### 创建证书

```
docker exec -it ssl certbot certonly --webroot --webroot-path /var/www/certbot/ -d domain.com
```

### 创建 站点

1. 按需复制模板
2. 修改模板
3. 重启 nginx

### Debian 关闭防火墙

```
systemctl stop ufw
systemctl disable ufw
```


### 备份

1. 修改 docker-compose.backup.yml 的 hostname 为主机 backup_ip/tag
2. 修改 .env 文件中的 备份配置
3. 执行 docker compose -f docker-compose.backup.yml up -d

CORN 写法
https://www.runoob.com/w3cnote/linux-crontab-tasks.html

```
每1分钟执行一次myCommand
* * * * * myCommand
每晚的21:30重启smb
30 21 * * * /etc/init.d/smb restart

每周一上午8点到11点的第3和第15分钟执行
3,15 8-11 * * 1 myCommand
```

crontab的命令构成为 时间+动作，其时间有分、时、日、月、周五种，操作符有

- * 取值范围内的所有数字
- / 每过多少个数字
- - 从X到Z
- ，散列数字
