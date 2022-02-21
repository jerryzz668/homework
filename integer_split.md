**单点时限:** 2.0 sec

**内存限制:** 256 MB

将正整数 n 表示成一系列正整数之和 : n=n1+n2+…+nk，其中 n1≥n2≥…≥nk≥1(k≥1)

正整数 n 的这种表示称为正整数 n 的拆分。求正整数 n 的不同拆分个数。

例如，正整数 6 有如下 11 种不同的拆分 :

6；

5+1；

4+2，4+1+1；

3+3，3+2+1，3+1+1+1；

2+2+2，2+2+1+1，2+1+1+1+1；

1+1+1+1+1+1。

例如，正整数 3 有如下 3 种不同的拆分 :

3;

2+1;

1+1+1。

### 输入格式

本题有多组测试数据，每组一行，每行有一个正整数 N(1<=N<=100)

### 输出格式

每组测试数据输出一行，表示有多少种拆分方法

### 样例

input

```
1
3
5
```

output

```
1
3
7
```

```python
def dp(a,b):
    dp = [[0 for _ in range(a+1)] for _ in range(b+1)]
    for i in range(1,a+1):
        for j in range(1,b+1):
            dp[i][1] = dp[1][j] = 1 
            if j > i:
                dp[i][j] = dp[i][i]
            elif j == i:
                dp[i][j] = dp[i][j-1]+1 
            else:
                dp[i][j] = dp[i-j][j]+dp[i][j-1]
    return dp[a][b]

while True:
    try:
        n = int(input())
        output = dp(n,n)
        print(output)
    except:
        break
```

