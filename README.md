# 绛橘色的日落

> 记录技术与生活，用最安静的方式发声。

[![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-在线预览-d97706?style=flat&logo=github)](https://honghuihaohao-cpu.github.io/orange-sunset-blog/)
[![Hexo](https://img.shields.io/badge/Hexo-7.x-0e83cd?style=flat&logo=hexo)](https://hexo.io/zh-cn/)
[![Theme](https://img.shields.io/badge/主题-Keep-d97706?style=flat)](https://keep-docs.xpoet.cn/)

---

## 关于这个博客

这是一个从零开始搭建的个人博客——没有花哨的动效，没有臃肿的框架，只有干净的文字和舒适的阅读体验。配色灵感来自 Claude AI 界面的暖色调，主题选用极简风格的 Keep，托管在 GitHub Pages 上，零成本、完全可控。

---

## 技术选型 & 思考过程

### 为什么选 Hexo？

在静态博客的世界里，主流选择有 Jekyll、Hugo、Hexo、Astro 等等。最终选择 Hexo 的原因：

| 框架 | 语言 | 优点 | 不选它的原因 |
|------|------|------|-------------|
| **Jekyll** | Ruby | GitHub Pages 原生支持 | Windows 上配置 Ruby 环境很痛苦 |
| **Hugo** | Go | 构建速度极快 | Go 模板语法学习曲线陡，中文资料少 |
| **Astro** | JS | 现代化、灵活 | 2024 年才真正成熟，对新手不够友好 |
| **Hexo** ✅ | Node.js | 中文社区最大，主题丰富，一键部署 | — |

**决定**：Hexo。Node.js 生态、中文文档完善、社区活跃，对新手最友好。

### 为什么选 Keep 主题？

逛了一圈 Hexo 主题市场：

| 主题 | 风格 | 暗色模式 | 问题 |
|------|------|----------|------|
| **NexT** | 经典极简 | 需配置 | 用的人太多，千篇一律 |
| **Butterfly** | 绚丽卡片风 | 支持 | 太花哨，不够克制 |
| **Fluid** | Material Design | 支持 | 功能堆砌感较重 |
| **Keep** ✅ | 极简克制 | 自动跟随系统 | — |

**决定**：Keep。它的设计哲学是「去繁就简，回归内容本质」——大道至简，恰好和我想写的博客气质一致。而且它原生支持自动暗色模式、中文排版优化、代码高亮，开箱即用。

### 为什么选 GitHub Pages？

- **零成本**：GitHub 免费提供，不需要买服务器
- **零运维**：不用管 Nginx、不用配 HTTPS、不用操心宕机
- **Git 工作流**：写 Markdown → git push → 自动部署，丝般顺滑
- **可迁移**：数据就是 Markdown 文件，随时可以搬走

### 部署方式：GitHub Actions

传统做法是用 `hexo-deployer-git` 插件在本地 `hexo d` 部署，但有两个问题：

1. 换电脑要重新配 SSH 密钥
2. 本地部署意味着源码和构建产物混在一起

改用 **GitHub Actions** 之后：推送源码到 `main` 分支，Actions 自动执行 `npm install` → `hexo generate` → 部署到 GitHub Pages。构建在云端，本地干干净净。

---

## 博客目录结构

```
orange-sunset-blog/
├── .github/workflows/pages.yml   # GitHub Actions 自动部署脚本
├── _config.yml                    # Hexo 站点配置
├── _config.keep.yml               # Keep 主题配置（颜色、头像、菜单等）
├── source/
│   └── _posts/                    # 所有文章（Markdown 文件）
├── scaffolds/                     # 文章模板
├── themes/                        # 主题文件
└── package.json
```

---

## 本地运行

确保你安装了 **Node.js**（≥ 14.0.0）和 **Git**：

```bash
# 克隆仓库
git clone https://github.com/honghuihaohao-cpu/orange-sunset-blog.git
cd orange-sunset-blog

# 安装依赖
npm install

# 启动本地预览
hexo server
```

浏览器打开 `http://localhost:4000`，修改文件后自动刷新。

---

## 怎么发布文章

### 方法一：本地写 + 推送（推荐）

```bash
# 新建文章
hexo new "我的文章标题"

# 用编辑器打开 source/_posts/我的文章标题.md
# 写完保存，本地预览
hexo server

# 提交并推送
git add .
git commit -m "发布：我的文章标题"
git push
```

推送后 GitHub Actions 自动部署，大约 1-2 分钟博客更新。

### 方法二：网页在线编辑

在 GitHub 仓库页面直接按键盘上的 **`.`** 键，自动打开 GitHub.dev（浏览器版 VS Code），可以直接编辑 Markdown 文件、提交。适合临时修改或没有本地环境的时候。

---

## 日常维护

| 操作 | 命令 |
|------|------|
| 新建文章 | `hexo new "标题"` |
| 本地预览 | `hexo server` |
| 清理+构建+推送 | `hexo clean && hexo generate && git add . && git commit -m "更新" && git push` |
| 更新主题 | `npm update hexo-theme-keep` |

---

## 待完成

- [ ] 评论系统
- [ ] 站点统计
- [ ] RSS 订阅
- [ ] 自定义域名

---

## 许可证

MIT License — 随便用，随便改，注明出处即可。

---

<p align="center">
  <sub>Built with Hexo & Keep Theme · Hosted on GitHub Pages · Deployed by GitHub Actions</sub>
</p>
