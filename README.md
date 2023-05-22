# 使用 Docker 快速部署环境

使用 Docker 快速生产环境。

> 使用IP下的 Tools 进行管理,后期替换为PHP-Docker。

> 所有容器都只存在内部网络，只暴露80、443端口。

- Linux + Nginx + PHP多版本 + MariaDB 基础的环境
- Postgres 数据
- Redis 缓存库
- tools/glances 主机监控