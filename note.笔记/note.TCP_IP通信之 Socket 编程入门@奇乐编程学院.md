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
- `s.bind`把这个 socket 连接到了我们某一个网卡的端口上 . 



### 让数据原封不动的发送回去


```python
import socket 

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:

s.bind("0.0.0.0", 1234)

```