title: 'Codeforces #341 div2 A.Wet Shark and Odd and Even'
date: 2016-02-03 18:55:04
tags: [ACM,模拟]
categories: codeforces
---
## Codeforces #341 div2 A

### 题意：
给你一串数字，求最大的偶数和。

### 数据规模：
**1e5**个数字,每个数字范围：**1~1e9**。
<!-- more -->
### 思路：
偶数+偶数=偶数
奇数个偶数相加 = 偶数
1. 用数组分别保存奇数和偶数，全部偶数相加，奇数先排序，如果有奇数个奇数，则后n-1个奇数相加。如果有偶数个奇数，则全部奇数相加。然后奇数和加偶数和。

2. 读入数据时记录最小的奇数，如果所有数总和为奇数，则减去最小的奇数。否则，不减。

### 注意点 :
用`ll`

### 代码 :
思路1
```
#include <cstdio>
#include <cstdlib>
#include <string.h>
#include <string>
#include <math.h>
#include <algorithm>
#include <iostream>
#include <queue>
#include <stack>
const int EPS = 1e-8;
typedef long long ll;
using namespace std;
const int maxn = 1e6 + 10;
ll even[maxn];
ll odd[maxn];

int main()
{
    int n, cntEven = 0, cntOdd = 0;
    cin >> n;
    getchar();
    while (n--)
    {
        ll temp = 0;
        scanf("%lld", &temp);
        temp % 2 == 0 ? even[cntEven++] = temp : odd[cntOdd++] = temp;
    }

    ll ans = 0;
    for (int i = 0; i < cntEven; i++)
    {
        ans += even[i];
    }

    if (cntOdd % 2 == 0)
    {
        for (int i = 0; i < cntOdd; i++)
        {
            ans += odd[i];
        }
    }
    else
    {
        sort(odd, odd + cntOdd);
        for (int i = cntOdd - 1; i > 0; i--)
        {
            ans += odd[i];
        }
    }
    cout << ans << endl;
    return 0;
}
```