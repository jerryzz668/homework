**单点时限:** 2.0 sec

**内存限制:** 256 MB

有些正整数可以表示为 n (n>1) 个连续正整数的和，如：

15=1+2+3+4+5=4+5+6=7+8

给定一个正整数 N，判断其是否可以表示为一组连续正整数的和，输出符合条件的解的组数。

### 输入格式

第 1 行：一个整数 T (1≤T≤10) 为问题数。

第 2 至 T+1 行，对应每个问题有一行，每行一个正整数 N (3≤N≤106)。

### 输出格式

对每个测试数据，输出 `Case x: y`。x 为从 1 开始的测试数据编号，y 为符合条件的解的组数。

### 样例

input

```
3
15
16
99
```

output

```
Case 1: 3
Case 2: 0
Case 3: 5
```

```python
t = int(input())

def inteer(a):
    if a - int(a) == 0:
        return True
    else:
        return False

for i in range(1, t+1):
    n = int(input())
    count = 0
    for j in range(1, n//2+1):
        if n/(j+1)-j/2 > 0 and inteer(n/(j+1)-j/2):
            count += 1
    print("Case {}: {}".format(i, count))
```

