---
layout: default
---

<style>
body {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
  line-height: 1.6;
  margin: 0;
  padding: 0;
  color: #333;
  background-color: #f8f9fa;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
}

/* 头部导航 */
.header {
  background-color: #fff;
  box-shadow: 0 2px 4px rgba(0,0,0,.1);
  padding: 1rem 0;
  position: sticky;
  top: 0;
  z-index: 100;
}

.nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.nav-brand {
  font-size: 1.5rem;
  font-weight: bold;
  color: #667eea;
  text-decoration: none;
}

.nav-links {
  display: flex;
  list-style: none;
}

.nav-links li {
  margin-left: 1.5rem;
}

.nav-links a {
  text-decoration: none;
  color: #333;
  font-weight: 500;
  transition: color 0.3s;
}

.nav-links a:hover {
  color: #667eea;
}

/* 主要内容区域 */
.main {
  padding: 2rem 0;
}

/* 英雄区域 */
.hero {
  text-align: center;
  padding: 4rem 1rem;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  color: white;
  border-radius: 8px;
  margin-bottom: 3rem;
}

.hero h1 {
  font-size: 2.5rem;
  margin-bottom: 1rem;
}

.hero p {
  font-size: 1.2rem;
  opacity: 0.9;
  max-width: 600px;
  margin: 0 auto;
}

/* 博客文章列表 */
.content {
  max-width: 800px;
  margin: 0 auto;
  background: #fff;
  border-radius: 8px;
  padding: 2rem;
  box-shadow: 0 1px 3px rgba(0,0,0,.1);
}

.post-list {
  list-style: none;
  padding: 0;
}

.post-item {
  padding: 1.5rem 0;
  border-bottom: 1px solid #eee;
}

.post-item:last-child {
  border-bottom: none;
}

.post-item h2 {
  margin-top: 0;
  margin-bottom: 0.5rem;
}

.post-item h2 a {
  text-decoration: none;
  color: #333;
  transition: color 0.3s;
}

.post-item h2 a:hover {
  color: #667eea;
}

.post-meta {
  color: #666;
  font-size: 0.9rem;
  margin-bottom: 1rem;
}

.post-excerpt {
  color: #555;
  line-height: 1.7;
}

/* 页脚 */
.footer {
  text-align: center;
  padding: 2rem 0;
  color: #666;
  font-size: 0.9rem;
}

.btn {
  display: inline-block;
  padding: 0.75rem 1.5rem;
  background-color: #667eea;
  color: white;
  text-decoration: none;
  border-radius: 4px;
  font-weight: 500;
  transition: background-color 0.3s;
}

.btn:hover {
  background-color: #5a6fd8;
}

/* 响应式设计 */
@media (max-width: 768px) {
  .nav {
    flex-direction: column;
  }
  
  .nav-links {
    margin-top: 1rem;
  }
  
  .nav-links li {
    margin: 0 0.5rem;
  }
  
  .hero {
    padding: 2rem 1rem;
  }
  
  .hero h1 {
    font-size: 2rem;
  }
}
</style>

<div class="header">
  <div class="container nav">
    <a href="/" class="nav-brand">我的博客</a>
    <ul class="nav-links">
      <li><a href="/">首页</a></li>
      <li><a href="#">关于</a></li>
      <li><a href="#">联系</a></li>
    </ul>
  </div>
</div>

<div class="container">
  <div class="main">
    <div class="hero">
      <h1>欢迎来到我的博客</h1>
      <p>在这里分享我的想法、经验和教程</p>
      <a href="#posts" class="btn">查看文章</a>
    </div>

    <div class="content">
      <h2 id="posts">最新文章</h2>
      <ul class="post-list">
        {% for post in site.posts %}
          <li class="post-item">
            <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
            <p class="post-meta">{{ post.date | date: "%Y年%m月%d日" }}</p>
            <p class="post-excerpt">{{ post.excerpt }}</p>
          </li>
        {% endfor %}
      </ul>
    </div>
  </div>
</div>

<div class="footer">
  <div class="container">
    <p>&copy; {{ site.time | date: "%Y" }} 我的博客. 版权所有.</p>
  </div>
</div>


