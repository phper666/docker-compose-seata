# docker-compose-seata
seata使用docker-compose部署，nacos+redis+mysql8+seata1.4.2(默认使用mysql8驱动)

###注意：
1、如果nacos启动失败，有可能是mysql初始化数据库数据还没有初始化完，可以使用下面命令重启   
`docker-compose restart seata-server`
