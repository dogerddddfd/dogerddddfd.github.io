##### GET和POST
- GET产生一个TCP数据包；POST产生两个TCP数据包。  
- 对于GET方式的请求，浏览器会把http header和data一并发送出去，服务器响应200（返回数据）；  
- 而对于POST，浏览器先发送header，服务器响应100 continue，浏览器再发送data，服务器响应200 ok（返回数据）。  

- get把参数包括在表头、url 
- post在url、表头、request body里  

- 浏览器忽略get中的表单请求
- 浏览器中：
- - 缓存GET，不缓存POST
- - 浏览器限制GET参数上限2k，POST无限制