# HTTPS 和 HTTP 什么区别？

1. 加密层：首先在 HTTP 的基础上，新增加了一个 `SSL/TLS` 协议作为加密层，确保数据的传输安全性。HTTP 是明文传输，比较容易受到攻击
2. HTTP 的连接只要 TCP 三次握手后就可以建立成功。而 HTTPS 的连接还有需要 `SSL/TLS` 的握手过程，才可以进行加密传输
3. 端口：HTTP 使用 80， HTTPS 使用 443 端口
4. HTTPS 协议需要向 CA 申请数字证书，确保服务器身份可信





# HTTPS 建立连接的过程

<img src="/Users/lujiema/Documents/typora-user-images/Screenshot 2025-02-28 at 10.08.14 PM.png" alt="Screenshot 2025-02-28 at 10.08.14 PM" style="zoom: 33%;" />

HTTPS 建立连接的过程 = TCP 三次握手 + TLS 四次握手

1. TCP 三次握手
2. TLS 四次握手
   1. 客户端发送 TLS 版本 + 加密算法 + 客户端随机数
   2. 服务器接收加密算法，并且返回数字证书（CA 包含公钥）以及 服务端随机数
   3. 客户端接收到 CA 并且做验证
   4. 客户端生成 预主密钥（pre-master secret），然后使用公钥加密后发送给服务器
   5. 服务器使用私钥进行解密，双方根据随机数，生成对称加密密钥
   6. 完成连接，后续都使用这对相同的密钥做对称加密













