~~~python
# 可以输出数字
print(16)
print(45.5)

# 可以输出字符串
# 关于字符串的输入输出，单引号和双引号都可以
print("helloworld")
print('helloword')

# 可以输出表达式
print(3+1)
# 输出结果是4

# 可以输出结果是文件
# 注意事项：指定的露营可达
# 使用的file=fp
# 使用之后关闭
# a+ 如果有这个文件在源文件内容的后面进行写入
# 如果没有该文件的话，需要再创建一个文件之后再写入
fp=open('D:/test.txt','a+')
print('helloworld',file=fp)
fp.close()

# 默认的换行输出
# 输出结果不换行
print('hello','world','python')
~~~