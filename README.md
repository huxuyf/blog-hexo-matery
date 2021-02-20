# Hexo+matery

> 使用Hexo搭建博客，并使用了matery这个模板



## 一、下载及安装

>  **Hexo**，[源码](https://github.com/hexojs/hexo) 

### 1、Hexo安装准备工作

前提条件：已安装好Node.js

```bash
npm install hexo-cli -g
npm install hexo-deployer-git --save
```

1. 安装Hexo；
2. 部署到Github上所需；

### 2、Hexo初始化

在D盘新建一个Hexo目录，并在里面执行如下命令：

```bash
hexo init
npm install
```

![Hexo初始化](https://cdn.jsdelivr.net/gh/huxuyf/images/20210220201538.png)



### 3、下载matery模板

[下载地址](https://codeload.github.com/blinkfox/hexo-theme-matery/zip/master)

下载后，解压，将文件`hexo-theme-matery-master`移动到Hexo的`themes`目录下（`D:\Hexo\themes`）



**注意：为保持前后一致，请将该文件夹改名为`matery`**



### 4、安装插件

```bash
npm install hexo-generator-search --save
npm i hexo-permalink-pinyin --save
npm i --save hexo-wordcount
npm install hexo-generator-feed --save
```

1. 搜索功能；
2. 中文链接转拼音；
3. 文章字数统计；
4. RSS订阅；

如果之前安装过prismjs，则需要卸载`npm uninstall hexo-prism-plugin`



### 5、新增一些文件

> 在Hexo根目录下执行

```bash
hexo new page "categories"
hexo new page "tags"
hexo new page "about"
hexo new page "contact"
hexo new page "friends"
hexo new page 404
```

1. 新增分类页；
2. 新增标签页；
3. 新增关于页；
4. 新增留言板页；
5. 新增友情链接页；
6. 新增404页



## 二、修改

### 1、Hexo配置文件的修改

> Hexo根目录下的`_config.yml`

#### 1.1 Site 站点信息

![](https://cdn.jsdelivr.net/gh/huxuyf/images/20210220205544.png)

这里大多是比较个性化的信息，请注意修改。

#### 1.2 URL 网页链接

![](https://cdn.jsdelivr.net/gh/huxuyf/images/20210220205808.png)

url是必改项



#### 1.3 Directory

保持不变



#### 1.4 Writing

![](https://cdn.jsdelivr.net/gh/huxuyf/images/20210220210126.png)

使用prismjs来高亮代码块，所以这里两处需要修改



#### 1.5 Home page setting

![](https://cdn.jsdelivr.net/gh/huxuyf/images/20210220211658.png)

因为matery这个模板的排版，需要每页的文章数应该是6的倍数。



#### 1.6 Category & Tag

保持不变



#### 1.7 Metadata elements

保持不变



#### 1.8 Date / Time format

保持不变



#### 1.9 Pagination

![](https://cdn.jsdelivr.net/gh/huxuyf/images/20210220212344.png)

同1.5



#### 1.10 Include / Exclude file(s)

保持不变



#### 1.11 Extensions 模板&插件设置

![](https://cdn.jsdelivr.net/gh/huxuyf/images/20210220212434.png)

这里设置模板为matery



#### 1.12 Deployment 部署

![](https://cdn.jsdelivr.net/gh/huxuyf/images/20210220212636.png)

Hexo部署到Github上的必要设置

#### 1.13 其他

以下是针对相应的插件新增的配置

```yaml
# 搜索
search:
  path: search.xml
  field: post

# 中文链接转拼音	
permalink_pinyin:
  enable: true
  separator: '-' # default: '-'

# 文章字数统计
wordCount:
  enable: false # 将这个值设置为 true 即可.
  postWordCount: true
  min2read: true
  totalCount: true

# 添加 RSS 订阅支持
feed:
  type: atom
  path: atom.xml
  limit: 20
  hub:
  content:
  content_limit: 140
  content_limit_delim: ' '
  order_by: -date
```



### 2、matery模板配置文件的修改

> matery目录下的`_config.yml`，具体路径：`D:\Hexo\themes\matery`

#### 2.1 一级菜单

![](https://cdn.jsdelivr.net/gh/huxuyf/images/20210220222023.png)

对应页面顶部右上角的菜单，可以根据需要取舍。

个人觉得**友情链接**不太有用，故注释掉。

![](https://cdn.jsdelivr.net/gh/huxuyf/images/20210220222145.png)

二级菜单默认是关闭的，我这里也没开启。



#### 2.2 站点运行开始时间

默认是关闭的，可以开启，并设置当前时间。

![](https://cdn.jsdelivr.net/gh/huxuyf/images/20210220222345.png)



#### 2.3 首页封面轮播图

保持默认



#### 2.4 配置首页显示

保持默认



#### 2.5 是否在首页显示音乐

默认是开启的，但我觉得没必要，关掉了。



#### 2.6 是否在首页显示视频

保持默认的关闭状态



#### 2.7 是否显示推荐文章的标题

保持默认



#### 2.8 配置网站favicon和网站LOGO

保持默认配置。但需要去替换掉`favicon.png`和`logo.png`两个文件。



#### 2.9 首页banner中的第二个按钮的配置

![](https://cdn.jsdelivr.net/gh/huxuyf/images/20210220223006.png)

将URL修改成自己的即可。



#### 2.10 首页个人信息配置

个人信息，修改成自己的。



#### 2.11 文章TOC功能

保持默认



#### 2.12 代码块相关

保持默认



#### 2.13 是否激活打赏功能

保持默认配置。但需要去替换掉`wechat.png`和``alipay.jpg`两个文件。



#### 2.14 是否激活复制功能

保持默认不开启。



#### 2.15 是否激活mathjax

保持默认不开启。



#### 2.16 字数统计等

![](https://cdn.jsdelivr.net/gh/huxuyf/images/20210220223439.png)

对应这块内容。根据自己需要开启或关闭。



#### 2.17 是否点击显示'爱心'效果

默认是开启的，但我觉得不好看关闭了。



#### 2.18 关于页面配置

关于页面也是个人信息，所以要修改。



myProjects，因为我没什么项目，所以关闭了。

![](https://cdn.jsdelivr.net/gh/huxuyf/images/20210220224353.png)

mySkillls，随便写点

![image-20210220224433066](C:\Users\user.ZJHUXUYF1Y\AppData\Roaming\Typora\typora-user-images\image-20210220224433066.png)

myGallery，关闭

![](https://cdn.jsdelivr.net/gh/huxuyf/images/20210220224442.png)

#### 2.19 归档页面配置

默认开启文章日历功能

![](https://cdn.jsdelivr.net/gh/huxuyf/images/20210220224257.png)



#### 2.20 留言功能

为了安全起见，全部保持默认的关闭状态。



#### 2.21 阅读文章密码验证功能

默认不开启



#### 2.22 不蒜子网站统计

默认开启，但出于效率考虑，关闭。



#### 2.23 副标题打字效果

觉得没必要，关闭



#### 2.24 ICP备案

因为没有备案，不启用。



#### 2.25 CDN访问加速 

开启



### 3、其他修改

**/source/categories/index.md**

```yaml
---
title: categories
date: 2021-02-20 20:48:57
type: "categories"
layout: "categories"
---
```

**/source/tags/index.md**

```yaml
---
title: tags
date: 2021-02-20 20:48:58
type: "tags"
layout: "tags"
---
```

**/source/about/index.md**

```yaml
---
title: about
date: 2021-02-20 20:48:59
type: "about"
layout: "about"
---
```

**/source/contact/index.md**

```yaml
---
title: contact
date: 2021-02-20 20:49:01
type: "contact"
layout: "contact"
---
```

**/source/friends/index.md**

```yaml
---
title: friends
date: 2021-02-20 20:49:02
type: "friends"
layout: "friends"
---
```

**/source/404/index.md**

```yaml
---
title: 404
date: 2021-02-20 20:49:06
type: "404"
layout: "404"
description: "Oops～，我崩溃了！找不到你想要的页面 :("
---

```



`source` 目录下新建 `_data` 目录，在 `_data` 目录中新建 `friends.json` 文件，文件内容如下所示：

```json
[{
    "avatar": "http://image.luokangyuan.com/4027734.jpeg",
    "name": "闪烁之狐",
    "introduction": "Matery的作者",
    "url": "http://blinkfox.com/",
    "title": "前去学习"
}, {
    "avatar": "https://godweiyang.com/medias/avatars/avatar.jpg",
    "name": "godweiyang",
    "introduction": "分享深度学习与NLP算法",
    "url": "https://godweiyang.com",
    "title": "前去学习"
}]
```



`/scaffolds/post.md`修改为如下代码：

```markdown
---
title: {{ title }}
date: {{ date }}
top: false
cover: false
password:
summary: 
categories: 
tags: 
---
```



| 属性名     | 默认值                    | 建议                             |
| ---------- | ------------------------- | -------------------------------- |
| title      | 自动生成                  | 不变                             |
| date       | 自动生成                  | 不变                             |
| img        | `featureImages`中的某一张 | 文章特征图，可以通过URL指定      |
| top        | true                      | 文章置顶，一般选false            |
| cover      | false                     | 是否加入首页轮播封面中           |
| coverImg   | 无                        | 如果cover=true，则需要指定封面图 |
| password   | 无                        | 一般不需要密码                   |
| toc        | true                      | 是否开启文章目录，建议关闭       |
| summary    | 无                        | 文章摘要                         |
| categories | 无                        | 文章分类，一篇文章只属于一个分类 |
| tags       | 无                        | 文章标签，一篇文章可以多个标签   |

