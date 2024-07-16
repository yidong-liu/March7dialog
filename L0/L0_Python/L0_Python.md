---
title: L0_Python_task
date: 2024-07-16 16:47:40
tags: 书生大模型
cover: /picture/20240715204439/bg.jpg
copyright: false
---
### 任务一
请用Python实现一个wordcount函数，统计英文字符串中每个单词出现的次数。返回一个字典，key为单词，value为对应单词出现的次数。
    TIPS：记得先去掉标点符号,然后把每个单词转换成小写。不需要考虑特别多的标点符号，只需要考虑实例输入中存在的就可以。
    Eg:
        Input:
        ```
           Hello world!  
           This is an example.  
           Word count is fun.  
           Is it fun to count words?  
           Yes, it is fun!
         ```
         Output:
         ```python
         {'hello': 1,'world!': 1,'this': 1,'is': 3,'an': 1,'example': 1,'word': 1,      'count': 2,'fun': 1,'Is': 1,'it': 2,'to': 1,'words': 1,'Yes': 1,'fun': 1  }
         ```
```python
import string  
def worldcount(text:str) -> dict:
    a = {}
    punctuation_to_remove = string.punctuation  
    translator = str.maketrans('', '', punctuation_to_remove)  
    no_punctuation = text.translate(translator)  
    lowercase_text = no_punctuation.lower()  
    lowercase_text = lowercase_text.split()
    for i in lowercase_text:
        if i not in a:
            a[i] = 1
        else:
            a[i] += 1
    return a
text = """
Got this panda plush toy for my daughter's birthday, 
who loves it and takes it everywhere. It's soft and 
super cute, and its face has a friendly look. It's 
a bit small for what I paid though. I think there 
might be other options that are bigger for the 
same price. It arrived a day earlier than expected, 
so I got to play with it myself before I gave it 
to her.
"""
result = worldcount(text)
print(result)
```
### 任务二
请使用本地vscode连接远程开发机，将上面你写的wordcount函数在开发机上进行debug，体验debug的全流程，并完成一份debug笔记(需要截图)。
![](/picture/L0_Python/20240716051641737.png)
![](/picture/L0_Python/20240716051842551.png)

