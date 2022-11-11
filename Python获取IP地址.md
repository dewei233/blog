# Python获取IP地址 

一些情况下，我们需要通过Python获取电脑当前的IP地址，并执行一些操作（比如上传到数据库），则可以执行下面的命令：

### 1. 获取外网IP地址

```python
import requests
print(requests.get('http://ifconfig.me/ip', timeout=1).text.strip())
```



### 2. 获取内网IP地址

```python
import socket

try:
  s = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)
  s.connect(('8.8.8.8', 80))
  ip = s.getsockname()[0]
  print(ip)
finally:
  s.close()
```



