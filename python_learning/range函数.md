~~~python
# 用于生成一个整数序列
# 创建range对象的三种方式
# range(stop)-->创建一个[0,stop]之间的整数序列，步长为1
# range(start,stop)-->创建一个[start,stop]之间的整数序列，步长为1
# range(start,stop,step)-->创建一个[start,stop]之间的整数序列，步长为step

# range的使用例子
r=range(10)
# 打印结果是range(0,10)
print(r)
# 查看range内的数，需要list列表
# 打印结果是0-9
print(list(r))


# 返回值是迭代器
# range类型不管对象表示的整数序列有多长，所有的range对象占用的内存空间都是相同的
# range只需要存储start,stop,step
# 只有用到range对象时候，才会去计算序列中的相关元素
# in,not in判断整数序列中是否存在（不存在）指定的整数
~~~