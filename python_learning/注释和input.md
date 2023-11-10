~~~python
# 单行注释：以#开头，直到换行结束
# 多行注释：三个单引号或三个双引号
# 默认存储编码方式是UTF-8

# input函数的使用
# 变量=(赋值运算符)input("内容")
# input函数是一个输入函数，需要输入回答
# 将输入函数的结果赋值给变量

gift=input('你想要什么礼物呢')
print(gift,type(gift))

# 结果
# 你想要什么礼物呢金箍棒
# 金箍棒 <class 'str'>

# 使用input可以从外界进行输入
# 但是如果需要进行正确的运算功能，需要进行相应的类型转换
a=input('a=')
b=input('b=')
print(int(a)+int(b))

a=int(input('a='))
b=int(input('b='))
print(a+b)

# 输出结果
# a=10
# b=10
# 20
~~~