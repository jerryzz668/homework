**单点时限:** 1.0 sec

**内存限制:** 256 MB

例如: n=3 时，3 个整数 13，312，343 联接成的最长时间为: 34331213。
又如: n=4 时，4 个整数 7，13，4，246 联接成的最长时间为: 7424613。

### 输入格式

n (1≤n≤20)，表示 n 个数。

接下来一行 n 个正整数，大小不超过 104。

### 输出格式

拼成的最长时间。

### 样例

input

```
3
623 583 413
```

output

```
623583413
```

```python
n = int(input())
list_number = list(map(str, input().strip().split()))

def compare_two(a,b):
    a_len,b_len = len(a), len(b)
    min_len = min(a_len, b_len)
    for i in range(min_len):
        if a[i] < b[i]:
            return True
        elif a[i] == b[i]:
            continue
        else:
            return False

for i in range(n):
    for j in range(n-i-1):
        if compare_two(list_number[j], list_number[j+1]):
            list_number[j], list_number[j + 1] = list_number[j+1], list_number[j]
# print(list_number)

output = ''.join(list_number)
print(output)
```

