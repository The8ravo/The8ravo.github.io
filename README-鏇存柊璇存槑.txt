Guangyi Zou — 简洁版主页替换说明
====================================

这套版本参考传统数学学术主页的结构：主页只放简介、联系方式和最近 3 篇论文；
完整论文与笔记分别放在独立页面。没有卡片、动画、深色模式或复杂导航。

需要上传/替换的文件：

  index.html
  publications.html
  notes.html
  404.html
  assets/css/style.css

请保留你仓库中已有的文件：

  assets/profile.jpg
  assets/files/cv.pdf
  assets/img/favicon.svg
  .github/workflows/pages.yml

注意：照片的正确路径是 assets/profile.jpg，不是 assets/img/profile.jpg。

推荐上传方式：

1. 解压本 ZIP。
2. 把解压后的文件复制到本地仓库根目录，允许覆盖同名文件。
3. 在仓库目录运行：

   git add .
   git commit -m "Simplify academic homepage"
   git push

也可以在 GitHub 网页逐个编辑/上传。部署完成后按 Ctrl+F5 强制刷新。
