---
layout: post
title:  "leet100.Same Tree"
author: "yzpwslc"
date: 2018-03-10 12:50
---

<p>题目：判断两棵树是否相同</p>
<p>分析：同时遍历两棵树，有节点不一致即返回False</p>
<p>代码如下：</p>
{% highlight python %}
        ret = [True]
        def dfs(node1,node2):
            if node1 and node2:
                if node1.val != node2.val:
                    ret[0] = False
                    return False
                dfs(node1.left,node2.left)
                dfs(node1.right,node2.right)
            elif node1 or node2:
                ret[0] = False
                return False
        dfs(p,q)
        return ret[0]
{% endhighlight%}
