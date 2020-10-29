### 文中代码 取自于李林峰 
`《netty权威指南》` 
`《netty实战》`
①netty相关概念和和核心组件
②自定义协议的编码解码器
③应用层高级协议支持

架构模型和设计模式


selector 是非阻塞IO的关键 事件通知和api确定在一组非阻塞套接字中哪些已经就绪能够进行io相关的操作
可以在任何事件检查任意的读操作

Channel 一个实体的开放链接 比如读写操作 看做时传入传出数据的载体
回调 是一个方法 指向已经被提供给另外有一个方法的方法引用 回调来处理事件
Future 另一种在操作完成时通知应用程序的方式
事件和ChannelHandler

事件触发不同的动作
动作分类：
记录日志
数据转化
流控制
应用程序逻辑
事件分类：（入站事件）
连接已被激活或者连接失活
数据读取
用户事件
错误事件
事件分类：（出站事件：未来触发某个动作的操作结果）
打开或者关闭到远程节点的连接
将数据写到或者冲刷到套接字



#### 第三章 netty组件和设计
Netty的技术和体系结构的方面内容
Channel.EventLoop ChannelFuture
ChannelHandler
ChannelPipeline


Channel------Socket
EmbeddedChannel
LocalServerChannel
NioDatagramChannel
EventLoop-----控制流 多线程处理
ChannelFuture ----异步通知

第四章 传输
OIO
NIO
Local
Embedded 

ChannelHandler和ChannelPipeline

ChannelHandlerContext 上下文管理
关系：
Channel 四个状态：
①ChannelUnregistered channel已创建但是未注册到EventLoop中去
②ChannelRegistered channel已经被注册到EventLoop
③ChannelActive channel处于活动状态
④channelInactive channel没有链接到远程节点

netty 线程模型
EventLoop


中断与系统调用

进程
处于执行期的程序，但进程并不仅仅局限于一段可执行的代码，包括其他资源，

