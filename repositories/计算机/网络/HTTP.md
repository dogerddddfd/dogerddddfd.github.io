## 请求头
https://www.cnblogs.com/wangyang108/p/5755525.html
> Accept:接收什么类型
> Authorization：授权信息  
> Cookie：这是最重要的请求头信息之一  
> Host：初始URL中的主机和端口。  
> Accept-Charset; Accept-Encoding; Accept-Language

## 响应头
> 

## 状态码
https://m.runoob.com/http/http-status-codes.html

>*1**：信息，服务器收到请求，需要请求者继续执行操作*
>>**100；Continue；继续。客户端应继续其请求**  
>>101；Switching Protocols；切换协议。
>
>
>*2**：成功，操作被成功接收并处理*
>>**200；OK；请求成功。一般用于GET与POST请求**  
>>**201；Created；已创建。成功请求并创建了新的资源**  
>>**202；Accepted；已接受。已经接受请求，但未处理完成**  
>
>
>*3**：重定向，需要进一步的操作以完成请求*  
>>300；Multiple Choices；多种选择。请求的资源可包括多个位置，相应可返回一个资源特征与地址的列表用于用户终端选择  
>>**301；Moved Permanently；永久移动。请求的资源已被永久的移动到新URI，返回信息会包括新的URI，浏览器会自动定向到新URI。今后任何新的请求都应使用新的URI代替**  
>>302；Found；临时移动。与301类似。但资源只是临时被移动。客户端应继续使用原有URI  
>>304；Not Modified；访问浏览器缓存内容  
>
>
>*4**：客户端错误，请求包含语法错误或无法完成请求*
>>**400；Bad Request；客户端请求的语法错误，服务器无法理解**  
>>401；Unauthorized；请求要求用户的身份认证  
>>**403；Forbidden；服务器理解请求客户端的请求，但是拒绝执行此请求**  
>>**404；Not Found；服务器无法根据客户端的请求找到资源（网页）**  
>>414；Request-URI Too Large；请求的URI过长（URI通常为网址），服务器无法处理  
>>408；Request Time-out；服务器等待客户端发送的请求时间过长，超时  
>
>
>*5**：服务器错误，服务器在处理请求的过程中发生了错误*
>>**500；Internal Server Error；服务器内部错误，无法完成请求**  
>>**502；Bad Gateway；作为网关或者代理工作的服务器尝试执行请求时，从远程服务器接收到了一个无效的响应**  
>>**503；Service Unavailable；由于超载或系统维护，服务器暂时的无法处理客户端的请求。**  
>>**504；Gateway Time-out；充当网关或代理的服务器，未及时从远端服务器获取请求**  

##### HTTP流
https://www.jianshu.com/p/4559d0b0d482