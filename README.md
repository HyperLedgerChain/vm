# vm
one virtual machine for installed fabric, SDK, explorer...

# 注意：虚拟机非常大（>6G）,请慎Clone。


## 虚拟机配置：硬盘50G，内存16G（物理机内存不足的，务必先修改内存）

用户名：bampool

密码：hyperledgerchain

root密码：hyperledgerchain


# 目录说明

#vms

虚拟机ova文件，要求vbox 5.2.20及以上。目前已经安装Fabric、nodejs SDK，blockchain-explorer，以及一个简单的key，value应用。

# 使用说明

---------------------------
-----  使用演示    --------
---------------------------
区块链浏览器地址（有时正在同步，打开较慢）：

http://your ip address:8880

本地端口：8080

transactions页面点击TxId链接，弹出页面中writes项(有时需要往下翻才能看到)可以浏览写入进链数据

其他脚本见cli-scripts.sh

---------------------------
-----  环境说明    --------
---------------------------
链安装在opt目录下

区块链浏览器和Rest服务安装在/usr/local/下

常用脚本和建库脚本在/home/bampool下

/root/目录有所有安装脚本。


---------------------------
-----  启动    --------
---------------------------
重新启动虚拟机后需要执行以下脚本启动服务

su

/home/bampool/start-fabric.sh

nvm use 8.11.2

cd ~/blockchain-explorer/

./start.sh

cd ~/sdk-node/

forever start -a -l /tmp/sdk-node-logs/forever.log -o /tmp/sdk-node-logs/out.log test/business/server.js

sdk示例链接

 curl http://localhost:3000/test/getByKey/TestKey
 
 curl http://localhost:3000/test/setKeyValue/TestKey/YourName

---------------------------
----- 进入cli环境   -------
---------------------------
docker exec -it cli2 bash
