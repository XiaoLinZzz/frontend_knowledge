# Cookie, SessionStorage and LocalStorage



1. 存储范围

   - LocalStorage 是持久的，关闭浏览器仍然存储，如果不是主动删除，不会消失。
   - SessionStoage 是会话级别的，数据只在会话内有效。关闭浏览器窗口或者标签页数据会被清除
   - Cookie 会设置 max-age & Expires，到期自动清除。如果是会话级 Cookie 的话，关闭标签页就自动清除。

2. 存储容量

   - LocalStorage 和 SessionStorage 都比较大，大概 5MB 的数据
   - Cookie 容量（4kb）相对比较小，数量也有限制（20-50个）

3. 适用场景

   - 如果是长期保存的数据，可以使用 localStorage 进行存储

   - 如果数据临时需要，比如只需要会话级别的信息，可以使用 SessionStorage 存储

   - Cookie 适合存储小规模数据，比如用户登陆状态，会话标识（Session id），跟踪信息等。

     并且 Cookie 会随着 http 请求发送到服务器，因此适合存储需要频繁根服务器互动的数据

4. 访问限制

   1. SessionStorage 是会话级的，在不同的标签页中互不影响。-> 容易收到 XSS 攻击
   2. LocalStorage 是一个域名共享的，所有的标签页和窗口都可以访问。 -> 容易收到 XSS 攻击
   3. Cookie 可以更灵活的设置访问的范围
      - 通过 `Path` 参数限制 Cookie 只能访问的域名
      - 通过 `Domain` 参数限制 Cookie 只能在特定子域名访问
      - 设置 `HTTPonly` 来禁止 js 访问，防止 XSS 攻击
      - 设置 `Secure` 来保证只能通过 https 进行传输













