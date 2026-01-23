# Q101 文档站点使用说明

## 📖 简介

使用 Docsify 为 Q101 用户申领手册创建的轻量级文档网站。

## 🚀 本地测试

### 方法 1: Python（推荐）
```bash
python -m http.server 3000
```
访问: http://localhost:3000

### 方法 2: Docsify CLI
```bash
npm i docsify-cli -g
docsify serve . -p 3000
```

## 🌐 在线访问

GitHub Pages: https://open-quest-academy.github.io/q101-document/

## 📁 文件结构

```
q101-document/
├── index.html              # Docsify 配置
├── .nojekyll               # GitHub Pages 设置
├── docs/
│   ├── _sidebar.md         # 侧边栏
│   └── manual/
│       └── CLAIM_GUIDE.md  # 用户申领手册
└── README_DOCSIFY.md       # 详细说明
```

## ✨ 功能

- ✅ 实时 Markdown 渲染
- ✅ 全文搜索
- ✅ 代码高亮和复制
- ✅ 图片缩放
- ✅ 响应式设计

## 📝 添加内容

只需在 `docs/manual/` 目录下添加新的 `.md` 文件，然后更新 `docs/_sidebar.md` 即可。
