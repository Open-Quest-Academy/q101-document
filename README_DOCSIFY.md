# Q101 Docsify Setup

## Quick Start

### Local Testing

使用 Python 启动本地服务器:

```bash
python -m http.server 3000
```

然后访问: http://localhost:3000

### GitHub Pages Deployment

1. 确保所有文件已提交到 master 分支
2. 进入 GitHub 仓库 Settings → Pages
3. Source 选择 `master` 分支和 `/root` 目录
4. 保存后访问: `https://open-quest-academy.github.io/q101-document/`

## Files

- `index.html` - Docsify 配置文件
- `.nojekyll` - 禁用 GitHub Pages Jekyll 处理
- `docs/manual/CLAIM_GUIDE.md` - 用户申领手册
- `docs/_sidebar.md` - 侧边栏导航

## Features

- 实时 Markdown 渲染
- 搜索功能
- 代码高亮和复制
- 图片缩放
- 响应式设计
