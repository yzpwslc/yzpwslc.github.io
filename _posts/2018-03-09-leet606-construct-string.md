---
layout: post
title:  "leet606.construct string from BT"
author: "yzpwslc"
date: 2018-03-09 01:08
---

<p>题目：将一棵二叉树输出为指定格式字符串</p>
<p>分析：考察对二叉树遍历过程的理解，根据指定格式，使用dfs，中左右方式遍历</p>
<p>代码如下：</p>
{% highlight python %}
        strLst = []
        def dfs(node):
            if node:
                strLst.append(str(node.val))
                if node.left:
                    strLst.append('(')
                    dfs(node.left)
                    strLst.append(')')
                if node.right:
                    if node.left is None:
                        strLst.append('()')
                    strLst.append('(')
                    dfs(node.right)
                    strLst.append(')')

        dfs(t)
        return ''.join(strLst)
{% endhighlight%}
