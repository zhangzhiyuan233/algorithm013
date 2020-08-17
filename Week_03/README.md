# 第三周学习笔记

## 1.泛型递归：
树的面试题一般都是递归：
- 节点的定义
- 重复性（自相似性）

```
def preorder(self, root):
if root:
 self.traverse_path.append(root.val)
 self.preorder(root.left)
 self.preorder(root.right)

def inorder(self, root):
if root:
 self.inorder(root.left)
 self.traverse_path.append(root.val)
 self.inorder(root.right)

def postorder(self, root):
if root:
 self.postorder(root.left)
 self.postorder(root.right)
 self.traverse_path.append(root.val) 
```

泛型递归模板：
```
def recursion(level, param1, param2, ...):

# recursion terminator
if level > MAX_LEVEL:
 process_result
 return

# process logic in current level
process(level, data...)

# drill down
self.recursion(level + 1, p1, ...)

# reverse the current level status if needed 
```

## 2.分治
分治代码模板：
```
def divide_conquer(problem, param1, param2, ...):

# recursion terminator
if problem is None:
 print_result
 return

# prepare data
 data = prepare_data(problem)
 subproblems = split_problem(problem, data)

# conquer subproblems
 subresult1 = self.divide_conquer(subproblems[0], p1, ...)
 subresult2 = self.divide_conquer(subproblems[1], p1, ...)
 subresult3 = self.divide_conquer(subproblems[2], p1, ...)
...

# process and generate the final result
 result = process_result(subresult1, subresult2, subresult3, …)

# revert the current level states 
```

## 3.回溯
回溯法通常用最简单的递归方法来实现，在反复重复上述的步骤后可能出现两种
情况：
- 找到一个可能存在的正确的答案；
- 在尝试了所有可能的分步方法后宣告该问题没有答案。

在最坏的情况下，回溯法会导致一次复杂度为指数时间的计算。