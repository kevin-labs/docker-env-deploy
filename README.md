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