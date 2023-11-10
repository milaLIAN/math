~~~python
if 条件：
#    输出
else:
#    输出

# 例如：判断输入的整数是奇数还是偶数
a=int(input("Enter a number:"))
if a%2==0:
    print("odd number")
else:
    print("even number")

# 多分支
if 条件表达式：
#      输出结果
elil 条件表达式：
#      输出结果

# 嵌套

# 条件表达式
# 正常写
# 从键盘中获取两个数
num1=int(input("num1:"))
num2=int(input("num2:"))
# 对两个数进行比较
if num1 > num2:
    print("num1 is bigger than num2")
elif(num1==num2) :
        print ("num1 is equal num2")
else:
    print("num1 is smaller than num2")

# 写成表达式的形式
# 适用于if-else这种类型的
print("num1 is bigger than num2" if num1 > num2 else "num1 is smaller than num2")

# pass占位符
# 什么也不用做，只是一个占位符，用到需要写语句的地方
if anser=='y'
    pass
~~~