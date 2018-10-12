---
layout:     post
title:      "如何使用Sublime Text3的Markdown Preview插件显示图表"
#subtitle:   " \"Hello World, Hello Blog\""
date:       2018-10-11 12:00:00
author:     "Nicole"
header-img: "img/post-bg-2015.jpg"
tags:
    - Markdown
---

### 如何使用Sublime Text3的Markdown Preview插件显示图表

1.Markdown Preview的作者对UML Support的描述如下：
[UML Support](https://facelessuser.github.io/MarkdownPreview/extras/#uml-support)

2.Check Markdown Preview是否支持SuperFences extension，点击<kbd>Preferences</kbd> -> <kbd>Package Settings</kbd> -> <kbd>Markdown Preview</kbd> -> <kbd>Settings</kbd>，看见"pymdownx.superfences"说明支持SuperFences extension, 我使用的Markdown Preview 2.20支持该extention。

```
       // PyMdown extensions that help give a GitHub-ish feel
        "pymdownx.superfences",  // Nested fences and UML support
        {
            "pymdownx.magiclink": {   // Auto linkify URLs and email addresses
                "repo_url_shortener": true,
                "repo_url_shorthand": true
            }
        },
```


3.点击<kbd>Preferences</kbd> -> <kbd>Package Settings</kbd> -> <kbd>Markdown Preview</kbd> -> <kbd>Settings</kbd>, 打开user文件，添加下面这段即可

```
"js": [
        // Required libraries to transform UML notation
        "https://cdnjs.cloudflare.com/ajax/libs/raphael/2.2.7/raphael.min.js",
        "https://cdnjs.cloudflare.com/ajax/libs/underscore.js/1.8.3/underscore-min.js",
        "https://cdnjs.cloudflare.com/ajax/libs/js-sequence-diagrams/1.0.6/sequence-diagram-min.js",
        "https://cdnjs.cloudflare.com/ajax/libs/flowchart/1.6.5/flowchart.min.js",

        // This library applies the above libraries to the fenced code blocks `flow` and `sequence`.
        "res://MarkdownPreview/js/uml.js"
    ]
```

4.然后就可以按照图表的语法编辑即可显示图表

````
```flow
st=>start: Start
op=>operation: Your Operation
cond=>condition: Yes or No?
e=>end
st->op->cond
cond(yes)->e
cond(no)->op
```
````

<img class="shadow" width="320" src="/img/2018-10-11-markdown-tips-flow.png" />


````
```sequence
Title: Here is a title
A->B: Normal line
B-->C: Dashed line
C->>D: Open arrow
D-->>A: Dashed open arrow
```
````

<img class="shadow" width="320" src="/img/2018-10-11-markdown-tips-seq.png" />
