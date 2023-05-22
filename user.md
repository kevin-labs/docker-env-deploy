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