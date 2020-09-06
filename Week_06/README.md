## 第六周学习内容整理

### 1.递归代码模板
```
def recursion(level, param1, param2, ...):

# 1 recursion terminator
    if level > MAX_LEVEL:
        process_result
        return

# 2 process logic in current level
    process(level, data...)

# 3 drill down
    self.recursion(level + 1, p1, ...)

# 4 reverse the current level status if needed 
```
### 2.分治代码模板

```
def divide_conquer(problem, param1, param2, ...):

# 1 recursion terminator
    if problem is None:
        print_result
        return

# 2 prepare data
    data = prepare_data(problem)
    subproblems = split_problem(problem, data)

# 3 conquer subproblems
    subresult1 = self.divide_conquer(subproblems[0], p1, ...)
    subresult2 = self.divide_conquer(subproblems[1], p1, ...)
    subresult3 = self.divide_conquer(subproblems[2], p1, ...)

...
# 4 process and generate the final result
    result = process_result(subresult1, subresult2, subresult3, …)

# 5 revert the current level states 
```

### 3. 动态规划
- “Simplifying a complicated problem by breaking it down into simpler sub-problems” (in a recursive manner)

- Divide & Conquer + Optimal substructure 
  
#### 动态规划的关键点：
- 最优子结构 opt[n] = best_of(opt[n-1], opt[n-2], …)
- 储存中间状态：opt[i]
- 递推公式（美其名曰：状态转移方程或者 DP 方程） 
  - Fib: opt[i] = opt[n-1] + opt[n-2] 
  - 二维路径：opt[i,j] = opt[i+1][j] + opt[i][j+1] (且判断a[i,j]是否空地）

### 4.相关资料
- [MIT algorithm course](https://www.bilibili.com/video/av53233912?from=search&seid=2847395688604491997)

- [股票问题系列通解](https://leetcode-cn.com/circle/article/qiAgHn/ )

