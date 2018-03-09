---
layout: post
title:  "leet169.majority element"
author: "yzpwslc"
date: 2018-03-09 23:36
---

<p>题目：选出数组的主元素</p>
<p>分析：用常规的思维，利用集合找到数组中有哪些数，统计，计算出最大值</p>
<p>代码如下：</p>
{% highlight python %}
        oneDarr = reduce(lambda  x,y:x + y,nums)
        elementArr = list(set(oneDarr))
        countsArr = [oneDarr.count(x) for x in elementArr]
        return elementArr[countsArr.index(max(countsArr))]
{% endhighlight%}
<p>思考：1.由于主元素数目大于一半，因此可以对数组排序，中间位置的数即为主元素。2.看到别人的一种解法，顺序遍历，取第一个值为主元素，遍历过程中计算出现次数，出现一次+1,不是该数则减1,计数为0时，选当前元素为主元素，一直到最后，由于主元素数量超过半数，因此最终一定会被选出</p>
<p>代码如下：</p>
{% highlight java %}
public class Solution {
    public int majorityElement(int[] num) {

        int major=num[0], count = 1;
        for(int i=1; i<num.length;i++){
            if(count==0){
                count++;
                major=num[i];
            }else if(major==num[i]){
                count++;
            }else count--;
            
        }
        return major;
    }
}
{% endhighlight %}
