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

    {% include filename %}
\{% include filename %\}
>“\” 转义 但不可放在代码块中

**_layouts**

对于网站的布局,我们一般会写成模板的形式。模板可以多层嵌套。模板中引入儿子内容。

    {{ content }}

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

\{{ page.title }\}

**循环：**

    {% for post in site.posts %}
        <a href={{site.baseurl}}{{post.url}} >{{ post.title }}</a>
    {{ endfor }}

**自动生成摘要：**

    {% for post in site.posts %}
        {{ post.url }} {{post.title}}
        {{ post.excerpt | remove: 'test' }}
    {% endfor %}

**删除指定文本：**

    {{ post.url | remove: 'http'}}

**删除html标签**

    {{ post.excerpt | scrip_html }}

**代码高亮**

    {% highlight ruby linenos %}
    \#some ruby code
    {% endhighlight %}

**数组大小**

    {{ array | size }}

**赋值**

    {% assign index = 1 %}

**格式化时间**

    {{ site.time | date_to_xmlschema }}
    {{ site.time | date_to_rfc822 }}
    {{ site.time | date_to_string }}
    {{ site.time | date_to_long_string }}

**搜索指定key**

    {{ site.members | where: "graduation_year","2014" }}

**排序**

    {{ site.pages | sort: 'title','last' }}

**to json**

    {{ site.data.projects | jsonify }}

**序列化**

    {{ page.tags | array_to_sentence_string }}

**单词个数**

    {{ page.content | number_of_words }}

**指定个数**

    {% for post in site.posts limit:20 %}

