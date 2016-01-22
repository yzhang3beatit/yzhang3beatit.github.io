---
layout: post
title:  "如何书写 Markdown 格式文本"
date:   2016-01-22
author: Zhang Yang
category: coach
tags: [open-source]
---

[toc]

<p class="intro"><span class="dropcap">M</span>arkdown 是一种轻量级标记语言，创始人为约翰·格鲁伯（John Gruber）。它允许人们“使用易读易写的纯文本格式编写文档，然后转换成有效的XHTML(或者HTML)文档”。这种语言吸收了很多在电子邮件中已有的纯文本标记的特性。</p>

## **兼容HTML**

Markdown 语法的目标是：成为一种适用于网络的书写语言。Markdown 的理念是，能让文档更容易读、写和随意改。HTML 是一种发布的格式，Markdown 是一种书写的格式。就这样，Markdown 的格式语法只涵盖纯文本可以涵盖的范围。 

 
不在 Markdown 涵盖范围之内的标签，都可以直接在文档里面用 HTML 撰写。不需要额外标注这是 HTML 或是 Markdown；只要直接加标签就可以了。  


要制约的只有一些 HTML 区块元素――比如 `<div>`、`<table>`、`<pre>`、`<p>` 等标签，必须在前后加上空行与其它内容区隔开，还要求它们的开始标签与结尾标签不能用制表符或空格来缩进。Markdown 的生成器有足够智能，不会在 HTML 区块标签外加上不必要的 `<p>` 标签。  


HTML 的区段（行内）标签如 `<span>`、`<cite>`、`<del>` 可以在 Markdown 的段落、列表或是标题里随意使用。依照个人习惯，甚至可以不用 Markdown 格式，而直接采用 HTML 标签来格式化。举例说明：如果比较喜欢 HTML 的 `<a>` 或 `<img>` 标签，可以直接使用这些标签，而不用 Markdown 提供的链接或是图像标签语法。


## **标题**

Markdown 支持两种标题方式：Setext 和 类atx形式

**Setext**：
>最高阶标题  
>`=======`

>第二阶阶标题  
>`-----`

效果如下
> 最高阶标题
> =======
> 第二阶阶标题
> ------

任何数目的`-`,`=`都可以 

**类atx**：
在行首插入1到6个`#`，分别表示6阶标题

># # 第一阶标题
>## ## 第一阶标题
>### ### 第一阶标题
>#### #### 第一阶标题
>##### ##### 第一阶标题
>###### ###### 第一阶标题 

## **段落与换行**

一个 Markdown 段落是由一个或多个连续的文本行组成，它的前后要有一个以上的空行（空行的定义是显示上看起来像是空的，便会被视为空行。比方说，若某一行只包含空格和制表符，则该行也会被视为空行）。普通段落不该用空格或制表符来缩进.   
如果你确实想要依赖 Markdown 来插入 `<br />` 标签的话，在插入处先按入两个以上的空格然后回车。

## **引用**

和email中的引用一样，就是在行首使用`>`表示引用的开始；连续多个`>`叠加表示多层引用
> `> 第一级引用`
>> `>> 第二级引用`

> ### `###引用中可以使用标题`
> 1. 列表一
> 2. 列表二
> 
>    return shell_exec("echo $input | $markdown_script");`

## **列表**

+ 无序列表可以直接使用 *、 +、 - 作为标记
+ 有序列表则使用： 数字加英文句点 作为标记
+ 所有标记后，必须要有空格或者制表符

写来是这样：

>
>        * 无序列表1
>        * 无序列表2
>          * 无序列表2.1
>        <空行>
>        1. 首先
>        2. 其次
>          2. 首先


看起来是这样

* 无序列表1
* 无序列表2
  * 无序列表2.1

1. 首先 
2. 其次
  2. 首先 


* 有序列表前的数字，并不和显示保持一致，偷懒的话，可以一直使用`1. `
* 标记可以缩进的1至3个空格
* 如果一个列表项目中包括多个段落，每个段落必须缩进4个空格或者1个制表符
  * 如果包含引用，`>`也需要缩进4个空格或者1个制表符
  * 如果包含代码引用，则需要缩进8个空格或者2个制表符

## **代码区块**

和程序相关的写作或是标签语言原始码通常会有已经排版好的代码区块，通常这些区块我们并不希望它以一般段落文件的方式去排版，而是照原来的样子显示，Markdown 会用 `<pre>` 和 `<code>` 标签来把代码区块包起来。

在markdown里只需要使用4个空格或者1个制表符就可以插入代码区块

Here is an example of AppleScript:

    tell application "Foo"
        beep
    end tell



## **分割线**

使用三个 *、-、`_` 可以建立一个分割线，本行内不能有其他东西，只能在符号间增加空格
例如：

    * * *
    ***
    ---
    *******
    ----------------



## **超链接**

### 行内式

Markdown：  

    `This is [an example](http://example.com/ "Title") inline link.`

看起来就是：  

This is [an example](http://example.com/ "Title") inline link.

### 参考式

Markdown:  

    `This is [an example][foo] reference-style link.`

    `[foo]: http://example.com/  "Optional Title Here"`


看起来就是：  

This is [an example][foo] reference-style link.

[foo]: http://example.com/  "Optional Title Here"

注意： foo是不区分大小写的


### 隐式链接

Markdown:  

    `Visit [Daring Fireball][] for more information.`

    `[Daring Fireball]: http://daringfireball.net`

看起来就是：
Visit [Daring Fireball][] for more information.

[Daring Fireball]: http://daringfireball.net


## **强调**


可以使用 * 或者 _ 来表示强调

    *single asterisks*

    _single underscores_

    **double asterisks**

    __double underscores__



*single asterisks*

_single underscores_

**double asterisks**

__double underscores__


 ~~strikethrough~~


## **代码**

可以使用**反引号**来包含包含代码

    Use the `printf()` function.
看起来就是：
Use the `printf()` function.


## **图片**

### 行内式

1. 找到图片外链
2. Markdown里插入图片即可：`![描述](图片链接)`
3. 例如：

    `![Alt text](/path/to/img.jpg "Optional title")`

### 参考式

    `![Alt text][id]`

例如：

    `[id]: url/to/image  "Optional title attribute"`


### 使用 `<img>` 标签


### Task list

- [ ] a bigger project
  - [x] first subtask
  - [x] follow up subtask
  - [ ] final subtask
- [ ] a separate task

[Task List Syntax](https://help.github.com/articles/writing-on-github/#task-lists)


``` C++
    // initialize ASFormatter member vectors
	formatterFileType = 9;		// reset to an invalid type
	headers = new vector<const string*>;
	nonParenHeaders = new vector<const string*>;
	preDefinitionHeaders = new vector<const string*>;
	preCommandHeaders = new vector<const string*>;
	operators = new vector<const string*>;
	assignmentOperators = new vector<const string*>;
	castOperators = new vector<const string*>;
```

[Code Formatting](https://help.github.com/articles/markdown-basics/#code-formatting)

### Tables and alignment

First Header | Second Header
------------ | -------------
Content from cell 1 | Content from cell 2
Content in the first column | Content in the second column


| Left-Aligned  | Center Aligned  | Right Aligned |
| :------------ |:---------------:| -----:|
| col 3 is      | some wordy text | $1600 |
| col 2 is      | centered        |   $12 |

[Table Syntax](https://help.github.com/articles/github-flavored-markdown/#tables)



### External

++insert++

==mark==

#### Subscript: H~2~O

You can also use inline math: `$H_2O$`


#### Superscript: 29^th^

You can also use inline math: `$29^{th}$`


#### Abbreviation

Markup is based on [php markdown extra](https://michelf.ca/projects/php-markdown/extra/#abbr) definition, but without multiline support:

*[HTML]: Hyper Text Markup Language
*[W3C]:  World Wide Web Consortium
The HTML specification
is maintained by the W3C.


#### Footnote

Here is a footnote reference,[^1] and another.[^longnote]

[^1]: Here is the footnote.

[^longnote]: Here's one with multiple blocks.

    Subsequent paragraphs are indented to show that they
belong to the previous footnote.


Here is an inline note.^[Inlines notes are easier to write, since
you don't have to pick an identifier and move down to type the
note.]

[Footnote Syntax](http://pandoc.org/README.html#footnotes)


#### Flowchart

```
graph TD
    A[Christmas] -->|Get money| B(Go shopping)
    B --> C{Let me think}
    C -->|One| D[Laptop]
    C -->|Two| E[iPhone]
    C -->|Three| F[Car]
```

[Flowchart Syntax](http://knsv.github.io/mermaid/#flowcharts-basic-syntax)

::: warning
Adding many flowcharts will slow down the editor.
:::


#### Sequence diagram

```
sequenceDiagram
    loop every day
        Alice->>John: Hello John, how are you?
        John-->>Alice: Great!
    end
```

[Sequence Diagram Syntax](http://knsv.github.io/mermaid/#sequence-diagrams)

::: warning
Adding many sequence diagrams will slow down the editor.
:::
