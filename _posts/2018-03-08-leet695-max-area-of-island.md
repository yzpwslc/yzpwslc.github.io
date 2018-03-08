---
layout: post
title:  "leet695.Max Aera of Island"
author: "yzpwslc"
date: 2018-03-08 18:42
---

<p>题目：用一个2D数组表示一块区域，1代表岛，计算最大岛的面积。</p>
<p>分析：使用递归方式，每次访问后的网格置0</p>
<p>代码如下：</p>
{% highlight python %}
        m, n = len(grid), len(grid[0])
        def dfs(i, j):
            ret = 0
            if 0 <= i < m and 0 <= j < n and grid[i][j]:
                grid[i][j] = 0
                ret =  1 + dfs(i - 1, j) + dfs(i, j + 1) + dfs(i + 1, j) + dfs(i, j - 1)
            return ret

        areas = [dfs(i, j) for i in range(m) for j in range(n) if grid[i][j]]
        return max(areas) if areas else 0
{% endhighlight%}
