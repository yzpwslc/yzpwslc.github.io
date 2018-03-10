---
layout: post
title:  "leet122.best time to buy and sell stock"
author: "yzpwslc"
date: 2018-03-10 09:54
---

<p>题目：根据价格序列，计算在此区间可获最大利润</p>
<p>分析：对序列进行差分判断，获得上涨列表，遍历上涨列表，依次将价格上涨部分加入，并求和</p>
<p>代码如下：</p>
{% highlight python %}
        return  sum([prices[i + 1] - prices[i] for i,x in enumerate([prices[i] - prices[i+1] < 0 for i in range(0,len(prices) - 1)]) if x])
{% endhighlight%}
<p>思考：1.也可以直接将上涨列表作为过滤器，截取价格表区间，计算区间涨幅，求和。2.该题不够严谨，现实中股票也有做空赚钱，应该强调只能做多。</p>
