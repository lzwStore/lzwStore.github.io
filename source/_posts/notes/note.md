---
title: Hexo 初体验
date: 2023-05-26 09:53:17
categories: 
  - 笔记
type: "note"
tag: [笔记]
feature: true
# 头图
top_img: /img/1.png
---

# Hexo搭建博客

## 创建项目

1. 全局安装 hexo-cli 脚手架
```bash
npm install -g hexo-cli
```

2. 安装hexo
```bash
npm install hexo
```

3. 安装 Hexo 完成后，请执行下列命令，Hexo 将会在指定文件夹中新建所需要的文件。
```bash
hexo init <folder>
cd <folder>
npm install
```

4. 新建完成后，指定文件夹的目录如下
```bash
├── _config.yml
├── package.json
├── scaffolds
├── source
|   ├── _drafts
|   └── _posts
└── themes
```

## _config.yml 文件

```bash
网站的 配置 信息，您可以在此配置大部分的参数。
```

## package.json 文件

应用程序的信息。EJS, Stylus 和 Markdown 渲染引擎 已默认安装，可以自由移除
```bash
{
  "name": "hexo-site",
  "version": "0.0.0",
  "private": true,
  "hexo": {
    "version": ""
  },
  "dependencies": {
    "hexo": "^3.8.0",
    "hexo-generator-archive": "^0.1.5",
    "hexo-generator-category": "^0.1.3",
    "hexo-generator-index": "^0.2.1",
    "hexo-generator-tag": "^0.2.0",
    "hexo-renderer-ejs": "^0.3.1",
    "hexo-renderer-stylus": "^0.3.3",
    "hexo-renderer-marked": "^0.3.2",
    "hexo-server": "^0.3.3"
  }
}
```

## scaffolds 文件夹

```bash
模版 文件夹。当您新建文章时，Hexo 会根据 scaffold 来创建文件。

Hexo 的模板是指在新建的文章文件中默认填充的内容。例如，如果您修改 scaffold/post.md 中的 Front-matter 内容，那么每次新建一篇文章时都会包含这个修改。
```

## source 文件夹
```bash
资源文件夹是存放用户资源的地方。除 _posts 文件夹之外，开头命名为 _ (下划线)的文件 / 文件夹和隐藏的文件将会被忽略。Markdown 和 HTML 文件会被解析并放到 public 文件夹，而其他文件会被拷贝过去。
```

## themes 文件夹
```bash
主题 文件夹。Hexo 会根据主题来生成静态页面
```


# hexo命令

## 基本命令

```bash
hexo s -g --debug # 热更新启动 修改配置文件需要重启生效
hexo serve # 启动服务 简写 hexo s
hexo generate # 打包静态文件 简写 hexo g
hexo deploy # 执行部署 简写 hexo d
```

## 新建文件

参数	描述
-p, --path	自定义新文章的路径
-r, --replace	如果存在同名文章，将其替换
-s, --slug	文章的 Slug，作为新文章的文件名和发布后的 URL

```bash
hexo new [layout] <title>
```

```bash
# 新建文件夹
hexo new page NewFileName 

# 新建文件
hexo new newFile
```



## 使用自己的域名访问

```bash
需要在根目录的 `source` 文件夹下创建 CNAME 文件, 在里面填入自己的域名即可
```