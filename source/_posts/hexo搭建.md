---
title: windows下hexo搭建
date: 2019-08-29 11:47:29
categories: hexo
tags:
   -hexo
---
#### 下载nodejs
 nodejs下载地址[下载](https://nodejs.org/en/)

#### 安装hexo
```
npm install -g hexo-cli

```

<!-- more -->

#### 构建hexo项目
  * 安装 Hexo 完成后，执行下列命令，Hexo 将会在指定文件夹中新建所需要的文件。
  ```
  $ cd <folder>
  $ npm install   安装nodejs的依赖到hexo目录下
  $ hexo init <folder>   初始化hexo项目
  ```
  * 新建完成后，指定文件夹的目录如下：
  ```
  .
  ├── _config.yml  网站的配置信息,可以在此配置大部分的参数,详细配置参考官网[配置](https://hexo.io/zh-cn/docs/configuration)
  ├── package.json
  ├── scaffolds  模版文件夹。当您新建文章时，Hexo 会根据 scaffold 来建立文件
  ├── source     资源文件夹，除 _posts 文件夹之外，开头命名为 _ (下划线)的文件 / 文件夹和隐藏的文件将会被忽略。Markdown 和 HTML 文件会被解析并放到 public 文件夹，而其他文件会被拷贝过去
  |   ├── _drafts
  |   └── _posts
  └── themes  主题目录，主题有自己的_config.yml文件，用来配置主题自己的属性
  ```
  * 编译开启web服务
   ```
    hexo g
    hexo s
    访问http://localhost:4000 即可看见项目

   ```

#### 构建时遇到的错误
  ```
    在执行hexo init <folder> 命令时 出现ERROR Local hexo not found in错误
    删除hexo目录下的node_modules文件 然后在hexo工程目录下重新执行npm install  安装nodejs依赖

  ```
