---
layout: post
title: jekyll学习
---
jekyll 学习

##配置

>配置不能使用tab，否则可能被忽略。

**_config.yml**

jekyll 的全局配置

**_includes**

网站的头部，底部，侧栏等公共部分。

![15][15]

>“\” 转义,在代码块中无效

**_layouts**

对于网站的布局,我们一般会写成模板的形式。模板可以多层嵌套。模板中引入儿子内容。

![16][16]

>必须在子节点顶部。

    ---
    layout:posts
    ---

**_post**

写的内容，一般作为叶子节点。

**_data**

也用于配置一些全局变量，因为数据过多，所以单独存放。

比如多人开发模式，我们定义一个members.yml文件

文件内容为

    name: dongjunyang
    github: dongjy

模板中我们可以用下面语法：

    site.data.members

**_site**

jekyll 生成网站输出的地方。一般加入.gitignore

**index.html**

主页文件

***全局变量配置***

- 源代码位置

    source: DIR 
> 也可在编译时指定 -s, --source DIR

- 输出网站位置 

    destination: DIR 
 >编译参数 -d, --destination DIR

- safe开关

    safe:BOOL
> 编译参数 --safe

- 忽略文件

    exclude: [DIR,FILE,...]

- 强处理文件

    include: [DIR,FILE,...]
- 时区

    timezone: TIMEZONE

> timezone: Asia/Shanghai

- 编码

    encoding: ENCODING

>encoding: utf-8

##模板语法

    ---
    layout: post
    title: title
    category: blog
    description: description
    published: true #default
    ---

**全局节点有：**

- _config.yml
- page页面配置
- content 引入子节点
- paginator 分页

**site 下的变量**

- site.time 运行 jekyll 的时间
- site.pages 所有页面
- site.posts 所有文章
- site.related_posts 类似的10篇文章,默认最新的10篇文章,指定lsi为相似的文章
- site.static_files 没有被 jekyll 处理的文章,有属性 path, modified_time 和 extname.
- site.html_pages 所有的 html 页面
- site.collections 新功能,没使用过
- site.data _data 目录下的数据
- site.documents 所有 collections 里面的文档
- site.categories 所有的 categorie
- site.tags 所有的 tag
- site.[CONFIGURATION_DATA] 自定义变量


**page 下的变量**

- page.content 页面的内容
- page.title 标题
- page.excerpt 摘要
- page.url 链接
- page.date 时间
- page.id 唯一标示
- page.categories 分类
- page.tags 标签
- page.path 源代码位置
- page.next 下一篇文章
- page.previous 上一篇文章


**paginator 下的变量**

- paginator.per_page 每一页的数量
- paginator.posts 这一页的数量
- paginator.total_posts 所有文章的数量
- paginator.total_pages 总的页数
- paginator.page 当前页数
- paginator.previous_page 上一页的页数
- paginator.previous_page_path 上一页的路径
- paginator.next_page 下一页的页数
- paginator.next_page_path 下一页的路径


**输出变量：**

![输出变量][17]

**循环：**

![循环][1]

**自动生成摘要：**

![自动生成摘要][2]

**删除指定文本：**

![删除指定文本][3]

**删除html标签**

![删除html标签][4]

**代码高亮**

![代码高亮][5]

**数组大小**

![数组大小][6]

**赋值**

![赋值][7]

**格式化时间**

![格式化时间][8]

**搜索指定key**

![搜索指定key][9]

**排序**

![排序][10]

**to json**

![to json][11]

**序列化**

![序列化][12]

**单词个数**

![单词个数][13]

**指定个数**

![指定个数][14]

[查看源码](https://github.com/dongjy/dongjy.github.io/edit/master/_posts/2015-07-20-jekyll-what.md)

[1]:{{ site.baseurl }}/images/jekyll_1.png
[2]:{{ site.baseurl }}/images/jekyll_2.png
[3]:{{ site.baseurl }}/images/jekyll_3.png
[4]:{{ site.baseurl }}/images/jekyll_4.png
[5]:{{ site.baseurl }}/images/jekyll_5.png
[6]:{{ site.baseurl }}/images/jekyll_6.png
[7]:{{ site.baseurl }}/images/jekyll_7.png
[8]:{{ site.baseurl }}/images/jekyll_8.png
[9]:{{ site.baseurl }}/images/jekyll_9.png
[10]:{{ site.baseurl }}/images/jekyll_10.png
[11]:{{ site.baseurl }}/images/jekyll_11.png
[12]:{{ site.baseurl }}/images/jekyll_12.png
[13]:{{ site.baseurl }}/images/jekyll_13.png
[14]:{{ site.baseurl }}/images/jekyll_14.png
[15]:{{ site.baseurl }}/images/jekyll_15.png
[16]:{{ site.baseurl }}/images/jekyll_16.png
[17]:{{ site.baseurl }}/images/jekyll_17.png

