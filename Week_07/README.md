## 第七周学习内容整理
### 本周学习内容于目前面试（ds）关系不大，所以整理的比较少
## 1.字典集
字典树，即 Trie 树，又称单词查找树或键树，是一种树形结构。典型应用是用于统计和排
序大量的字符串（但不仅限于字符串），所以经常被搜索引擎系统用于文本词频统计。

它的优点是：最大限度地减少无谓的字符串比较，查询效率比哈希表高。
```
class Trie(object):

def __init__(self):
    self.root = {}
    self.end_of_word = "#"

def insert(self, word):
    node = self.root
    for char in word:
        node = node.setdefault(char, {})
    node[self.end_of_word] = self.end_of_word

def search(self, word):
    node = self.root
    for char in word:
        if char not in node:
            return False
    node = node[char]
    return self.end_of_word in node

def startsWith(self, prefix):
    node = self.root
    for char in prefix:
        if char not in node:
            return False
    node = node[char]
    return True
```

## 2.并查集
组团、配对问题

- makeSet(s)：建立一个新的并查集，其中包含 s 个单元素集合。
- unionSet(x, y)：把元素 x 和元素 y 所在的集合合并，要求 x 和 y 所在
的集合不相交，如果相交则不合并。
- find(x)：找到元素 x 所在的集合的代表，该操作也可以用于判断两个元
素是否位于同一个集合，只要将它们各自的代表比较一下就可以了。
```
def init(p):
    # for i = 0 .. n: p[i] = i;
    p = [i for i in range(n)]

def union(self, p, i, j):
    p1 = self.parent(p, i)
    p2 = self.parent(p, j)
    p[p1] = p2

def parent(self, p, i):
    root = i
    while p[root] != root:
        root = p[root]
    while p[i] != i: # 路径压缩 ?
        x = i; i = p[i]; p[x] = root
    return root
```

## 3.A* Search
```
def AstarSearch(graph, start, end):
    pq = collections.priority_queue() # 优先级 —> 估价函数
    pq.append([start])
    visited.add(start)
    while pq:
        node = pq.pop() # can we add more intelligence here ?
        visited.add(node)
        process(node)
        nodes = generate_related_nodes(node)
        unvisited = [node for node in nodes if node not in visited]
        pq.push(unvisited)
```
