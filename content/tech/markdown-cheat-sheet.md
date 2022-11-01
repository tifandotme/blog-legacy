+++
title = 'Markdown Cheat Sheet'
description = 'Full markdown cheat sheet. Use this as reference 😀'
tags = ['markdown','reference']
date = 2022-10-30T14:05:07+07:00
draft = true
+++

| Syntax      | Description | Test Text  markdown   |
| :---        |    :----:   |          ---: |
| Header      | Title markdo asd as  dasd <br>asdwnasd   asd     | Hereasdasd as markn|
| Paragraph markdown  | Text        | And more      |

> I am testing out markdown syntax for this site. And beware, I am going to use the word "reference" a lot.

# 1. Reference's Reference (oh god)

- [Matt Cone\'s (Basic Syntax)](https://www.markdownguide.org/basic-syntax/)
- [Matt Cone\'s (Extended Syntax)](https://www.markdownguide.org/extended-syntax//)

# 2. Heading

# Big title (h1)
## Middle title (h2)
### Smaller title (h3)
#### and so on (h4)
##### and so on (h5)
###### and so on (h6)

> Best practice: Space after hash

## 2.1 Alternate Heading

Heading level 1
===============

Heading level 2
---------------

# 3. Paragraph

I really like using Markdown.

I think I'll use it to format all of my documents from now on. 

> Best practice: Don't add tabs or spaces before in front of paragraph

# 4. Line Break

To create a line break or new line (\<br\>), end a line with two or more spaces, and then type return.  
Another line

# 5. Text basics

this is *italic* and this is **bold** .  another _italic_ and another __bold__. 

this is `important` text. and percentage signs : % and `%`

This is a paragraph with a footnote (builtin parser only). [^note-id]

Insert `[ TOC ]` without spaces to generate a table of contents (builtin parsers only).

## 6. Blockquote

> Here is some indented text
>> even more indented


# 7. Example lists (1)

- bullet can be
- bullet list 1
- bullet list 2
    * bullet list 1  
    with indented text inside

* This is the first list item.
* Here's the second list item.  
    I need to add another paragraph below the second list item.
* And here's the third list item.

# 8. Links

This is an [example inline link](http://lmgtfy.com/) and [another one with a title](http://lmgtfy.com/ "Hello, world").

Links can also be reference based : [reference 1][ref1] or [reference 2 with title][ref2].

References are usually placed at the bottom of the document

My favorite search engine is [Duck Duck Go](https://duckduckgo.com "The best search engine for privacy").

<https://www.markdownguide.org>
<fake@example.com>

In a hole in the ground there lived a hobbit. Not a nasty, dirty, wet hole, filled with the ends
of worms and an oozy smell, nor yet a dry, bare, sandy hole with nothing in it to sit down on or to
eat: it was a [hobbit-hole][1], and that means comfort.

[1]: <https://en.wikipedia.org/wiki/Hobbit#Lifestyle> "Hobbit lifestyles"


# 9. Horizontal Line

test

***

test

---

_________________

> Best Practice: Try to put a blank line before and after a horizontal rule. 

# 10. Images

A sample image :

![revolunet logo](http://www.revolunet.com/static/parisjs8/img/logo-revolunet-carre.jpg "revolunet logo")

As links, images can also use references instead of inline links :

![revolunet logo][revolunet-logo]


## Code

It's quite easy to show code in markdown files.

Backticks can be used to `highlight` some words.

Also, any indented block is considered a code block.  If `enable_highlight` is `true`, syntax highlighting will be included (for the builtin parser - the github parser does this automatically).

```javascript
<script>
    document.location = 'http://lmgtfy.com/?q=markdown+cheat+sheet';
<\/script>
```





Here's a simple footnote,[^1] and here's a longer one.[^bignote]

[^1]: This is the first footnote.

[^bignote]: Here's one with multiple paragraphs and code.

    Indent paragraphs to include them in the footnote.

    `{ my code }`

    Add as many paragraphs as you like.