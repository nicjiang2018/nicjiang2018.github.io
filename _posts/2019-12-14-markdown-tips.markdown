---
layout:     post
title:      "Markdown 如何在code block里显示行号"
#subtitle:   " \"Hello World, Hello Blog\""
date:       2019-12-04 12:00:00
author:     "Nicole"
header-img: "img/post-bg-2015.jpg"
tags:
    - Markdown
---



>软件：Sublime Text 3（MacOS）

一些时候我们需要显示代码同时，能够把行号也显示出来，增加代码的易读性。

<img class="shadow" width="600" src="/img/191204g.png" />

Step 1: 打开Sublime Text 3里的markdown preview setting文件，点击`Sublime Text`->`Preferences` -> `Package Settings` -> `Markdown Preview`->`Settings`

<img class="shadow" width="600" src="/img/191204a.png" />

打开后，就会看见左右两个文件窗口，左侧窗口是自带的默认设置`MarkdownPreview`，右侧窗口是用户自定义设置`User`

<img class="shadow" width="600" src="/img/191204b.png" />

Step 2: 在左侧`MarkdownPreview`文件，搜索关键词 *“markdown_extentions”*

<img class="shadow" width="600" src="/img/191204c.png" />

Step 3: 然后把markdown_extentions整段复制到右侧`User`文件

<img class="shadow" width="600" src="/img/191204d.png" />

Step 4: 在右侧`User`文件，**markdown_extentions**找到**markdown.extensions.codehilite** 添加**"linenums": true**, 保存关闭

```markdown
            "markdown.extensions.codehilite": {
                "guess_lang": false,
                "linenums": true //显示行号 
            }
        },
        
```
<img class="shadow" width="600" src="/Users/nicjiang/Documents/Markdown/img/191204e.png" />

Step 5: 现在就可以在代码段里显示行号了

<img class="shadow" width="600" src="/Users/nicjiang/Documents/Markdown/img/191204f.png" />

