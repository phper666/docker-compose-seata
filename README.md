# docker-compose-seata
seata使用docker-compose部署，nacos+redis+mysql8+seata1.4.2(默认使用mysql8驱动)

### 步骤：
1、安装docker和安装docker-compose，怎么安装，自行百度   
2、git clone https://github.com/phper666/docker-compose-seata.git  
3、查询自己电脑的ip，例如mac输入ifconfig则可以查看到ip，类似192.168.0.8，然后修改.env里面的SEATA_IP     
4、cd docker-compose-seata && docker-compose up -d  
5、打开nacos,http://localhost:8848/nacos, 账户：nacos 密码：nacos  
6、点击新建命名空间，命名空间id:9fdcbe8r-4511-4a30-b5f0-7a4fab022ac7,名称为seata    
7、进入配置列表，选择刚刚新建的seata命名空间，点击新建配置，Data ID输入为：seata.properties Group输入为：seata-server     
8、复制seata/conf/seata.properties内容到配置内容里面，类型选择properties  
9、注意修改seata.properties里面的mysql连接，如果你端口默认使用3306则不需要改动  
### 注意：
1、如果nacos启动失败，有可能是mysql初始化数据库数据还没有初始化完，可以使用下面命令重启    
`docker-compose restart seata-server`     
2、seata-service真的太坑了，k8s集群内的pod注册到nacos，是pod的ip，pod之间使用ip可以连接，但是用docker-compose去部署，拿到的也是容器内的ip，所以如果你的应该是在宿主机上，不是容器内，你必须制定SEATA_IP为你的宿主机ip，否则会连接不上   


###demo
最近在研究seata的各个模式demo，欢迎关注，会分享到我的github上
