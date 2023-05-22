# 使用 Docker 快速部署 LNMP 环境

## LNMP 环境

- Nginx PHP和反对代理服务
- PHP81 PHP多版本支持
- Mariadb mysql数据库
- Redis 缓存
- Postgres 数据库

## 下版本优化

- 管理程序
- 权限和密码管理
- Nginx 状态
- Nginx waf 防火墙
- Node 支持

## 使用

创建托管网络
```
docker network create hosting_running_network
```

html 权限
```
docker exec -it php_81 chown 82:82 -R .
#
chown 82:82 -R .
```


### Nginx

nginx-php
```
docker exec -it nginx-web-1 chmod 777 -R /etc/nginx/php
```

nginx 不停机加载
```
docker exec -it nginx-web-1 nginx -t
#
nginx -t
nginx -s reload
```

logs
```
docker logs -f nginx-web-1 
```

### 证书
```
docker exec -it certbot sh
certbot certonly --webroot --webroot-path /var/www/certbot/ -d domain.com
```


### mysql

```
wget https://files.phpmyadmin.net/phpMyAdmin/5.2.1/phpMyAdmin-5.2.1-all-languages.zip
mv myadmin
```

连接配置

```
/**
 * First server
 */
$i++;
/* Authentication type */
$cfg['Servers'][$i]['auth_type'] = 'cookie';
/* Server parameters */
$cfg['Servers'][$i]['host'] = 'db_mariadb';
$cfg['Servers'][$i]['compress'] = false;
$cfg['Servers'][$i]['AllowNoPassword'] = false;
// 多服务器
// $cfg['AllowArbitraryServer'] = true;
```