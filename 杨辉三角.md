**单点时限:** 1.0 sec

**内存限制:** 256 MB

抬头再看了一眼星空和黑夜，今晚的星星变成了一个三角形的样子，像这样：

```
1
1 1
1 2 1
1 3 3 1
1 4 6 4 1
...
```

现在给你一个正整数 n，请你给出星空的前 n 行。

### 输入格式

输入文件共一行，包含一个正整数 n (1≤n≤20)。

### 输出格式

输出文件共 n 行，即星空的前 n 行。每行包含若干正整数，这些正整数之间用一个空格隔开（不能有多余的空格），最后一个正整数后面没有空格。

### 样例

input

```
4
```

output

```
1
1 1
1 2 1
1 3 3 1
```

```python
n = int(input())
l1 = [[1]]
l2 = [[1], [1, 1]]
if n == 1:
    print('1')
if n == 2:
    for i in range(2):
        print(' '.join(str(j) for j in l2[i]))
if n > 2:
    yanghui_list = [[1], [1, 1]]
    N = 3
    while N <= n:
        newlist = [1]
        for i in range(len(yanghui_list[-1])-1):
            newlist.append(yanghui_list[-1][i]+yanghui_list[-1][i+1])
        newlist.append(1)
        yanghui_list.append(newlist)
        N +=1 
    for i in range(len(yanghui_list)):
        print(' '.join(str(j) for j in yanghui_list[i]))
```

