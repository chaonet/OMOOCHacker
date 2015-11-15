# Markdown 教程
## 源起
一种标记语言，可以用易读易写的纯文本格式编写文档，转换为HTML文档。

### 运用场景
* 项目文档
* 博客
* 个人创作
* 自助出版
* 科学写作

### 编辑器
- macdown，仅 mac
- MWeb Lite(免费)/MWeb
- DILLINGER，网页版，可以链接网盘，支持文档的转换、导出

## 语法
### 标题
一共六级，以「#」数量递增

\# a  
\## a  
\### a  
\#### a  
\##### a  
\###### a


# a
## a
### a
#### a
##### a
###### a

### 索引
\[索引](#link)  

[索引](#link)

### 换行，空格
#### 行末两个空格  
aaa  
aaa  
aaa  
aaa

#### 双回车
aaa

aaa

### 分隔符
**\*
***

\* * *
* * *

--\-破折号
---

__\_，下划线
___

### 没有超链接的注脚
Text prior to footnote reference.[^2]

[^2] Comment to include in footnote.

### 代码块
#### 制表符

	aaa
	
#### 四个空格

    aaa

#### code
\<code>  
import os  
\</code>

<code>
import os
</code>

#### 三个「`」

```
def ():
```

#### 前后各一个「`」

`aaaa`

#### 开头四个空格

    aaaa

### 链接

1. 基本[link name](link)  
[google](http://www.google.com)
2. 参考链接: 文中[link name][ID], 文末[ID]:link  
[test\][1\]  
[google][1]

3. 自动链接 ,主要是短网址、邮箱  
<http://www.google.com>，格式:<http://www.google.com\>

### 表格
由「|」和「-」构成

第二行中间由连续至少三个连字符组成

第二行的冒号:对齐方式，排版

#### 第一种

\|aaaa|bbbb|cccc|  
\|:---:|:---|---:|  
\|d|e|f|

|aaaa|bbbb|cccc|
|:---:|:---|---:|
|d|e|f|

#### 第二种

aaaa|bbbb|cccc  
\:---:|:---|---:  
d|e|f

aaaa|bbbb|cccc
:---:|:---|---:
d|e|f

### 图片
#### 基本形式  
![](http://i.imgur.com/5kxDajk.jpg?1)

#### 索引形式  
![pic name](http://i.imgur.com/wsXwFQ1.jpg?1)

#### 图片居中显示
makedown 可以直接调用 HTML 语言

\<center>...\</center>

\<center>  
\!\[pic name](pic link)  
\</center>

<center>  
![pic name](http://i.imgur.com/5kxDajk.jpg?1)  
</center>

\<figure>...\</figure>, 必须使用 HTML 的形式引用。\<img src="http://xxx">

\<figure>  
   \<img src="http://xxx.jpg">  
\</figure>

<figure>  
    <img src="http://i.imgur.com/wsXwFQ1.jpg?1">
</figure>

### 引用
#### 对整段文字的引用
只需在段落开头添加「>」，段落间需要空行
>Markdown具有一系列衍生版本，用于扩展Markdown的功能（如表格、脚注、内嵌HTML等等），这些功能原初的Markdown尚不具备，它们能让Markdown转换成更多的格式，例如LaTeX，Docbook。Markdown增强版中比较有名的有Markdown Extra、MultiMarkdown、 Maruku等。这些衍生版本要么基于工具，如Pandoc；要么基于网站，如GitHub和Wikipedia，在语法上基本兼容，但在一些语法和渲染效果上有改动。

#### 诗歌每行的引用
每行前面添加「>」，末尾加两空格用于换行
>如何让你遇见我  
>在我最美丽的时刻  
>为这  
>我已在佛前求了五百年  
>求它让我们结一段尘缘  
>佛于是把我化作一棵树  
>长在你必经的路旁  

#### 嵌套引用
\>Markdown  
\>>一种标记语言

>Markdown
>>一种标记语言

### 列表
#### 无序列表
「+」「-」「*」开头，加一个空格，可以缩进三个空格嵌套

+ a1
   + aa1
+ b1

- a2
   - aa2
- b2

* a3
   * aa3
* b3


#### 有序列表

1. a
2. b
3. c

### 强调
*a\*

*a*

_a\_

_a_

**aaaa\*\*

**aaaa**

__aaaa\_\_

__aaaa__

___aaa\_\_\_

___aaa___

***aaa\*\*\*

***aaa***

### 转义

*a\\\*

*a\*

## `macdown`快捷键

dfasfsdaf**dfdfd**,`command+b`

sfsfd`fdfd`,`command+k`

*aaa*,`command+i`

<!--hihi-->,`command+/`

\标题, `command+1~6`,`command+0`取消


\* `shift+command+u`,再次按取消


\> `shift+command+b`

\[](link),`shift+command+k`,再次按不会取消

\![](image),`shift+command+i`


`command+return`,换行

## 中文写作风格
### 空格
1. 中英文之间加空格；
2. 中文与数字之间加空格；
3. 数字与单位之间加空格(气温与百分比计量单位等除外)；
4. 全角标点(中文输入下的 逗号、句号、冒号 等)与其他字符之间不空格；
5. 英文内容，输入逗号和句号后添加一个半角空格；
6. 段落开头不留空格，段落之间空一行进行分隔

### 符号
1. 中文或中英文混排中，用中文/全角标点；
2. 数字、英文用半角字符；
3. 出现整句英文，该句用英文/半角标点；
4. 中文使用直角引号。直角引号包括「」、『』。先单后双(与“”、‘’相反)
5. 不重复使用标点符号；
6. 省略号：「......」。不要使用「...」、「。。。」替代。

### 拼写
1.专用名词大小写使用；Google，GitHub
2.缩写要准确，使用公认用法；
3.长数字的输入，从小数点开始相左，每三位一组，组间空格。金额: 1 234 567

### 索引
\<a name="link"></a>
<a name="link"></a>

## 扩展
### 图床
保存图片，可用于分享、引用。要求长期、稳定

#### 七牛。
登录 七牛，`选择一个空间`，选择、`新建空间`，选择`公开空间`。`内容管理`,`上传`。

#### imgur.com。
- 登录
- 上传
   - 点击左上角`upload images`，`browse your computer`，选择电脑中的图片，`打开`，在`imgur`中选中图片，`start upload`上传，此时可以编辑图片，然后`save`。
   - 可以通过`browse your computer`一次选择多个图片，会创建一个相册，可以选择进行`命名`，一起上传。
- 得到 直接连接
   - 点击图片右侧`Direct Link`下的`copy`图标
   - 或 点击右上角用户名，选择`images`，选择图片，点击`Direct Link`下的`copy`图标。编辑图片，然后`save`。
   - 或 进入相册，将鼠标移至图片右上角`。。。`，点击`Direct Link`下的`copy`图标。

#### photobucket.com

### chrome 扩展
#### copy as markdown
将网址链接复制为 markdown 语法格式

#### markdown here
在邮件或其他可以用到 makedown 文档时，将 makedown 语法内容转换为 HTML 形式的呈现

## 其他
论文写作平台`authorea.com`= LaTeX + git + Markdown

`Remarkjs`,一个 JavaScript 库，利用它，可以使用 Markdown 格式来制作幻灯片


[1]:http://www.google.com

