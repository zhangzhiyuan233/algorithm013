## 第一周学习内容整理

### 1. 指法/小操作：
- fn + 左/右： 到行头/行尾
- crtl + 左/右： 单词头/尾
- crtl + delete: 删除整个单词
- crtl + shift + 左/右：选取整个一行
- ide 代码补全
- command + E： 打开最近打开的文件夹
- [Top Tips for VScode](https://scotch.io/bar-talk/my-top-8-visual-studio-code-tips-and-features)
- [VScode thems](https://vscodethemes.com/)
- [Top Tips for pycharm](https://www.youtube.com/watch?v=NoDx0MEESDw)

### 2. 算法复杂度：
  - 时间复杂度：
     - 快排： $O(Nlog(N))$ 
     - 冒泡： $O(N^2)$
     - 二叉树遍历 (前序、中序、后序)： $O(N)$
     - 图的遍历：$O(N)$
     - 搜索算法 (DFS,BFS): $O(N)$
     - 二分查找：$O(N)$

  - 空间复杂度：
     - 临时空间不随着某个变量n的大小而变化： $O(1)$
     - 新开了一个大小为n的数组： $O(N)$

![常用算法时间复杂度](time_complexity.png)

### 3. 数组/链表/跳表：
#### 数组: 
```
list = []
```
#### Linked List:
- 单链表：
  ```
  class ListNode:
     def __init__(self, x):
         self.val = x
         self.next = None
  ```
![](singly_linked_list.png)
- 双链表：
  ```
  class Node: 
    def __init__(self, next=None, prev=None, data=None): 
        self.next = next # reference to next node in DLL 
        self.prev = prev # reference to previous node in DLL 
        self.data = data 
  ```
![](doubly_linked_list.png)
#### 跳表：
- 只能用于元素有序的情况
- insert/ delete/ search: $O(logN)$

### 4. 栈/对列/双端对列/优先对列：
#### 栈(Stack):
Last in - First out

```
class Stack:
     def __init__(self):
         self.items = []

     def isEmpty(self):
         return self.items == []

     def push(self, item):
         self.items.append(item)

     def pop(self):
         return self.items.pop()

     def peek(self):
         return self.items[len(self.items)-1]

     def size(self):
         return len(self.items)

```
![](stack.png)

#### 对列(Queue):
```
class Queue:
    def __init__(self):
        self.items = []

    def isEmpty(self):
        return self.items == []

    def enqueue(self, item):
        self.items.insert(0,item)

    def dequeue(self):
        return self.items.pop()

    def size(self):
        return len(self.items)
```
![](Queue.png)

#### 双端对列(Deque):
- 两端都可以进出的Queue
- Deque: Double ended queue
- 插入和删除都是 $O(1)$ 操作

```
# importing "collections" for deque operations 
import collections 
  
# initializing deque 
de = collections.deque([1,2,3]) 
  
# using append() to insert element at right end  
# inserts 4 at the end of deque 
de.append(4) 
  
# printing modified deque 
print ("The deque after appending at right is : ") 
print (de) 
  
# using appendleft() to insert element at right end  
# inserts 6 at the beginning of deque 
de.appendleft(6) 
  
# printing modified deque 
print ("The deque after appending at left is : ") 
print (de) 
  
# using pop() to delete element from right end  
# deletes 4 from the right end of deque 
de.pop() 
  
# printing modified deque 
print ("The deque after deleting from right is : ") 
print (de) 
  
# using popleft() to delete element from left end  
# deletes 6 from the left end of deque 
de.popleft() 
  
# printing modified deque 
print ("The deque after deleting from left is : ") 
print (de) 
```

#### [Priority Queue](https://www.educative.io/edpresso/what-is-the-python-priority-queue):
- 插入操作： $O(1)$
- 取出操作： $O(logN)$
- 底层具体实现的数据结构较为多样和复杂

```
from queue import PriorityQueue

q = PriorityQueue()

q.put(4)
q.put(2)
q.put(5)
q.put(1)
q.put(3)

while not q.empty():
    next_item = q.get()
    print(next_item)
```
  




