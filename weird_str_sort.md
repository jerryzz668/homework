**单点时限:** 1.0 sec

**内存限制:** 256 MB

定义函数 Sort，对一个字符串数组的元素按照字符串的首字符的升序进行排序。首字符相同的字符串按照字符串本身的字典序降序进行排序。

字符串中只会出现小写英文字母。

### 样例

**input:**

24
alpha
beta
gamma
delta
epsilon
zeta
eta
theta
iota
kappa
lambda
mu
nu
xi
omicron
pi
rho
sigma
tau
upsilon
phi
chi
psi
omega

**output:**

alpha
beta
chi
delta
eta
epsilon
gamma
iota
kappa
lambda
mu
nu
omicron
omega
psi
pi
phi
rho
sigma
theta
tau
upsilon
xi
zeta

**python 实现**

```python
n = int(input())  # 获取输入行数
arr = []
for i in range(n):
    a = input()
    arr.append(a)
arr.sort()  # 先按照首字母升序排好

i,j = 0,0  # 获取首字母序列的首尾坐标
while i < n-1:  # 遍历arr，寻找所有首字母相同子序列
    j = 0
    if arr[i][0] == arr[i+1][0]:  # 找到相同子序列的首坐标i
        j+=1
        for k in range(n-i-1):
            if arr[i][0] == arr[i+j][0]:
                j+=1  # 找到相同子序列的尾坐标j
        arr1 = arr[i:i+j]  # 提取出该字段
        b = sorted(arr1, reverse=True)  # 进行降序排列
        arr = arr[0:i] + b + arr[i+j:n]  # 拼接好
        i = i+j
    else:
        i+=1
for i in arr:  # 输出结果
    print(i)
```

