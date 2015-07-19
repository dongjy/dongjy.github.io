---
layout: post
title: jekyll学习
---
jekyll 学习
- 配置
>配置不能使用tab，否则可能被忽略。

**_config.yml**

jekyll 的全局配置

**_includes**

网站的头部，底部，侧栏等公共部分。

    {% include filename %}

**_layouts**

对于网站的布局,我们一般会写成模板的形式。模板可以多层嵌套。模板中引入儿子内容。

    {{ content }}

>必须在子节点顶部。

    ---
    layout:post
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

****全局变量配置****

- 源代码位置

    source: DIR 
> 也可在编译时指定 -s, --source DIR

- 输出网站位置 

    destination: DIR 
 >编译参数 -d, --destination DIR