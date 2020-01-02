---
layout:     post
title:      "test python comments"
#subtitle:   " \"Hello World, Hello Blog\""
date:       2020-01-02 12:00:00
author:     "Nicole"
header-img: "img/post-bg-2015.jpg"
tags:
    - Markdown
---

```python
import sys
# it's a comment  
# 这是加两个空格的注释  
## 这是加两个##
## 这是加两个+两个空格##
# 这是空一行

if sys.version_info[0] == 3:
    from importlib import abc
else:
    from importlib2 import abc
```

```
python
import sys

# 这是python在第二行
if sys.version_info[0] == 3:
    from importlib import abc
else:
    from importlib2 import abc
```

```
import sys
# 这是没有定义语言的注释
if sys.version_info[0] == 3:
    from importlib import abc
else:
    from importlib2 import abc
```
