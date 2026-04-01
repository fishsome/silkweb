<div align="center">

# 🕸️ SilkWeb

**丝滑网页抓取工具**

*如丝绸般流畅，如猎手般精准*

<img src="https://img.shields.io/badge/Python-3.8+-blue?style=for-the-badge&logo=python" alt="Python">
<img src="https://img.shields.io/badge/License-MIT-green?style=for-the-badge" alt="License">
<img src="https://img.shields.io/badge/Version-2.0-purple?style=for-the-badge" alt="Version">

---

*触摸网页的每一个角落，不留痕迹*

</div>

## 💋 她能做什么？

| 功能 | 描述 |
|------|------|
| **navigate** | 丝滑导航，支持缓存 |
| **snapshot** | 一眼看穿页面结构 |
| **evaluate** | 执行 JavaScript，随心所欲 |
| **act** | click / type / submit / hover |
| **redirects** | 跟踪每一次跳转 |
| **detect_js** | 识破 JS 重定向陷阱 |

---

## 🔥 快速开始

```python
from silkweb import SilkWeb

# 初始化她的魅力
browser = SilkWeb(timeout=10, cache_dir='./cache')

# 导航到目标
html = browser.navigate("https://example.com")

# 获取快照 - 看清她的全部
snapshot = browser.snapshot(url)
print(snapshot['title'])
print(snapshot['links'])

# 执行 JavaScript - 让她听从你的命令
result = browser.evaluate(url, "document.title")

# 页面交互 - 点击、输入、提交
browser.act(url, action="click", selector="#submit")
browser.act(url, action="type", selector="#search", value="关键词")
```

---

## 🌙 缓存机制

她记得一切，72 小时不忘记：

- **Cookie/Session** - 保持登录态
- **HTML 页面** - 本地缓存
- **跳转历史** - 记录每一次转身

```python
# 保存她的记忆
browser.save_cache()
```

---

## 📦 安装

```bash
pip3 install requests beautifulsoup4 pyyaml pyexecjs lxml
```

或直接下载 Skill 文件：

```bash
# 下载 .skill 文件
wget https://github.com/fishsome/silkweb/raw/main/silkweb.skill
```

---

## 🎭 API 参考

### 核心方法

```python
# 导航
html = browser.navigate(url, force=False)  # force=True 跳过缓存

# 快照
snapshot = browser.snapshot(url)
# 返回: {'title', 'links', 'forms', 'images', 'scripts'}

# JavaScript 执行
result = browser.evaluate(url, "document.title")

# 页面交互
browser.act(url, action="click", selector="#btn")
browser.act(url, action="type", selector="#input", value="text")
browser.act(url, action="submit", selector="form")
browser.act(url, action="hover", selector=".menu")
```

### 高级功能

```python
# 带跳转跟踪的请求
response, redirects = browser.get_with_redirects(url)

# 检测 JS 跳转
redirect_url = browser.detect_js_redirect(url)

# 提取链接
links = browser.extract_links(url, pattern=r'/news/\d+')

# 提交表单
response = browser.submit_form(url, form_selector="#login", data={
    "username": "user",
    "password": "pass"
})
```

---

## ⚙️ 配置

```python
browser = SilkWeb(
    timeout=10,        # 超时时间（秒）
    cache_dir='./cache',  # 缓存目录
    headers={...}      # 自定义请求头
)
```

---

## 🐛 已知问题

- 部分网站需要验证码
- 复杂 JS 渲染可能不完整
- Cloudflare 保护需要特殊处理

---

## 💌 联系

- **作者**: FishSome
- **邮箱**: fishsomes@gmail.com
- **GitHub**: [@fishsome](https://github.com/fishsome)

---

## 📝 更新日志

### v2.0 (2026-04-01)
- ✅ 重命名为 **SilkWeb**
- ✅ 新增 navigate / snapshot / evaluate / act
- ✅ 跳转跟踪 + JS 跳转检测
- ✅ Cookie/Session 缓存 72 小时

### v1.0 (2026-03-30)
- ✅ Chrome 请求头模拟
- ✅ PyExecJS 集成

---

<div align="center">

**用 SilkWeb，让网页抓取变得丝滑**

*Made with 💕 by FishSome*

</div>