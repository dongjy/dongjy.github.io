---
layout: post
title: markdown语法
---
markdown语法

- 基本

单个回车
视为空格。

连续回车

才能分段。

行尾加两个空格，这里->  
即可段内换行。


- 标题

Markdown 支持两种标题的语法，Setext 和 atx 形式。Setext 形式是用底线的形式，利用 = （最高阶标题）和 - （第二阶标题），Atx 形式在行首插入 1 到 6 个 # ，对应到标题 1 到 6 阶。

一阶标题
===
二阶标题
---
#一阶标题
##二阶标题
- 修辞和强调

*这些文字显示为斜体*

**这些文字显示为粗体**

- 列表
--- --
三个或更多-_*，必须单独一行，可含空格
> 引用
>>引用中的引用

*符号之后的空格不能少，\-\+\*效果一样，但不能混合使用，因混合是嵌套列表，内容可超长*

- 无序列表
- 无序列表
- 无序列表


1. 有序列表
2. 有序列表
3. 有序列表
8. 有序列表


- 嵌套列表  
 + 嵌套列表  
 + 嵌套列表  
  - 嵌套列表  
   * 嵌套列表  
- 嵌套列表  

- 链接

[董军阳博客](www.dongjy.github.io)  
- 图片

![markdown简洁语法]({{site.baseurl}}/images/markdown-syntax.png)  
**索引**  
[董军阳][1]  
![董军阳][2]

[1]:http://dongjy.github.io  
[2]:{{site.baseurl}}/images/markdown-syntax.png

**自动链接**  
<http://dongjy.github.io>  
<http://dongjy.github.io>

- 代码

行的开头空4个空格，表示程序代码，例如：  
C#:

    public class Blog
    {
         public int Id { get; set; }
         public string Subject { get; set; }
    }
Javascript:

    function fib(n) {
        var a = 1, b = 1;
        var tmp;
        while (--n >= 0) {
            tmp = a;
            a += b;
           b = tmp;
        }
        return a;
    }

    document.write(fib(10));

	
[查看源码](https://github.com/dongjy/dongjy.github.io/edit/master/_posts/2015-07-19-markdown-syntax.md)