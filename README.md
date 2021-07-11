# docker-compose-seata
seata使用docker-compose部署，nacos+redis+mysql8+seata1.4.2(默认使用mysql8驱动)

### 步骤：
1、安装docker和安装docker-compose，怎么安装，自行百度   
2、git clone https://github.com/phper666/docker-compose-seata.git   
3、cd docker-compose-seata && docker-compose up -d  

### 注意：
1、如果nacos启动失败，有可能是mysql初始化数据库数据还没有初始化完，可以使用下面命令重启   
`docker-compose restart seata-server`
