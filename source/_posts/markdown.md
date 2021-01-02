---
title: Markdown syntax
tags:
  - markdown
  - GitHub
  - blog
  - hexo
  - git
categories: markdown
description: Markdown's usage syntax
keywords: [markdown, github, gitee, osc, opensource, blog, blogger, hexo]
date: 2020-03-22 11:45:15
---

![](https://cdn.bmyjacks.io/img/20200322113727.jpg?x-oss-process=style/style)

## Titles
```markdown
# First level title
## Second level title
### Third level title
#### Fourth level title
##### Fifth level title
###### Sixth level title
```

### Third level title
#### Fourth level title
##### Fifth level title
###### Sixth level title

## Paragraphs
```markdown
This is the first paragraph  
This is the second paragraph

This is the third paragraph
```

This is the first paragraph  
This is the second paragraph
This is the third paragraph

## Typeface
```markdown
*Italics*
_Italics_
**Bold**
__Bold__
***Bold italics***
___Bold italics___
```

*Italics*
_Italics_
**Bold**
__Bold__
***Bold italics***
___Bold italics___

## Splitters
```markdown
***

* * *

*****

- - -

----------
```

***
* * *
*****
- - -
----------

## Strikethrough

```markdown
~~This is the strikethrough~~
```

~~This is the strikethrough~~

## Underline

```markdown
<u>This is the underline</u>
```

<u>This is the underline</u>

## Annotations
```markdown
This is the [^text] to mark.
[^text] : This is the content
```

{% note info %}
#### info
Due to the limitation of blog, we can't display annotations. Sorry.
{% endnote %}

## Lists
### Unordered lists
```markdown
* 1
* 2
* 3

+ 1
+ 2
+ 3

- 1
- 2
- 3
```

* 1
* 2
* 3
+ 1
+ 2
+ 3
- 1
- 2
- 3

### Ordered lists

```markdown
1. 1
2. 2
3. 3
```

1. 1
2. 2
3. 3

### Lists nesting
```markdown
1. 1
    - 1.1
    - 1.2
2. 2
    - 2.1
    - 2.2
```

1. 1
    - 1.1
    - 1.2
2. 2
    - 2.1
    - 2.2

## Blocks
### Standard blocks
```markdown
> 1
> 2
> 3
```

> 1
> 2
> 3

### Nested blocks
```markdown
> 1
>> 2
>>> 3
```

> 1
>> 2
>>> 3

## Code
{% note warning %}
### Warning
Due to the limitation of code representation in this blog, I suggest you use the following website to query the code format of Markdown.[https://github.github.com/gfm/#code-spans](https://github.github.com/gfm/#code-spans)
{% endnote %}

## Links
### Standard links
```markdown
[Text link](Link address)
![Picture alt](Link address)
```

[TextLink](https://www.bmyjacks.com/2020/markdown.html#TextLink)
![Pictures linking](https://cdn.bmyjacks.io/img/20200322144321.png?x-oss-process=style/style)

### Advanced links
```markdown
This is an [advanced link][1]
Then assign a value to the variable at the end of the article
[1](Link address)
```

{% note info %}
#### info
Due to the limitation of blog, we can't display advanced links. Sorry.
{% endnote %}

## Forms
### Drawing Forms
```markdown
| Header | Header |
| ------ | ------ |
| Cell   | Cell   |
| Cell   | Cell   |
```

| Header | Header |
| ------ | ------ |
| Cell   | Cell   |
| Cell   | Cell   |

### Alignment
```markdown
| Left alignment         | right alignment             | Center alignment         |
| :--------------------- | --------------------------: | :----------------------: |
| This is left alignment | This is the right alignment | This is center alignment |
| This is left alignment | This is the right alignment | This is center alignment |
```

{% note info %}
#### info
Due to special reasons, this blog can not display the alignment table.Sorry.
{% endnote %}

## Buttoms
```markdown
This is <kbd>Ctrl</kbd>和<kbd>enter</kbd>
```
This is a<kbd>Ctrl</kbd>和<kbd>enter</kbd>

## Escape symbols
```markdown
Insert a backslash\ before the following characters to help paraphrase
\   backslash
`   backquote
*   asterisk
_   underline
{}  curly brackets
[]  square brackets
()  parentheses
#   #
+   plus sign
-   minus sign
.   English period
!   exclamatory mark
```

\\ backslash
\` backquote
\* asterisk
\_ underline
\{} curly brackets
\[] square brackets
\() parentheses
\# #
\+ plus sign
\- minus sign
\. English period
\! exclamatory mark

## Mathematical formulas and images
It needs to be supplemented.
