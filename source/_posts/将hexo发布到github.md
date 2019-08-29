---
title: 将hexo发布到github
date: 2019-08-29 15:17:40
categories: hexo
tags:
  -hexo
  -next
  -github
---

#### 创建一个github仓库
      * 创建一个github公有仓库,点击settings如图  
      ![settings](github1.png)
      * 选择GitHub Pages选项  设置git分支为，和访问域名
      ![githubpage](github2.png)

<!-- more -->

#### 设置hexo部署目录  

      ```
      打开项目目录下的_config.yml文件
      修改deploy:属性
      type 为类型设置为git
      branch设置为master分支
      repo为你的仓库地址
      如

      deploy:
      type: git
      branch: master
      repo: https://
      ```


  * 参数解释  
      | 参数	| 描述 |
      | ----- | ----- |
      | repo	 | 库（Repository）地址 |
      | branch |	分支名称。如果不指定，则默认值为 master |
      | message |	自定义提交信息,非必须  |



  #### 安装部署插件
  ```
    进入项目主目录执行
    $ npm install hexo-deployer-git --save


  ```

  #### 发布项目至github pages
  ```
    $ hexo clean
    $ hexo g
    $ hexo d


  ```

  #### 解决样式丢失问题
  * 此时发布项目至github，css样式会丢失修改以下内容  

  ```
    打开项目目录下的_config.yml文件
    修改如下参数
    url: https://liushprofessor.github.io/liushaohuang.github.io/
    root: /liushaohuang.github.io/
    permalink: :year/:month/:day/:title/
    permalink_defaults:

    其中url替换为你github的仓库地址
    root替换为你的仓库名
    重新发布解决问题
  ```
