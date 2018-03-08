---
layout: post
title:  "leet653.Two Sum"
author: "yzpwslc"
date: 2018-03-08 00:36
---

<p>题目：判断BST上是否存在两个数的和为目标值</p>
<p>分析：以深度优先，左中右方式遍历BST，建立集合用于存储节点值，差集合用于存储目标值与节点值的差值，判断节点值是否在差值集合</p>
<p>代码如下：</p>
{% highlight python %}
        ret = [False]
        valSet = set()
        diffSet = set()
        def tree2list(node):
            if node and (not ret[0]):
                tree2list(node.left)
                if node.val in diffSet:
                    ret[0] = True
                    return ret[0]
                else:
                    valSet.add(node.val)
                    diffSet.add(k - node.val)
                tree2list(node.right)
        tree2list(root)
        if not ret[0]:
            if (valSet & diffSet):
                ret[0] = True
                if (valSet & diffSet).pop() == k / 2:
                    ret[0] = False
        return ret[0]
{% endhighlight%}
<p>思考：需要排除节点值为目标值1/2的情况</p>
