**单点时限:** 2.0 sec

**内存限制:** 256 MB

给你一个字符串，长度不超过 10000，反转输出这个字符串。

### 输入格式

每次一行字符串，有空格。

多 Case，处理到文件结束。

### 输出格式

每次一行，输出反转后的字符串。

### 样例

input

```
abcd
abcd a
```

output

```
dcba
a dcba
```

```python
while True:
    try:
        a = input()
        b = a[::-1]
        print(b)
    except:
        break
```

