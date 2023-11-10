~~~python
# 与else语句配合使用的情况
#if-else
# if表达式不成立时执行else
# for-else、while-else
# 当没有碰到break的时候执行else

for item in range(3):
    pwd=input("Enter password: ")
    if pwd=='888':
        print("right")
        break
    else:
        print("error")
else:
    print("error tree times")

# 当输入是888的时候，由于碰到了break，所以执行一次之后即可结束
# 当输入是999的时候，由于没有碰到break,执行将开启下一次

~~~