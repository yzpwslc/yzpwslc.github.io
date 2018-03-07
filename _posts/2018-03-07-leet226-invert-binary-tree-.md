---
layout: post
title:  "leet226"
author: "yzpwslc"
date: 2018-03-07 20:42
---

<p>题目：二叉树变换</p>
<p>分析：采用递归方式，交换二叉树节点左右指针</p>
<p>代码如下：</p>
{% highlight python %}
        def exchange(node):
            if node:
                temp = node.left
                node.left = node.right
                node.right = temp
                exchange(node.left)
                exchange(node.right)

        exchange(root)
        return root
{% endhighlight%}
