**单点时限:** 1.0 sec

**内存限制:** 256 MB

假设在周末舞会上，男士们和女士们进入舞厅时，各自排成一队。跳舞开始时，依次从男队和女队的队头上各出一人配成舞伴。规定每个舞曲能有一对跳舞者。若两队初始人数不相同，则较长的那一队中未配对者等待下一轮舞曲。现要求写一个程序，模拟上述舞伴配对问题。

### 输入格式

三个整数 m, n, k (1≤m,n≤150,1≤k≤4000)，分别表示男士人数、女士人数、几轮舞曲。

### 输出格式

输出各轮舞曲的配对方案。

### 样例

input

```
2 4 6
```

output

```
1 1
2 2
1 3
2 4
1 1
2 2
```

```python
m, n, k = list(map(int, input().strip().split()))

if m >= k and n >= k:
    for i in range(1, k+1):
        print('{} {}'.format(i,i))
elif m >= k and n < k:
    a = 1
    for i in range(1, k+1):
        if a<=n:
            print('{} {}'.format(i,a))
            a+=1
        elif a>n:
            a = 1
            print('{} {}'.format(i,a))
            a += 1
elif n >= k and m < k:
    a = 1
    for i in range(1, k+1):
        if a<=m:
            print('{} {}'.format(a,i))
            a+=1
        elif a>m:
            a = 1
            print('{} {}'.format(a,i))
            a += 1
elif m < k and n < k:
    a,b = 1, 1
    for i in range(k):
        if a<=m and b<=n:
            print('{} {}'.format(a,b))
            a+=1
            b+=1
        elif a>m and b <=n :
            a = 1
            print('{} {}'.format(a,b))
            a+=1
            b+=1
        elif a<=m and b >n :
            b = 1
            print('{} {}'.format(a,b))
            a+=1
            b+=1
        elif a>m and b >n :
            a,b = 1, 1
            print('{} {}'.format(a,b))
            a+=1
            b+=1
```

