---
title: hexo主题的更换
date: 2019-08-29 13:45:29
categories: hexo
tags:
  -hexo
  -next
---

#### 主题主体安装设置
  * 这里以next主题为例，进入hexo项目目录，执行以下命令，从github上下载next主题,并将主题存放在themes目录的next文件夹下
    ```
    $ git clone https://github.com/theme-next/hexo-theme-next themes/next
    ```

    <!-- more -->
  * 更改主题
      ```
      项目主目录进入主目录，这里以hexo为例
      $ cd hexo
      打开该目录下的_config.yml文件
      将theme属性更改为
      theme: next
     ```
  * 更改主题文字为中文
      ```
      同上打开主目录下的_config.yml文件
      将language属性更改为
      language: zh-CN
      ```
  * 更改主题标题
    ```
    同上打开主目录下的_config.yml文件
    修改title标签为想要的标题
    title: 标题

    ```

#### 主题内部设置
  * 主题内部配置文件为themes/next目录下的_config.yml
  * 更改主题样式
    ```
      在主题配置文件中更改scheme属性来切换不同样式的主题
      #scheme: Muse
      #scheme: Mist
      scheme: Pisces
      #scheme: Gemini

    ```

  * 配置菜单找到menu标签
    以下配置在主要中打开主页，归档页，分类和标签
    如下图所示  
    ![按钮](menu.png)

    ```
    menu:
      home: /
      archives: /archives
      #about: /about
      categories: /categories
      tags: /tags
      #commonweal: /404.html
    ```
    每个标签的含义为

    |键值|	设定值	|显示文本（简体中文）|
    | ----| -----| ----|
    |home|	home: /|	主页|
    |archives|	archives: /archives|	归档页|
    |categories|	categories: /categories|	分类页|
    |tags|	tags: /tags|	标签页 |
    |about|	about: /about|	关于页面 |
    |commonweal	|commonweal: /404.html	|公益 404|

  * 配置标签和分类按钮  
      现在点击标签和分类按钮是无法使用的，下面进行标签和分类按钮的配置  
      标签按钮配置
      ```
        在hexo项目下执行
        hexo new page tags
        执行完成后在source\tags目录下生成index.md文件
        打开文件在标题中增加 type: "tags"
        如
        ---
        title: tags
        date: 2019-08-29 14:35:28
        type: "tags"
        ---
       ```
       配置分类按钮
      ```
        同上打开工程目录
        hexo new page categories
        打开文件在标题中增加 type: "categories"
        如
        ---
        title: categories
        date: 2019-08-29 14:43:25
        type: "categories"
        ---
       ```
#### 编写博客内容

    ```
      执行 hexo new 标题
      在source/_posts目录下会出现  标题.md文件
      打开文件 给博文添加分类和标签 categories，tags
      如下
      ---
      title: 标题
      date: 2019-08-29 13:45:29
      categories: hexo
      tags:
        -hexo
        -next
      ---
    这样这个博文就属于hexo分类，并且其有两个标签hexo和next
    现在进入首页点击分类和标签按钮即可按分类和标签找到该文章
    ```
#### 给文章配置图片
    ```
      在项目目录下安装插件
      $ npm install hexo-asset-image --save
      配置主配置文件_config.yml（项目根目录下非主题目录）
      post_asset_folder: true
      这样在执行 hexo new 标题   命令时会在source\_posts目录下建立一个对应文件夹
      把图片放入该目录即可
      然后可以使用md语法引用图片如
      ![按钮](menu.png)
    ```


#### 首页展示文章全文的问题
  * 首页中展示的文章是全文，这样导致首页非常的长，可以使用md语法在文章中加入 
  <!-- more -->来控制首页展示的长度
