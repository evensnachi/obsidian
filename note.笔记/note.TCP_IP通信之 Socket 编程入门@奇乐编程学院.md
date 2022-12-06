---
title: note.TCP_IP通信之 Socket 编程入门@奇乐编程学院
date: 05-12-2022
url: https://youtu.be/ST6WLZFSHXs
tags: category/application/socket, 
aliases: socket, socket编程, note.TCP/IP通信之 Socket 编程入门@奇乐编程学院
publisher: 奇乐编程学院
---

# IP通信之 Socket 编程入门@奇乐编程学院

## 什么是 Socket

- Socket 是一套用于**不同主机**间**通信**的[[API]] . 
	- 工作在 [[TCP_IP_协议栈|TCP/IP协议栈]]之上 . 
## 通过Socket在不同主机间建立通信

- 制定主机的[[IP 地址]]和一个[[端口号]] . 
	-  [[IP 地址]] : 用于区分网络上的不同主机, 保证数据发送到正确的主机中去. 
	- [[端口号]] : 用于区分主机上的不同应用 . 保证数据发送到正确的应用中去.  
- 通过 Socket 我们可以在网络上点对点的建立一条数据通道. 
	- 就像把一条数据线连接到两个 usb 接口上一样.  
- Socket 翻译为 "(电源)插座; (电器)插口" . 

## Socket 的两种类型

### TCP

- [[Transmission Control Protocol]]

#### TCP 的两个特点

- 底层会自动检测并回传丢失的数据包 . 
	- 保证了数据会完整的被发送与接收 . 
- 发送和接收到的数据顺序是完全一致的 . 
	- 这就是 TCP被说是基于[[Data Stream|数据流]] 的协议 . 


#### TCP 要求收发数据的双方扮演不同的角色 : 

##### 服务器与客户端

- 服务器会**被动等待**客户端的连接, 自己不会主动发起请求 . 

### UDP

- [[User Datagram Protocol]]
	- 以[[Datagram|报文]]为单位来收发数据
- UDP 不会自动回传丢失的数据包 . 
	- 所以不保证数据的完整传输 . 
	- 也因此具有更低的延迟并占用更少的系统资源 . 
	- 更适合像视频或语音的这种实时性要求较高的应用. 

## 以 Python 为例来讲解 Socket 编程的部分 

### 创建服务器

```python
import socket 
```
- 导入 `socket` 包

```Python
with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
```
- `with` 表示当代码离开`with`块的时候, 自动调用 `s.close()` 销毁这个 socket . 
- 两个参数
	- `socket.AF_INET` 代表使用的是 [[IPV4]] 的[[Address family|地址家族]] . 
	- `socket.SOCK_STREAM` 代表我们使用的是[[Transmission Control Protocol|TCP]]协议 . `STREAM` 也说明了TCP协议是个流式协议 . 

```python
s.bind("0.0.0.0", 1234)
```
- `s.bind`把这个 socket 关联到了我们某一个网卡和端口上 .  
	- 网卡通过 IP 地址制定
		- 0.0.0.0 是个特殊的 IP 地址 : 代表主机上的任意网卡都可以使用这个 socket 进行通信 . 

```python
s.listen()
```
- 将 socket 置为监听状态. 等待连接. 

```python
c, addr = s.accept()
```

- `accept()` 会接收来自任意客户端的连接
	- 并返回一个新的 socket `c` 以及客户端的 IP 地址 `addr`
- 注意 `s` 和 `c` 的不同
	- `s` 主要用于监听
	- `c` 则用于与客户端的通信 

### 让数据原封不动的发送回去

```python
with c: 
	print(addr, "connedcted.")
	while True:
		data = c.recv(1024)
		if not data: 
			break
		c.sendall(data)
```
- 输出客户端 IP 地址
- 使用循环调用` recv()`接收客户端传来的信息. 
	- 1024 是一次性收到的数据长度 1024 字节.
- `if not data: break` 如果没有接收数据, 就 结束
- `c.sendall(data)` 否则就把数据回传

```python
import socket 

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:

s.bind("0.0.0.0", 1234)
s.listen()
c,addr = s.accept()
with c:
	print(addr, "connected")
	while Ture:
		data = c.recv(1024)
		if not data:
			break
		c.sendall(data)

```

### 测试代码

- 首先运行代码
- 进入 shell

#### Linux 下的网络测试工具 netcat 

- 可以读取 TCP/UDP 数据

```shell
nc  127.0.0.1 1234
```
- `nc` + 服务器的 IP 地址 + 端口号
- `127.0.0.1` 是一个回送地址, 代表本地计算机 . 
- `1234` 是端口号

- 之后在控制台输入的都会原封不动的发送回来

### 制作客户端

```python
import socket 

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:

s.connect("127.0.0.1", 1234)
s.sendall(b"Hello World!")
data = s.recv(1024)
print("Received: ", repr(data))

```

`s.connect()` 连接服务器
`s.sendall()` 发送一条消息给服务器, 注意这里的参数是字符序列, 前面要加`b` . 并不是字符串 . 
`s.recv(1024)` 获取服务器回传的信息
`print("Received: ", repr(data))` 输出回传数据

## 多线程的 Socket 服务器
- Multi-threaded Socket Server 

```python
import socket
import threading

# 这段线程中的代码代表服务器会不断回传信息
def handle_client(c, addr):
	print(addr, "connected")

	While True: 
		data = c.rev(1024)
		if not data:
			break
		c.sendall(data)

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
	s.bind("0.0.0.0", 1234)
	s.listen()

	while True: 
		c, addr = s.accept()
		# 不断接收客户端数据
		t.threading.Thread(target = handle_client, args = ( c, addr ))
		# 创建新线程, 并将 socket 和地址传递给这个线程
		t.start() 
		
```

- python 无法做到真正的多线程, 有不少缺点. 

#### selectors - 高级 I/O 复用库

- 实现多连接并发

####  asyncio - 异步 I/O

- 更高层

## 简易 HTTP 服务器
- simple HTTP Server

- HTTP 是 TCP 协议的一个典型应用, 浏览器与服务器交互的主要方式.
- 通常服务器会监听 80 端口, 等待客户端
- 客户端连接上服务器后
	- 指定要连接的资源
	- 提供额外的信息, 每一条都是键值对
		- 包括浏览器信息等.
	- 这部分叫做**消息的头部(header)**(HTTP消息头)
	- 空行
	- **消息的主体**
- 服务器在收到消息后, 会以同样的格式响应 .
	- 第一行是状态行, 包含状态码
		- 200 : 请求成功
		- 404 : 请求资源不存在
	- 接下来是请求的类型, 服务器信息等
	- 空行
	- **消息的主体**

#### python 标准库中, 已经实现了一个简易的 HTTP 服务器
- 只用于测试和开发