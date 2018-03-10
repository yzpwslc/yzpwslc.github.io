---
layout: post
title:  "leet404.sum of left leaves"
author: "yzpwslc"
date: 2018-03-10 13:22
---

<p>题目：计算数的左叶子节点的和</p>
<p>分析：遍历树，找到左叶子，求和</p>
<p>代码如下：</p>
{% highlight python %}
        sum0 = [0]
        def dfs(node):
            if node:
                if node.left and not (node.left.left or node.left.right):
                    sum0[0] += node.left.val
                dfs(node.left)
                dfs(node.right)
        dfs(root)
        return sum0[0]
{% endhighlight%}
