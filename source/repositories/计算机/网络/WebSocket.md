## 特性
* HTML5下一种新的基于tcp的协议
* 浏览器与服务器全双工通信,可以互相主动请求
* **WebSocket在建立握手时，数据是通过HTTP传输的。但是建立之后，在真正传输时候是不需要HTTP协议的**

## 应用
https://zhuanlan.zhihu.com/p/408291927 聊天室
```js
var ws = new WebSocket("ws://localhost:8080");   
//申请一个WebSocket对象，参数是服务端地址，同http协议使用http://开头一样，WebSocket协议的url使用ws://开头，另外安全的WebSocket协议使用wss://开头
ws.onopen = function(){  
　　//当WebSocket创建成功时，触发onopen事件
   console.log("open");  
　　ws.send("hello"); //将消息发送到服务端
}  
ws.onmessage = function(e){  
　　//当客户端收到服务端发来的消息时，触发onmessage事件，参数e.data包含server传递过来的数据  
　　console.log(e.data);  
}  
ws.onclose = function(e){  
　　//当客户端收到服务端发送的关闭连接请求时，触发onclose事件  
　　console.log("close");  
}  
ws.onerror = function(e){  
　　//如果出现连接、处理、接收、发送数据失败的时候触发onerror事件  
　　console.log(error);  
}
```