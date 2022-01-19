**单点时限:** 1.0 sec

**内存限制:** 256 MB

一个人走走了很多年，发现自己走到了一个很长的，年久失修的楼梯面前。年久失修的意思就是，有 k 个台阶坏了，没法走。

楼梯一共有 n 层，你一次能上一阶、两阶或三阶台阶，请问，你从楼梯底部 (0 开始) 走到楼梯顶部，共有多少种走法。

### 输入格式

输入数据共两行，第一行包含两个自然数 n (1≤n≤100) 和 k (0≤k<n)，第二行包含 k 个自然数 Xi (1≤Xi≤n)，数字之间用一个空格隔开，表示损坏的台阶的序号（从楼梯底部到楼梯顶部，台阶序号依次为 1 到 n）。

### 输出格式

输出数据仅包含一个整数，表示所有可行走法的总数。

### 样例

input

```
5 2
2 4
```

output

```
2
```

```python
[n,k] = list(map(int, input().strip().split()))

broken = {}
dp = {}
if k != 0:
    broken_list = list(map(str, input().split()))
    # print(broken_list)

    dp[1] = 1 if '1' not in broken_list else 0
    dp[2] = dp[1] + 1 if '2' not in broken_list else 0
    dp[3] = dp[2] + dp[1] + 1 if '3' not in broken_list else 0
    if n >= 4:
        for i in range(4, n+1):
            if '{}'.format(i) in broken_list:
                dp[i] = 0
            else:
                dp[i] = dp[i-1]+dp[i-2]+dp[i-3]
    print(dp[n])
if k == 0:
    dp[1] = 1
    dp[2] = dp[1] + 1
    dp[3] = dp[2] + dp[1] + 1
    if n >= 4:
        for i in range(4, n+1):
            dp[i] = dp[i-1]+dp[i-2]+dp[i-3]
    print(dp[n])
```

