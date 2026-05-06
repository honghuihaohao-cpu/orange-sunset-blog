# 绛橘色的日落

个人博客，记录技术与生活。

## 技术栈

- **框架**：[Hexo](https://hexo.io/zh-cn/) — 快速、简洁的静态博客框架
- **主题**：[Keep](https://keep-docs.xpoet.cn/) — 极简优雅、专注写作
- **托管**：GitHub Pages（免费）
- **部署**：GitHub Actions 自动部署

## 本地运行

```bash
git clone https://github.com/honghuihaohao-cpu/orange-sunset-blog.git
cd orange-sunset-blog
npm install
hexo server
```

浏览器打开 `http://localhost:4000`。

## 写文章

```bash
hexo new "文章标题"
# 编辑 source/_posts/文章标题.md
hexo server  # 本地预览
git add . && git commit -m "发布文章" && git push
```

推送后 GitHub Actions 自动部署，1-2 分钟后博客更新。

## 网页编辑

在 GitHub 仓库页面按 `.` 键，直接在浏览器里用 VS Code 编辑 Markdown 文件。

## 许可证

MIT
