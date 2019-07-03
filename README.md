#nginx-php-fpm


#环境组件

##OS

- [alpine:3.8](https://github.com/docker-library/php/blob/4fa4c526cf52725f859d7067006e8d4b3c226a52/7.1/alpine3.8/fpm/Dockerfile)

##PHP

- php:7-fpm-alpine

##Nginx

- 1.14.2

#Redis

- redis:latest

##memcahed

- memcached:alpine

##beanstalkd

- schickling/beanstalkd:latest

# 开始

- 构建镜像

````
sh build.sh

或者

docker build -t wushunyi/nginx-php7-fpm:latest .
    
````

- 启动环境

````
docker-compose up
    
````

# 本地化配置

## 修改代码路径

```
   
```

## 修改HOST

## 修改nginx域名

```
    所有NGINX的配置都在这里 
    
    conf/nginx/sites-enabled
```


# 目录说明

```

.   
├── Dockerfile                      镜像构建文件
├── README.md
├── build.sh                        镜像构建脚本
├── conf
│   ├── nginx
│   │   ├── nginx-site-ssl.conf
│   │   ├── nginx-site.conf
│   │   ├── nginx.conf              nginx服务配置
│   │   └── sites-enabled           nginx虚拟主机配置
│   │       ├── default.conf
│   ├── php                     PHP相关配置
│   │   ├── docker-vars.ini
│   │   ├── php-fpm.conf
│   │   └── php.ini
│   └── supervisord             supervisor配置
│       ├── conf.d
│       └── supervisord.conf
├── data
│   ├── database            数据库文件
│   └── log                 日志文件目录
├── docker-compose.yml
├── env_file                服务器环境变量
├── errors                  404相关错误提示
│   ├── 404.html        
│   └── sad.svg
├── hosts.example           hosts修改建议
├── scripts                 docker启动相关配置脚本
│   └── start.sh            
└── src
    └── index.php           默认站点演示脚本phpinfo

```

