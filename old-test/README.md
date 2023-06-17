# 使用Docker快速部署Web 应用

使用 Docker 快速 部署 Web 应用的生产环境，一些必要的东西。

- 使用IP下的 Tools 进行管理, 使用命令行进行Docker。

- 所有容器都只存在内部网络，只暴露80、443端口。

- 项目不托管独立的应用，需要托管独立的应用使用 docker-app。

### 环境配置

- 使用 Wireguard 完成服务器见的网络组网。

### 环境组件

- Linux + Nginx + PHP多版本 + MariaDB 基础的环境
- Postgres 数据
- Redis 缓存库
- Email 邮箱服务 maddy.email
- tools/glances 主机监控
- tools/code-server 在线编辑器(主机配置要求高)
- tools/gost 端口转发
- tools/restic 备份