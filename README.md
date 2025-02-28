## Shadowsocks 一键安装脚本（四合一）</br> 
</br> 

#### 脚本地址:  
https://github.com/teddysun/shadowsocks_install/tree/master  </br>

关于本脚本</br> 
>1.一键安装 Shadowsocks-Python， ShadowsocksR， Shadowsocks-Go， Shadowsocks-libev 版（四选一）服务端；</br> 
2.各版本的启动脚本及配置文件名不再重合；</br> 
3.每次运行可安装一种版本；</br> 
4.支持以多次运行来安装多个版本，且各个版本可以共存（注意端口号需设成不同）；</br> 
5.若已安装多个版本，则卸载时也需多次运行（每次卸载一种）；</br> 


</br> 
</br> 
默认配置</br>

>服务器端口：自己设定（如不设定，默认从 9000-19999 之间随机生成）</br> 
密码：自己设定（如不设定，默认为 teddysun.com）</br> 
加密方式：自己设定（如不设定，Python 和 libev 版默认为 aes-256-gcm，R 和 Go 版默认为 aes-256-cfb）</br> 
协议（protocol）：自己设定（如不设定，默认为 origin）（仅限 ShadowsocksR 版）</br> 
混淆（obfs）：自己设定（如不设定，默认为 plain）（仅限 ShadowsocksR 版）</br> 
备注：脚本默认创建单用户配置文件，如需配置多用户，请手动修改相应的配置文件后重启即可。</br> 


</br> 
</br> 
客户端下载</br> 

>常规版 Windows 客户端</br> 
https://github.com/shadowsocks/shadowsocks-windows/releases</br> 
ShadowsocksR 版 Windows 客户端</br> 
https://github.com/shadowsocksrr/shadowsocksr-csharp/releases
</br> 

---
使用方法</br> 
使用root用户登录，运行以下命令：
```
wget --no-check-certificate -O shadowsocks-all.sh https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocks-all.sh
chmod +x shadowsocks-all.sh
./shadowsocks-all.sh 2>&1 | tee shadowsocks-all.log
```

</br> 
安装完成后，脚本提示如下</br> 

```
Congratulations, your_shadowsocks_version install completed!
Your Server IP        :your_server_ip
Your Server Port      :your_server_port
Your Password         :your_password
Your Encryption Method:your_encryption_method

Your QR Code: (For Shadowsocks Windows, OSX, Android and iOS clients)
 ss://your_encryption_method:your_password@your_server_ip:your_server_port
Your QR Code has been saved as a PNG file path:
 your_path.png

Welcome to visit:https://teddysun.com/486.html
Enjoy it!
```
</br> 

---
卸载方法</br> 
若已安装多个版本，则卸载时也需多次运行（每次卸载一种）</br> 

使用root用户登录，运行以下命令：</br> 


```
./shadowsocks-all.sh uninstall
```
</br>

---
启动脚本
启动脚本后面的参数含义，从左至右依次为：启动，停止，重启，查看状态。</br> 
Shadowsocks-Python 版：</br>

```
/etc/init.d/shadowsocks-python start | stop | restart | status
```

</br>
ShadowsocksR 版：</br>

```
/etc/init.d/shadowsocks-r start | stop | restart | status
```

</br>
Shadowsocks-Go 版：</br>

```
/etc/init.d/shadowsocks-go start | stop | restart | status
```

</br>
Shadowsocks-libev 版：</br>

```
/etc/init.d/shadowsocks-libev start | stop | restart | status
```
</br>

---
各版本默认配置文件</br>
Shadowsocks-Python 版：</br>

```
/etc/shadowsocks-python/config.json
```

</br>
ShadowsocksR 版：</br>

```
/etc/shadowsocks-r/config.json
```

</br>
Shadowsocks-Go 版：

```
/etc/shadowsocks-go/config.json
```

</br>
Shadowsocks-libev 版：

```
/etc/shadowsocks-libev/config.json
```



