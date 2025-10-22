# 📚 前端知识库

一个系统化的前端知识库，涵盖 JavaScript、CSS、浏览器原理、计算机网络和算法等核心内容。

## 🌐 在线访问

[点击这里访问文档站点](https://xiaollinzzz.github.io/frontend_knowledge/)

> GitHub Pages 地址: https://xiaollinzzz.github.io/frontend_knowledge/

## ✨ 特性

- 📖 基于 Docsify 构建的轻量级文档网站
- 🔍 全文搜索功能
- 📱 响应式设计，支持移动端
- 🎨 美观的代码高亮
- 📊 字数统计和阅读进度
- 🔗 便捷的页面导航

## 📖 内容概览

### JavaScript 核心
- let、var、const 的区别
- Promise 原理与使用
- this 指向问题
- V8 垃圾回收机制
- 作用域与闭包
- 原型链
- 深浅拷贝
- 防抖与节流

### CSS 与浏览器
- BFC（块级格式化上下文）
- 回流与重绘
- 浏览器渲染进程
- 页面渲染流程

### 计算机网络
- TCP/IP 与 OSI 模型
- HTTP 协议详解
- HTTPS 加密原理
- 同源策略与跨域
- XSS 和 CSRF 攻击
- 缓存机制
- CDN 与 DNS

### 算法
- 排序算法
- 回溯算法

## 🚀 本地运行

### 方式一：使用 docsify-cli

```bash
# 安装 docsify-cli
npm i docsify-cli -g

# 运行本地服务器
docsify serve docs

# 访问 http://localhost:3000
```

### 方式二：使用 Python

```bash
cd docs
python -m http.server 3000
# 访问 http://localhost:3000
```

### 方式三：使用 npx

```bash
npx docsify-cli serve docs
```

## 📦 部署

### GitHub Pages

1. 在 GitHub 上创建一个新仓库
2. 推送代码到仓库：
   ```bash
   git remote add origin <你的仓库地址>
   git branch -M main
   git push -u origin main
   ```
3. 在仓库设置中启用 GitHub Pages：
   - 进入仓库的 Settings
   - 找到 Pages 选项
   - Source 选择 `main` 分支和 `/docs` 目录
   - 保存并等待部署完成

### Vercel

1. 导入 GitHub 仓库到 Vercel
2. 设置构建配置：
   - Build Command: 留空
   - Output Directory: `docs`
3. 点击 Deploy

### Netlify

1. 连接 GitHub 仓库
2. 配置构建设置：
   - Build command: 留空
   - Publish directory: `docs`
3. 部署

## 🛠️ 技术栈

- [Docsify](https://docsify.js.org/) - 文档网站生成器
- Markdown - 文档编写
- GitHub Pages - 静态网站托管

## 📝 License

MIT

## 🤝 贡献

欢迎提交 Issue 和 Pull Request！

---

⭐ 如果这个项目对你有帮助，请给个 Star 吧！

