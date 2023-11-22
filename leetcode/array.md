> Problem: [88. 合并两个有序数组](https://leetcode.cn/problems/merge-sorted-array/description/)

[TOC]

##### 题目描述

> 给你两个按 非递减顺序 排列的整数数组 nums1 和 nums2，另有两个整数 m 和 n ，分别表示 nums1 和 nums2 中的元素数目。
> 请你 合并 nums2 到 nums1 中，使合并后的数组同样按 非递减顺序 排列。
> 注意：最终，合并后数组不应由函数返回，而是存储在数组 nums1 中。为了应对这种情况，nums1 的初始长度为 m + n，其中前 m 个元素表示应合并的元素，后 n 个元素为 0 ，应忽略。nums2 的长度为 n 。

##### 实例

> 输入：nums1 = [1,2,3,0,0,0], m = 3, nums2 = [2,5,6], n = 3
> 输出：[1,2,2,3,5,6]
> 解释：需要合并 [1,2,3] 和 [2,5,6] 。
> 合并结果是 [1,2,2,3,5,6] ，其中斜体加粗标注的为 nums1 中的元素。
> 示例 2：

> 输入：nums1 = [1], m = 1, nums2 = [], n = 0
> 输出：[1]
> 解释：需要合并 [1] 和 [] 。
> 合并结果是 [1] 。
> 示例 3：

> 输入：nums1 = [0], m = 0, nums2 = [1], n = 1
> 输出：[1]
> 解释：需要合并的数组是 [] 和 [1] 。
> 合并结果是 [1] 。
> 注意，因为 m = 0 ，所以 nums1 中没有元素。nums1 中仅存的 0 仅仅是为了确保合并结果可以顺利存放到 nums1 中。

##### 解题方法

因为题目中给出的序列就是非递减序列，并且给出的序列不用占位置的都是用 0 进行代替，所以进行合并的时候就不需要对 nums1 的空间进行扩展。结果也是需要递减的，因此要从 nums1 和 nums2 的最后一个元素进行比较和替换，直到某个数组的元素为 0 开始。

![Alt text](/resource/88.jpg)

##### 复杂度

- 时间复杂度:

  > $O(m+n)$

- 空间复杂度:
  > $O(1)$

##### Code

```Python

from typing import List

class Solution:
    def merge(self, nums1: List[int], m: int, nums2: List[int], n: int) -> List[int]:
        # 使用双指针的方式
        # 首先，将指针移到对应的位置上
        i = m-1
        j = n-1
        k = m+n-1
        # 判断整个工作的条件
        while i >= 0 and j >= 0:
            if nums1[i] > nums2[j]:
                nums1[k] = nums1[i]
                i -=1
            else:
                nums1[k] = nums2[j]
                j -= 1
            k -= 1

        # nums2中有元素未合并，将其复制到nums1中
        while j >= 0:
            nums1[k] = nums2[j]
            j -= 1
            k -= 1

        return nums1

if __name__ == '__main__':
    s = Solution()
    nums1 = [1, 2, 3, 0, 0, 0]
    m = 3
    nums2 = [2, 5, 6]
    n = 3
    result = s.merge(nums1, m, nums2, n)
    print(result)

```

##### 栈相关

- 匹配括号

> 普通情况：
> 输入的括号中只有()和空格，没有其他的东西

```python
from pythonds.basic import Stack

# 当输入是(时，push()栈中
# 当输入时)时，pop()出栈
def parChecker(symbolString):
    s = Stack()
    balence = True
    index = 0
    while index<len(symbolString) and balence:
        symbol = symbolString[index]
        if symbol=="(":
            s.push(symbol)
        else:
            if s.isEmpty():
                balence = False
            else:
                s.pop()
        index = index + 1
    if balence and s.isEmpty():
        return True
    else:
        return False

if __name__ == '__main__':
    str = input("please input the string:")
    print(parChecker(str))

```

- 进制转换

  - 思路
    - 十进制的数字除以 目标进制 之后获得的余数不断进入栈
    - 之后将十进制进行除以目标进制
    - 如果获得的栈不为空，那么将栈中的元素弹出
  - 代码如下：

    ```python
    def div(num):
        result = Stack()
        while num>0:
            res = num % 2
            result.push(res)
            num // 2
            # 使得num最后的值不是float类型

        # 将最后的结果进行返回
        # 使用string类型
        ress = ""
        while not result.isEmpty():
            ress = ress + result.pop()

        return ress

    ```

- 队列相关

  - 使用两个栈形成队列
    - 其中一个栈用于队列出，一个栈用于队列进
    - 其中这两个栈内的数据顺序正好相反
    - ![Alt text](/resource/queue.jpg)

  ```python
  class MyQueue(object):
    def __init__(self):
        # push
        self.stack1 = []
        # pop
        self.stack2 = []

    def push(self,x):
        self.stack1.append(x)

    def pop(self):
        # 当用于pop的栈为空的时候
        # 将push栈中的元素依次放进pop栈中

        if not self.stack2:
            while self.stack1:
                self.stack2.append(self.stack1.pop())

        return self.stack2.pop()

    def peek(self):

        if not self.stack2:
            while self.stack1:
                self.stack2.append(self.stack1.pop())

        return self.stack2[-1]

    def isEmpty(self):
        return not self.stack1 and not self.stack2

  ```

  - 传土豆/约瑟夫斯问题

    - 在这个游戏中，孩子们围成一圈，并依次尽可能快地传递一个土豆，当停止传递时候，手里有土豆的孩子就要退出游戏。重复上述过程，直到只剩下一个孩子。
    - ![Alt text](/resource/potato.jpg)
    - 分析
      - 传参进入的是人名以及传递土豆的次数
      - pop()的次数比传递土豆的次数要多 1
    - 代码详情

      ```python
      from pythonds import Queue

      def hotPotato(namelist,num):
         # 首先建立一个队列
         que = Queue()
         for name in namelist:
        # 将所有名字压入队列中
        que.enqueue(name)

        # 队列中有元素
        while not que.isEmpty():
            for i in range(num):
            # 将队列弹出的元素放在队列的末尾
            que.enqueue(que.dequeue())

        # dequeue() = num - 1
        que.dequeue()
        # 将队列前面的元素弹出
        return que.dequeue()
      ```

##### 双端队列

- 双端队列是与队列类似的有序集合。双端队列对在哪一端添加和移除元素没有限制。新元素可以被添加到前端，也可以被添加到后端。双端队列是栈和队列的结合。

  ```python
  class Deque():
    def __int__(self):
        self.iterms = []

    def isEmpty(self):
        return self.iterms == []
    # 在前面添加元素
    def addFront(self,x):
        self.iterms.append(x)
    # 在后面添加
    def ddRear(self,x):
        self.iterms.index(0,x)

    def removeFront(self):
        return self.iterms.pop()

    def removeRear(self):
        return self.iterms.pop(0)

    def size(self):
        return len(self.iterms)
  ```
