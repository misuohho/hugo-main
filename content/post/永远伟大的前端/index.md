+++
date = '2025-02-21T22:11:30+08:00'
draft = true
title = '永远伟大的前端'

description = 'hugo + github 创建个人博客'

categories = [
    "编程" ,"学习"

]
tags = [
    "记录",
]

image = "girl.png"

+++

# Hugo ＋ GitHub 个人博客的建设

​	参考B站视频学习（<u>BV1bovfeaEtQ</u>）

​	hugo下载：前往hugo官网【  <u>**[The world’s fastest framework for building websites](https://gohugo.io/)**</u>  】

​	通过GitHub下载地址进行下载最新版

<img src="loading.png" style="zoom:200%;" />

​	通过Themes下载自己想要的主题

<img src="tags.png" style="zoom:200%;" />

​	点击tags，hugo版本选择extended版本，自己的操作系统与位数下载

​	themes直接下载最新的压缩包

<u>**[Tabler Admin Template: Responsive HTML Dashboard with Clean UI](https://tabler.io/admin-template)**</u>	SVG图标网站



## cmd控制台指令(hugo)

```
hugo new site 文件名
```

​	创建hugo的框架，其余依靠themes内主题模仿建立

```
hugo server -D
```

​	启动hugo的博客

```
hugo new content /content/post/文件夹名（blog内标题名）/文件名.md
```

​	创建文章文件夹解释

### assets

assets-img存放博客网站头像

assets-icons存放点击svg图片logo

### content 

**content-page**存放了左侧的点击栏【about-archives-links-search】

每一个文件夹对应一个栏，有的没有设置中文，需要修改title为中文



## 以下为hugo.yaml配置文件的解释

baseurl为博客网站地址

theme:博客主题名称

pagination:

    pagerSize: 3

博客每一页展示的文章数量

languages配置中撰写所需语言，需要考虑书写格式的缩进，会报告错

favicon为网站标签旁边的logo图标

avatar为博客头像

comment为文章下的评论（评论功能后续更新）

menu-social下配置可点击的小图标（跳转）

<img src="jietu/tubiao.png" style="zoom:100%;display: block; margin: 0 auto;" />

hugo配置文件中可以加入其他小组件（列如音乐播放器，评论功能）

可以在hugo的官方文档中查看【 [**<u>Welcome | Stack</u>**](https://stack.jimmycai.com/guide/) 】

------

## Github自动化部署

部署教程搜寻github自动化部署

以下为建立完成，进行代码更新操作

```
git add .
```

```
git commit -m "update"
```

```
git push
```



------

## 零碎的修改

### 布局修改

```scss
// 在 /assets/scss/grid.scss 中修改 left-sidebar 和 right-sidebar 的描述
.container {
    margin-left: auto;
    margin-right: auto;

    .left-sidebar {
        order: -3;
        // max-width: var(--left-sidebar-max-width);
        max-width: 10%;
    }

    .right-sidebar {
        order: -1;
        // max-width: var(--right-sidebar-max-width);
        max-width: 20%;
        /// Display right sidebar when min-width: lg
        @include respond(lg) {
            display: flex;
        }
    }
    // 文章左右部分占显示区域百分比修改成30%
```

### 归档页面两栏

```scss
@media (min-width: 1024px) {
    .article-list--compact {
      display: grid;
      grid-template-columns: 1fr 1fr;
      background: none;
      box-shadow: none;
      gap: 1rem;
  
      article {
        background: var(--card-background);
        border: none;
        box-shadow: var(--shadow-l2);
        margin-bottom: 8px;
        border-radius: 16px;
      }
    }
  }
```

### 归档页面卡片缩放

```scss
.article-list--tile article {
    transition: .6s ease;
  }
  
  .article-list--tile article:hover {
    transform: scale(1.03, 1.03);
  }
```

###  友情链接三栏

```scss
@media (min-width: 1024px) {
    .article-list--compact.links {
      display: grid;
      grid-template-columns: 1fr 1fr 1fr;
      background: none;
      box-shadow: none;
      gap: 1rem;
  
      article {
        background: var(--card-background);
        border: none;
        box-shadow: var(--shadow-l2);
        margin-bottom: 8px;
        border-radius: var(--card-border-radius);
  
        &:nth-child(odd) {
          margin-right: 8px;
        }
      }
    }
  }
```

### 主页布局间距调整

```scss
.main-container {
    gap: 50px; //文章宽度
  
    @include respond(md) {
      padding: 0 30px;
      gap: 40px; //中等屏幕时的文章宽度
    }
  }
  
  .related-contents {
    overflow-x: visible; //显示隐藏的图标
    padding-bottom: 15px;
  }
  /*------------------右侧导航栏--------------*/
```

### 搜索菜单动画

```scss
.search-form.widget {
    transition: transform 0.6s ease;
  }
  
  .search-form.widget:hover {
    transform: scale(1.1, 1.1);
  }
```

### 归档小图标放大动画

```scss
.widget.archives .widget-archive--list {
    transition: transform .3s ease;
  }
  
  .widget.archives .widget-archive--list:hover {
    transform: scale(1.05, 1.05);
  }
```

### 右侧标签放大动画

```scss
.tagCloud .tagCloud-tags a {
    border-radius: 10px;
    font-size: 1.4rem;
    transition: transform .3s ease;
  }
  
  .tagCloud .tagCloud-tags a:hover {
    transform: scale(1.1, 1.1);
  }
```

