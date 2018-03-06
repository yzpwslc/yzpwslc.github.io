---
layout: post
title:  "leet673"
author: "yzpwslc"
date: 2018-03-06 20:23
---

<p>题目：计算给定二叉树每层节点平均值</p>
<p>分析：用深度优先(DFS)或广度优先（BFS）遍历二叉树，累加每层节点值，以及个数，输出平均值</p>
<p>代码如下：</p>
{% highlight python %}
        ret = []
        if root is None:
            return ret
        ave0 = [[root.val,1]]
        def dfs(node,depth = 0):
            if node:
                if len(ave0) <= depth:
                    ave0.append([0,0])
                ave0[depth][0] += node.val
                ave0[depth][1] += 1
                dfs(node.right,depth + 1)
                dfs(node.left,depth + 1)
        dfs(root.left,1)
        dfs(root.right,1)
        def avang(l):
            return l[0] / float(l[1])
        return map(avang,ave0)
{% endhighlight%}
