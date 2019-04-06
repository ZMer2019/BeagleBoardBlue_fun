# BeagleBoardBlue_fun
My funny working

# Step 1 系统更新
* 从https://beagleboard.org/latest-images 下载最新的系统镜像，我下在的是Debian 9.5 2018-10-07 4GB SD IoT(without graphical desktop)
* 下载并安装Etcher（https://www.balena.io/etcher/ ）
* 通过Etcher将镜像写入到大于4GB的TF卡中
* 将TF卡插入到beagleboard的TF卡槽中，上电即可进入系统
* 暂时我未将系统写入到板载eMMC中。
# Step 2 网络配置
* 上电之后，通过电脑搜索以BeagleBoard-XXXX的无限信号
* 连接上面的SSID
* 此处使用的是无线，默认网关地址为192.168.8.1，可以使用ssh debian@192.168.8.1登陆到后台(官方提供了网页登陆模式),默认的debian用户的密码是"temppwd"
* 登陆之后，切换到root用户，执行如下命令
```
    connmanctl
    scan wifi
    services
    agent on
    connect wifi_XX_XXXX_managed_psk
```
* 上面scan wifi之后执行services会出现你想连接的SSID 对应的在beagleboard中的配置名称，所以connect的参数为SSID对应的一个系统配置名称
