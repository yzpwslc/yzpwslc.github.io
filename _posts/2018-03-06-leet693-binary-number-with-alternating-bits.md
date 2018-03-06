---
layout: post
title:  "leet693"
author: "yzpwslc"
date: 2018-03-06 20:49
---

<p>题目：指定整数二进制形式相邻两位是否想同</p>
<p>分析：将整数转化为二进制的字符串形式，查找是否存在相邻位相同的情况(即11或00)</p>
<p>代码如下：</p>
{% highlight python %}
        return  bin(n).find('11') + bin(n).find('00') < -1
{% endhighlight%}
<p>思考：看了一下别人的代码，采用位运算，对于满足条件的整数，将其右移1位，与原数取异或，得到的数所有位均为1,根据这一思路，代码如下：</p>

{% highlight python %}
        num = n  ^ (n >> 1)
        return (num ^ (num + 1)) >> 1 == num
{% endhighlight%}
