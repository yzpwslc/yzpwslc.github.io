---
layout: post
title:  "leet136"
author: "yzpwslc"
date: 2018-03-07 00:36
---

<p>题目：一个数组里除一个数外，其余数字均出现两次，以O（n）的时间复杂度找出该数，且不使用额外内存。</p>
<p>分析：我采用的方法只实现了线性时间复杂度要求，没有达到不占额外内存的要求。我利用了集合元素不重复，通过遍历过程中将不能重复插入元素存入另一个集合，最后计算差集，得到结果</p>
<p>代码如下：</p>
{% highlight python %}
        len0 = 0
        sNums = set()
        sNum2 = set()
        for x in nums:
            sNums.add(x)
            len1 = len(sNums)
            if len(sNums) - len0 < 1:
                sNum2.add(x)
            len0 = len1
        return  (sNums - sNum2).pop()
{% endhighlight%}
<p>思考：其他人利用了一个A XOR A = 0的特性，遍历列表，将所有元素计算异或，最终结果就是出现一次的数，对异或运算不够熟悉，太笨了，代码如下：</p>
{% highlight python %}
        return reduce(operator.xor,nums)
{% endhighlight %}
