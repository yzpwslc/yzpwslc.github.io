---
layout: post
title:  "leet538.convert BST to Greater Tree"
author: "yzpwslc"
date: 2018-03-09 19:38
---

<p>题目：将BST转换为更大树</p>
<p>分析：采用dfs方式按右中左将节点值加上一节点值</p>
<p>代码如下：</p>
{% highlight python %}
        greaterNode = [0]
        def dfs(node):
            if node:
                dfs(node.right)
                node.val += greaterNode[0]
                greaterNode[0] = node.val
                dfs(node.left)
            return node
        dfs(root)
        return root
{% endhighlight%}
