# Hacking Tools Demo
This is my simplicity hacking demo

### TcpPortForward.py 端口转发
```
使用场景:

一：
A服务器在内网，公网无法直接访问这台服务器，但是A服务器可以联网访问公网的B服务器（假设IP为222.2.2.2）。
我们也可以访问公网的B服务器。我们的目标是访问A服务器的22端口。那么可以这样：

1. 在B服务器上运行：
./TcpPortForward.py l:10001 l:10002
表示在本地监听了10001与10002两个端口，这样，这两个端口就可以互相传输数据了。

2. 在A服务器上运行：
./TcpPortForward.py c:localhost:22 c:222.2.2.2:10001
表示连接本地的22端口与B服务器的10001端口，这两个端口也可以互相传输数据了。

3. 然后我们就可以这样来访问A服务器的22端口了：
ssh 222.2.2.2 -p 10002
原理很简单，这个命令执行后，B服务器的10002端口接收到的任何数据都会传给10001端口，此时，A服务器是连接了B服务器的10001端口的，数据就会传给A服务器，最终进入A服务器的22端口。

二：
不用更多举例了，TcpPortForward.py的l与c两个参数可以进行灵活的两两组合，多台服务器之间只要搞明白数据流方向，那么就能满足很多场景的需求。
```



### zipattack.py zip加密文件暴力破解

```
帮助说明：  python zipattack.py -h

测试：
zip test.zip *.gif -e 

进行暴力破解：
python zipattack.py -f test.zip -d password.txt
```


### createDict.py 生成一个简单的密码破解字典
```
python createDict.py 

按ctrl+c 停止生成
```