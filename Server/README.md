## Server程序



使用：

​	为了匹配环境，请先使用`make`生成新的`server`

​	启动时可以输入参数`Host`表示使用的通信端口，示例：

```bash
./server	#默认使用 8000 作为通信端口
./server 8001	#使用 8001 作为通信地址
```

​     



功能：

- 1、每当一个用户请求连接，就需要开辟一个新的线程
- 2、维护了一个用户名队列，每当有用户连接时，就需要往队列中添加一个用户名以及对应的文件描述符；每当一个用户离开时就将其从队列中删除
- 3、接受每个用户发送过来的消息，并转发至每个用户
- 4、识别用户的传输文件请求，并将作为中介向两端的用户进行消息的传递与数据传输