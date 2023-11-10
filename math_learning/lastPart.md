##### 常用的字符编码格式

- python 的解释器使用的是 Unicode(内存)
- .py 文件在磁盘上使用 UTF-8 存储

##### 文件的读写原理

- 文件的读写俗称 IO 操作

- r 模式

  ```python
  file=open('a.txt','r')
  # 只读方式打开文件
  # 文件的指针会放在文件的开头
  print(file.readline())
  # 将读取的内容打印出来
  file.close()
  # 关闭文件

  ```

- w 模式

  ```python
  file=open('b.txt','w')
  # 已只写模式打开文件
  # 如果文件不存在则创建
  # 如果文件存在，则覆盖原有内容
  # 文件指针在文件的开头
  file.write('Python')
  file.close()

  ```

- a 模式
  - 以追加模式打开文件
  - 如果文件不存在则创建，文件指针在文件开头
  - 如果文件存在，则在文件末尾追加内容，文件指针在原文件的末尾
- b 模式

  - 以二进制方式打开文件，不能单独使用，需要和共它一起使用
  - 例如 rb、wb

- +模式
  - 以读写方式打开文件，不能单独使用，需要与其他模式一起使用
  - 例如 a+

##### 文件对象的常用方法

- read([size])
  - 从文件中读取 size 个字节或字符的内容返回
  - 如果省略[size]，则读取到文件末尾，即一次读取文件的所有内容
- readline()
  - 从文本文件中读取一行内容
- readlines()
  - 把文本文件中每一行作为独立的字符串对象，并将这些对象放入列表返回
- write(str)
  - 把字符串 str 内容写入文件
- writelines(s_list)
  - 将字符串列表 s_list 写入文本文件
  - 不添加换行符
- close()
  - 把缓冲区内容写入文件中
  - 同时关闭文件，释放文件对象相关资源

##### with 语句/上下文管理器

- with
  - k 可以自动管理上下文资源
  - 不论什么原因跳出 with 块，都能确保文件正确的关闭
  - 以此达到释放资源的目的
    > with open('a.txt','r') as file:
    > print(file.read())
  - 使用 with 方式可以不写 close()代码

##### os 模块

- 与操作系统相关

```python
import os
os.system("notepad.exe")
# 调用记事本
os.system("calc.exe")
# 调用计算器
os.startfile('文件位置')
# 注意转义字符要使用两个//
```

- os 操作目录相关函数
  - getcwd()返回当前的工作目录
  - listdir(path)返回指定路径下的文件和目录信息
  - mkdir(path,[,mode])创建目录
  - rmdir(path)删除目录
  - removedirs(path1/path2……)删除多级目录
  - chdir(path)将 path 设置为当前工作目录
