
---
layout:     post
title:      "小白学Markdown遇到的问题记录"
#subtitle:   " \"Hello World, Hello Blog\""
date:       2018-10-17 12:00:00
author:     "Nicole"
header-img: "img/post-bg-2015.jpg"
tags:
    - Markdown
---



>软件：Sublime Text 3（MacOS）



#1.Sublime Text 3 没有安装Package Control?

安装插件需要通过Package Control安装。
如果点开Sublime Text -> Preferences发现没有Package Control，则需要安装Package Control本身。 

安装方法:

>参考[点击链接](https://www.jianshu.com/p/2a4267e1bae8) 的**插件安装过程**章节

同时按下ctrl+`,将会在窗口底部出现一个小控制台,将如下python code拷贝执行

```pyth
import urllib.request,os; 
pf = 'Package Control.sublime-package'; 
ipp = sublime.installed_packages_path(); 
urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); 
open(os.path.join(ipp, pf), 'wb').write(urllib.request.urlopen( 'http://sublime.wbond.net/' + pf.replace(' ','%20')).read())
```

安装完毕后就可以看见Package Control了

![Alt text](img/a01.png)

#2.需要安装什么插件

安装**MarkdownEditing**和**MarkdownPreview**

#3.如何安装插件

1.打开Package Control  
![Alt text](img/a01.png)

2.点击Package Control:Install Packages  
![Alt text](img/a02.png)

3.选择**MarkdownEditing**安装  
![Alt text](img/a03.png)

4.同样选择**MarkdownPreview**安装  
![Alt text](img/a04.png)

#4 换行问题

当输入：

    **今天星期几？**
    *星期一*

会发现呈现在同一行的效果：

**今天星期几？**
*星期一*

在需要换行的所在行最后加**两个空格**：

    **今天星期几？**  //此处加两个空格即可换行
    *星期一*

**今天星期几？**  
*星期一*


#5.何为锚点？

类似word目录索引，如果写了一篇很长的文章，读者可以根据点击目录中感兴趣的篇章，直接跳转到所在位置。锚点就是将其连接在一起的工具。

#6.锚点例子
标题2

    ##2.1 Target

对应锚点
    
    [2.1 Target](#21-target)  

>锚点注意事项: 

- 点号 **.** 直接忽略  
- 空格用 **-** 表示  
- 字母一律小写
- 不支持中文（发现中文出现在锚点总是链接不成功，目前还没有找到好方法）  

参考链接：

[sublime之markdown语法高亮和修改主题](https://www.jianshu.com/p/2a4267e1bae8)  
[Github 中 Markdown 锚点链接如何写](https://my.oschina.net/antsky/blog/1475173)

#<meta http-equiv="refresh" content="3">