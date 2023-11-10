#### bug 的常见类型

- 粗心导致语法错误 SyntaxError

  - 语法语句后面的冒号
  - 缩进错误
  - 把英文符号携程中文符号
  - 字符串拼接的时候，把字符串和数字拼接在一起
  - 没有定义变量，例如 while 的循环条件的变量
  - ==比较运算符和=赋值运算符的混用

- 索引越界问题 IndexError

  - 列表、集合、字典的索引都是从 0 开始的，所以容易导致索引越界的问题

- append()方法的使用掌握不熟练
- 思路不清楚的错误

  - 使用 print 进行调试
  - 使用#注释代码进行调试

- 无法避免的错误

  - 异常处理机制，可以在异常出现时即时捕获，然后内部进行消化，让程序继续运行
  - try-except
  - 多个异常情况时对每一个异常都使用 except 进行列举出来
  - except 执行之后不回去，继续执行

- try-except-else-finally

  ```python
  from unittest import result

  try:
    a=int(input("first number:"))
    b=int(input("last number:"))
    result=a/b
  except BaseException as e:
    # 对所有可能出现的异常做一个捕获
    # 错误内容是e
    print('Error',e)
  # 如果try块中没有抛出异常，执行else块
  # 如果try块中抛出异常，则执行except块
  else:
    print(result)
  # finally块无论是否发生异常都会被执行
  # 常用来释放try块中申请的资源
  finally:
    print('Code Success')
  ```

- 常见的异常类型

  - 除(或取模)零(所有类型)

- 使用 traceback 打印异常信息
  ```python
  import traceback
  try:
    print(1/0)
  except:
    traceback.print_exc()
    # 异常信息会被保存到系统日志当中
    # 使用上述方法可以将异常信息进行打印
  ```
