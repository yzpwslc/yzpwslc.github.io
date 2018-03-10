---
layout: post
title:  "leet733.Flood Fill"
author: "yzpwslc"
date: 2018-03-10 12:21
---

<p>题目：对一个代表图像的二维数组，进行‘flood fill’操作</p>
<p>分析：替换指定位置为新的颜色，查找四个方向相邻元素，递归操作</p>
<p>代码如下：</p>
{% highlight python %}
        m = len(image)
        n = len(image[0])
        def cellFloodFill(sr,sc,newColor):
            temp = image[sr][sc]
            if temp == newColor:
                return 0
            image[sr][sc] = newColor
            if sr > 0 and image[sr - 1][sc] == temp:
                cellFloodFill(sr - 1,sc,newColor)
            if sc > 0 and image[sr][sc -1] == temp:
                cellFloodFill(sr,sc - 1,newColor)
            if sr < m - 1 and image[sr + 1][sc] == temp:
                cellFloodFill(sr + 1,sc,newColor)
            if sc < n - 1 and image[sr][sc + 1] == temp:
                cellFloodFill(sr,sc + 1,newColor)
        cellFloodFill(sr,sc,newColor)
        return image
{% endhighlight%}
<p>思考：如果新颜色与旧颜色一致，则不操作，否则会死循环</p>
