## 第四周学习心得
### 1. 深度优先
- 树中的dfs：
```
def dfs(node):

    if node in visited:
    # already visited
        return
    visited.add(node)
    # process current node
    # ... # logic here
    dfs(node.left)
    dfs(node.right) 
```

- 一般递归写法：
```
visited = set()
def dfs(node, visited):
if node in visited: # terminator
    # already visited
    return
    visited.add(node)
    # process current node here.
    ...
    for next_node in node.children():
        if not next_node in visited:
            dfs(next node, visited)


```
- 非递归写法：
```
def DFS(self, tree):
    if tree.root is None:
        return []
    visited, stack = [], [tree.root]
    while stack:
        node = stack.pop()
        visited.add(node)
        process (node)
        nodes = generate_related_nodes(node)
        stack.push(nodes) 
```


### 2.广度优先
- 树中的广度优先：
```
def BFS(graph, start, end):
    queue = []
    queue.append([start])
    visited.add(start)
    while queue:
        node = queue.pop()
        visited.add(node)
        process(node)
        nodes = generate_related_nodes(node)
        queue.push(nodes)
# other processing work
```

- 递归代码：
```
def BFS(graph, start, end):
    queue = []
    queue.append([start])
    visited.add(start)
    while queue:
        node = queue.pop()
        visited.add(node)
        process(node)
        nodes = generate_related_nodes(node)
        queue.push(nodes) 
```

## 3.贪心算法
贪心算法是一种在每一步选择中都采取在当前状态下最好或最优（即最有
利）的选择，从而希望导致结果是全局最好或最优的算法。 
- 贪心算法不能回退，对每个子问题都做出选择
- 动态规划会保存之前的运算结果，有回退功能

使用贪心算法的场景：
- 问题能拆成子问题来解决，这种子问题被称为最优子结构
- 贪心算法对子问题解决方案都能做出选择，不能回退
  
## 4.二分查找
代码模板
```
left, right = 0, len(array) - 1
while left <= right:
    mid = (left + right) / 2

    if array[mid] == target:
    # find the target!!
        break or return result

    elif array[mid] < target:
        left = mid + 1
        
    else:
        right = mid - 1
```