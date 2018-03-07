---
layout: post
title:  "leet104"
author: "yzpwslc"
date: 2018-03-07 20:01
---

<p>题目：计算二叉树的最大深度。</p>
<p>分析：计算最大深度，需要完全遍历，深度优先或广度优先效率一致</p>
<p>代码如下：</p>
{% highlight python %}
        ret = [0]
        def dfs(node,depth = 0):
            if node is None:
                if depth > ret[-1]:
                    ret.append(depth)
                return 0
            else:
                depth += 1
                dfs(node.left,depth)
                dfs(node.right,depth)
        dfs(root,0)
        return ret[-1]
{% endhighlight%}
