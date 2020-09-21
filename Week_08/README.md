## 第八周学习笔记
### 1.Bloom Filter
```
from bitarray import bitarray
import mmh3
class BloomFilter:
def __init__(self, size, hash_num):
    self.size = size
    self.hash_num = hash_num
    self.bit_array = bitarray(size)
    self.bit_array.setall(0)
def add(self, s):
    for seed in range(self.hash_num):
        result = mmh3.hash(s, seed) % self.size
        self.bit_array[result] = 1
def lookup(self, s):
    for seed in range(self.hash_num):
        result = mmh3.hash(s, seed) % self.size
        if self.bit_array[result] == 0:
            return "Nope"
    return "Probably"
bf = BloomFilter(500000, 7)
bf.add("dantezhao")
print (bf.lookup("dantezhao"))
print (bf.lookup("yyj")) 
```

### 2.排序
#### 1. 初级排序 - $O（N^2）$
- 选择排序（Selection Sort）:每次找最小值，然后放到待排序数组的起始位置。
- 插入排序（Insertion Sort）:从前到后逐步构建有序序列；对于未排序数据，在已排序序列中从后向前扫描，找到相应位置并插入。
- 冒泡排序:嵌套循环，每次查看相邻的元素如果逆序，则交换。

#### 2.高级排序 - $O(NlogN)$
- 快速排序：
数组取标杆 pivot，将小元素放 pivot左边，大元素放右侧，然后依次对右边和右边的子数组继续快排；以达到整个序列有序。
- 归并排序（Merge Sort）— 分治：
1. 把长度为n的输入序列分成两个长度为n/2的子序列；
2. 对这两个子序列分别采用归并排序；
3. 将两个排序好的子序列合并成一个最终的排序序列。

- 堆排序：
 1. 数组元素依次建立小顶堆
 2. 依次取堆顶元素，并删除
