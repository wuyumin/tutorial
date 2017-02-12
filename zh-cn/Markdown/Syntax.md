# 简介

这个文档本身就是使用 Markdown 编写的。  
Markdown 允许你通过编写易读、易写的富文本格式，然后很方便就可以转换成有效的 HTML。  
文件后缀名一般为`.md`或`.markdown`。

# 标准 Markdown 语法

### 标题

**atx 格式**(尾部的`#`是可选的)

```markdown
# 标题1
# 标题1 #
## 标题2
###### 标题6
```

**Setext 格式**

```markdown
标题1
========

标题2
--------
```

### 强调或突出

```markdown
*突出*   **强调**
_突出_   __强调__
```

### 链接

内联风格(`title`是可选的)
```markdown
[海互网](https://www.089858.com "title")
```

引用风格(`title`是可选的)
```markdown
[海互网][id]

之后，可以在文档的其它任意地方, 定义这个链接：
[id]: https://www.089858.com "title"
```

### Email

```markdown
电子邮箱 <xxx@xxx.com>
```

技巧：纯网址链接尽量使用尖括号`<>`包含网址更好一些，没有必要使用`[](网址)`这种形式。

### 图片

跟链接类似，但比链接前面多了个`!`。

内联风格(`title`是可选的)
```markdown
![alt text](/path/img.jpg "title")
```

引用风格(`title`是可选的)
```markdown
![alt text][id]

[id]: /url/to/img.jpg "title"
```

### 列表

> 切记：数字与列表项之间有空格。

有序列表：

```markdown
1. 列表项1
2. 列表项2
```

无序列表：

```markdown
- 列表项1
- 列表项2

* 列表项1
* 列表项2
```

> 列表项缩进两个空格就可以创建一个嵌套的列表。

```markdown
1. 列表项1
  1. 嵌套的列表可以是有序的
  2. 格式和正常的有序、无序列表没有差异
2. 列表项2
  * 嵌套的列表可以是无序的
    * 这个嵌套的列表项有4个空格的缩进，因为它的父列表项自身就带有2个空格的缩进
    * 还允许更多层的嵌套
3. 列表项3
```

### 引用

```markdown
> 段落前面添加大于号和空格，就能够形成引用段落。

> > 这是嵌套的引用。
```

### 内联代码

```markdown
`内联代码`使用反引号包含

你也可以像`` `这样` ``转义反引号
```

### 代码块

每行缩进4个空格或者1个 tab。

```markdown
这是一个正常的段落。

    这是代码块。
```

### 水平分割线

三个或更多的星号或横杠：

```markdown

---

* * *

******

- - - -
```

### 强制换行

在行尾输入两个空格：

```markdown
这句话
不会
换行

这句话  
会  
换行
```

# GitHub Flavored Markdown(简称GFM) 语法

是 Github 基于 Markdown 拓展的一种纯文本的书写格式。

### 链接自动展示

你可以直接输入链接地址，它可以直接识别这个链接。

```markdown
https://www.089858.com
```

### 删除线

通过两个波浪号将字符包含：

```markdown
~~错误的文本~~
```

### 围栏式代码块

````markdown
```语言名
标准的 Markdown 通过每行开头的4个空格将文本转换成代码块，而 GFM 支持围栏式代码块。只要将代码用 ``` 包含起来即可，不需要4个空格的缩进。
```
````
[点此查看 Markdown 代码块高亮支持的语言](Syntaxhighlighting.md)

### 表格

这是个简单的表格：

```markdown
First Header | Second Header | Third Header
------------ | ------------- | ------------
Content Cell | Content Cell  | Content Cell
Content Cell | Content Cell  | Content Cell
```

出于美观的考虑, 可以把两端都包围起来：

```markdown
| First Header | Second Header | Third Header |
| ------------ | ------------- | ------------ |
| Content Cell | Content Cell  | Content Cell |
| Content Cell | Content Cell  | Content Cell |
```

通过在标题分割行添加冒号 `:` ,你可以定义表格单元的对齐格式：向左靠齐，居中和向右靠齐：

```markdown
| First Header | Second Header | Third Header |
| :----------- | :-----------: | -----------: |
| Left         | Center        | Right        |
| Left         | Center        | Right        |
```

# 技巧
- 段首空格的显示：使用全角空格，切换到全角模式下（一般的中文输入法都是按 shift + space）输入两个空格就行了。

# Markdown 参考资料
- 创始人 John Gruber 的 Markdown 语法说明 <http://daringfireball.net/projects/markdown/syntax>
- GitHub 的 Markdown 参考 <https://guides.github.com/features/mastering-markdown>
- Markdown 中文语法说明
  * <http://wowubuntu.com/markdown>
  * <https://segmentfault.com/markdown>