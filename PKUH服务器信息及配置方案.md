# PKUH服务器信息及配置方案

## 服务器信息
### 222.29.141.4
#### SSH
- root
- Snail302
#### mysql
- root
- LG1703

## 配置方案
### 基础组件
- nginx latest/1.13.12
- php 7.2-fpm
- mysql latest/8.0.11
### 目录结构
略
### 启动方法
- 初始启动：cd到`/pkuh-site/`目录，运行`docker-compose up -d`，若无报错，访问 http://localshost/ 即可看到网站
- 若修改了nginx配置文件，需要重启容器生效：`docker restart pkuh-nginx`
### 修改配置
- 站点根目录：`/pkuh-site/www/site1/`
- 站点配置文件：`/pkuh-site/conf/nginx/conf.d/site1.conf`
### 恢复原始网站
1. 将之前备份的网站文件解压到站点根目录（里边的index.php可以直接删除）
2. php代码里连接数据库的地址需修改为：mysql
3. 刷新浏览器，看网站是否可以正常访问，若有报错根据报错信息做相应处理
