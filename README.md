## 要求

要启动程序，需要满足以下要求：
- 支持 XDP 的现代 Linux 内核（>4.8）
-Python
-需要安装 BCC 及其相关包

## 使用方法

```
python3 filter.py -h
usage: filter [-h] [-protocol PROTOCOL [PROTOCOL ...]]
                 [-p PORT [PORT ...]] [-a ACTION]
                 iface

positional arguments:
  iface                 network interface to listen
                        (e.g. eth0, see avaliable with ip a)

optional arguments:
  -h, --help            show this help message and
                        exit
  -protocol PROTOCOL [PROTOCOL ...], --protocol PROTOCOL [PROTOCOL ...]
                        Specify protocol(s) and
                        port(s), eg tcp:22, udp:53-63
  -p PORT [PORT ...], --port PORT [PORT ...]
                        Specify port(s)
  -ip IP [IP ...]
  					    Specify ip-address(es)
  -mac MAC [MAC ...]
  				    	Specify mac-address(es)                     
  -c CAPTURE, --capture CAPTURE
                        Capture to .pcap file (default dump.pcap)

```
## 使用方法

```
python3 filter.py -h
用法：filter [-h] [-protocol PROTOCOL [PROTOCOL ...]]
               [-p PORT [PORT ...]] [-a ACTION]
               iface

位置参数：
  iface                 监听的网卡接口
                        （例如 eth0，可用 ip a 查看）

可选参数：
  -h, --help            显示帮助信息并
                        退出
  -protocol PROTOCOL [PROTOCOL ...], --protocol PROTOCOL [PROTOCOL ...]
                        指定协议和端口，例如 tcp:22, udp:53-63
  -p PORT [PORT ...], --port PORT [PORT ...]
                        指定端口
  -ip IP [IP ...]
  					    指定 IP 地址
  -mac MAC [MAC ...]
  				    	指定 MAC 地址
  -c CAPTURE, --capture CAPTURE
                        捕获到 .pcap 文件（默认为 dump.pcap）

```
#### 示例

丢弃所有传入的 ICMP 包。

```
python3 filter.py enp0s6 -protocol icmp

```
