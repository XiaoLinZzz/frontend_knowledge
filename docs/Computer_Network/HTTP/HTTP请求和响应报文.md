# HTTP 请求报文

请求报文主要以下组成：

1. 请求行
   1. 方法：比如 GET，POST，PUT，DELETE 等
   2. 资源路径：请求资源的 URI
   3. HTTP 版本： HTTP/1.1 或者 HTTP/2.0
2. 请求头
   - Host：请求的服务器域名
   - **Authorization**：用于认证的凭证信息，比如 token 等
   - **Content-Type**：请求体的媒体类型
   - **Cookie**：存储在客户端的 Cookie
   - if-none-match：资源的 Etag，缓存控制
   - Connection：管理连接的选项，比如 keep-alive
3. 空行：风格请求头部和请求主体
4. 请求体：常用于 POST 和 PUT 请求，包含发送给服务器的数据



# HTTP 响应报文

HTTP响应报文是服务器发送给客户端返回的数据格式，用于传达服务器对客户端请求的处理结果以及相关的数据。

一个标准的 HTTP 响应报文通常包含状态行，响应头，空行和响应体。

状态行包含 HTTP 版本，状态码和状态消息。例如：`HTTP/1.1 200 OK`

一些常见的响应头部字段包括：

- Content-Type：响应主体的类型
- **Expires**：响应的过期时间
- **Etag**：用于缓存，HTTP1.1后
- **Last-Modified**：用于缓存，HTTP1.1后
- **Access-Control-Allow-Origin**: CORS设置，指示哪些域可以访问资源





























