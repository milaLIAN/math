## 列表list

#### 列表

- 变量可以存储一个元素
- 列表是一个大的容器，可以存储多个元素
- 列表相当于其他语言中的数组
- 列表内的元素可以是不同类型

#### 列表的创建

- 使用[]
  > ["hello","world","python"]
  > ["hello","124"]

- 使用内置函数list()
  > list(["hello","world","python"])
- 内置函数list使用的是引用

#### 列表的特点

- 列表元素按顺序有序排序
- 索引映射一个数据,索引从0开始
- 索引可以从左边开始,0之后依次++
- 索引也可以从右边开始，-1之前依次--
- 列表可以存储重复数据
- 任意数据类型混存
- 根据需要动态分配和回收内存,不需要考虑内存不够的问题

#### 列表种元素的获取

- 获取列表种指定元素的索引

  > index()
  > > 如查列表中存在N个相同元素,只返回相同元素中的第一个元素的索引
  > > 如查询的元素在列表中不存在，则会抛出ValueError
  > > 也可在指定的start和stop之间进行查找

- 获取列表中的单个元素
  > > 使用索引进行查找
  > > 正向索引从0-->N-1,list[0]
  > > 逆向索引从-N-->-1
  > > 指定索引不存在，抛出indexError

- 获取列表中的多个元素
  > 列表名[start: stop :step]
  > 切片的操作
  > > 结果：原列表片段的拷贝
  > > 范围：[start,stop)
  > > step默认是1
  > > step为正数
  > > > [:stop:step]切片的第一个元素默认是列表的第一个元素
  > > > [start::step]切片的最后一个元素默认是列表的最后一个元素
  > > step为负数
  > > > [:stop:step]切片的第一个元素默认是列表的最后一个元素
  > > > [start::step]切片的最后一个元素默认是列表的第一个元素


#### 列表元素的查询操作

- 判断指定元素在列表中是否存在

~~~python
lst=[10,20,'python','int']
print('python' in lst)
print(10 not in lst)
~~~

- 列表元素的遍历

~~~python
for intem in lst:
    print(intem)
~~~


#### 列表元素的增加操作

~~~python
lst=[10,20,'python','int']

# 列表的末尾添加一个元素
lst.append(100)
for intem in lst:
    print(intem,end='\t')
print()

# 在列表的末尾至少添加一个元素
li=[10,20]

# 10	20	python	int	100	[10, 20]
# 将li当成一个元素添加到lst的末尾
lst.append(li)
for intem in lst:
    print(intem,end='\t')
print()

# 10	20	python	int	100	[10, 20]	10	20
# 将li的元素依次放到lst的末尾
lst.extend(li)
for intem in lst:
    print(intem,end='\t')
print()

# 在列表的任一位置上添加
# 10	3	20	python	int	100	[10, 20]	10	20
# 在某个位置添加某个元素
lst.insert(1,3)
for intem in lst:
    print(intem,end='\t')
print()

# 在列表的任意位置添加至少一个元素
# 使用切片的方式进行添加
lis=['worker','network']
lst[1:]=lis
# [10, 'worker', 'network']
# 相当于把1之后的元素全部切掉，然后用添加的列表进行补充
print(lst)
~~~

#### 列表元素的删除

~~~python
# 列表元素的删除操作
# 一次删除一个元素
# 重复元素只删除第一个
# 元素不存在溢出抛出ValueError
# 打印结果[10, 20, 40, 50, 60]
lst=[10,20,30,40,50,60]
lst.remove(30)
print(lst)

# 删除一个指定索引位置上的元素
# 打印结果[10, 40, 50, 60]
lst.pop(1)
print(lst)

# 指定索引不存在抛出IndexError
# IndexError: pop index out of range
# lst.pop(100)
# print(lst)

# 不指定索引，删除列表中的最后一个元素
# 打印结果[10, 40, 50, 60]
lst.pop()
print(lst)

# 切片
# 一次至少删除一个元素
#将产生一个新的列表对象
new_lst =lst[1:3]
print(new_lst)
# 不产生新的列表对象，而是删除原列表中的内容
# 操作如下
# 打印结果[10]
lst[1:3]=[]
print(lst)

# 清空列表
lst.clear()

# 删除列表
del lst
print(lst)
# 打印结果NameError: name 'lst' is not defined

~~~


#### 列表的修改

~~~python
# 一次只修改一个值
# [10, 20, 100, 40, 50, 60]
lst=[10,20,30,40,50,60]
lst[2]=100
print(lst)

# 一次修改多个值
# 切片的方式
# 打印结果[10, 100, 200, 300, 40, 50, 60]
lst[1:3]=[100,200,300]
print(lst)
~~~

#### 列表的排序

~~~python
from audioop import reverse

lst=[10,30,20,50,100,60]
# 开始排序，调用列表对象的sort方法，升序排序
# 列表的排序是在原列表的基础上进行，id没有发生改变
lst.sort()
print(lst)

# 通过指定关键字参数，将列表中的元素进行降序排序
lst.sort(reverse=True)
print(lst)

# reverse=False将进行升序排序
# 默认是False

# 使用内置函数sorted()对列表进行排序，将产生一个新的列表对象
new_list=sorted(lst)
delete_list=sorted(lst,reverse=True)
~~~

#### 列表生成式

~~~python
# 列表生成式
# 列表生成式 列表变量 可迭代式
lst=[i for i in range(1,10)]
print(lst)
# 列表生成式具有局限性，是有一定规律的
~~~