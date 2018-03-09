---
layout: post
title:  "leet453.minimum moves toequal array elements"
author: "yzpwslc"
date: 2018-03-09 22:53
---

<p>题目：给一个大小为n的非空整数列表，每次让n-1个元素加1,计算要使数组所有数相等，最小需要多少步操作</p>
<p>分析：可以逆向思考，n-1个元素加1,那么可以等效为1个元素减1，这样就很明显了，依次让每个元素减小到列表最小值，所用的次数即为最小所需次数</p>
<p>代码如下：</p>
{% highlight python %}
        return  sum(nums) - len(nums) * min(nums)
{% endhighlight%}
<p>思考：在这个问题试了蛮久的，一开始认为只要能达到让列表每个值相等，即列表元素之和能被n整除即可，呵呵</p>
