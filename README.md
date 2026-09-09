# Guangyi Zou — GitHub Pages 学术个人主页

这是从原 WordPress 公共页面整理并重新设计的一套纯静态网站。无需安装 Jekyll、Node.js 或其他框架；上传到 GitHub 后即可通过 GitHub Pages 部署。

## 文件结构

```text
.
├── index.html                  # 主页面内容
├── 404.html                    # 404 页面
├── assets/
│   ├── css/style.css           # 页面样式与响应式布局
│   ├── js/main.js              # 深色模式、移动导航
│   ├── img/profile.svg         # 当前头像占位图/字母头像
│   ├── img/favicon.svg         # 浏览器图标
│   └── files/                  # 可放 CV、讲义等文件
├── .github/workflows/pages.yml # GitHub Pages 自动部署
├── .nojekyll                   # 兼容“从分支部署”的静态模式
└── MIGRATION_CHECKLIST.md      # 上线前检查清单
```

## 一、部署到 GitHub Pages

### 推荐方式：个人主页仓库

1. 登录 GitHub，新建仓库，仓库名必须是：

   ```text
   你的GitHub用户名.github.io
   ```

2. 把本目录的全部文件上传到仓库根目录，包括 `.github` 文件夹。
3. 打开仓库的 **Settings → Pages**。
4. 在 **Build and deployment** 中，把 **Source** 设为 **GitHub Actions**。
5. 推送到 `main` 分支后，等待 Actions 完成部署。
6. 网站地址为：

   ```text
   https://你的GitHub用户名.github.io/
   ```

如果你使用的是普通项目仓库，例如 `homepage`，地址通常为 `https://用户名.github.io/homepage/`。本项目全部使用相对路径，因此同样可以正常工作。

## 二、本地预览

进入项目目录后运行：

```bash
python -m http.server 8000
```

浏览器访问：

```text
http://localhost:8000
```

双击 `index.html` 也能查看，但使用本地服务器更接近正式部署环境。

## 三、上线前建议修改

### 1. 换成正式照片

当前 `assets/img/profile.svg` 是不冒充真人照片的字母头像。建议从 WordPress 旧站保存原始照片，再放到：

```text
assets/img/profile.jpg
```

然后在 `index.html` 中搜索：

```html
src="assets/img/profile.svg"
```

改为：

```html
src="assets/img/profile.jpg"
```

旧站当前公开照片地址：

```text
https://zouguangyi.wordpress.com/wp-content/uploads/2026/08/photo.jpg?w=768
```

建议在关闭或隐藏 WordPress 站点前先保存到本地。

### 2. 添加 CV

把简历放到：

```text
assets/files/cv.pdf
```

然后在 `index.html` 中找到 `To add a CV later` 注释，取消对应链接的注释。

### 3. 检查个人信息

目前页面使用：

- UCI 邮箱：`gzou3@uci.edu`
- 个人邮箱：`zouguangyi2001@gmail.com`
- Google Scholar、arXiv、ORCID、UCI profile
- UCI 与 USTC 学习经历
- 6 篇 arXiv 论文/预印本
- 原 WordPress 的 7 份笔记链接

请特别核对年级、导师关系、论文状态以及是否希望公开个人邮箱。

## 四、以后如何更新

主页大部分内容都在 `index.html`：

- 简介：搜索 `hero-copy`
- 新闻：搜索 `news-list`
- 论文：搜索 `publication-list`
- 笔记：搜索 `notes-grid`
- 友情链接：搜索 `link-columns`

样式在 `assets/css/style.css`；主题颜色集中写在文件开头的 `:root` 变量中。

## 五、自定义域名（可选）

购买域名并按 GitHub Pages 文档设置 DNS 后，在仓库根目录新建 `CNAME` 文件，只写一行域名，例如：

```text
guangyizou.com
```

仓库中附带了 `CNAME.example` 供参考。

## 六、WordPress 迁移建议

新站部署并检查无误后，可以先在 WordPress 首页顶部加入新站地址，保留旧站一段时间，方便访问者和搜索引擎发现新地址。确认 Google Drive 笔记权限、所有外链及邮箱都正常后，再决定是否关闭旧站。

## 技术说明

- 纯 HTML/CSS/JavaScript，无第三方 CDN
- 响应式设计，适配手机与桌面
- 支持系统深色模式和手动切换
- 基础 SEO、Open Graph 与 Person JSON-LD
- 自动生成当前年份
- 尊重 `prefers-reduced-motion`

页面代码可按 MIT License 使用；个人资料、论文内容、照片与笔记不因本仓库而自动采用 MIT License。
