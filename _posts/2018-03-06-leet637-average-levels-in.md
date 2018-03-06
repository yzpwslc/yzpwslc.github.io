---
layout: post
title:  "leet673"
author: "yzpwslc"
date: 2018-03-06 20:23
---

<p>题目：计算给定二叉树每层节点平均值</p>
<p>分析：用深度优先(DFS)或广度优先（BFS）遍历二叉树，累加每层节点值，以及个数，输出平均值</p>
<p>代码如下：心情不好写单行程序</p>
{% highlight python %}
        return [-1 if len(sorted(nums[nums.index(x):])[sorted(nums[nums.index(x):]).index(x):]) < 2 else nums[min([nums.index(y) for y in sorted(nums[nums.index(x):])[sorted(nums[nums.index(x):]).index(x) + 1:]])] for x in findNums]
{% endhighlight%}
<p>思考：其他思路 遍历原数组 将满足较大值特性的元素与对应元素存入字典</p>
<p>别人的代码：</p>

{% highlight java %}
    public int[] nextGreaterElement(int[] findNums, int[] nums) {
        Map<Integer, Integer> map = new HashMap<>(); // map from x to next greater element of x
        Stack<Integer> stack = new Stack<>();
        for (int num : nums) {
            while (!stack.isEmpty() && stack.peek() < num)
                map.put(stack.pop(), num);
            stack.push(num);
        }   
        for (int i = 0; i < findNums.length; i++)
            findNums[i] = map.getOrDefault(findNums[i], -1);
        return findNums;
    }
{% endhighlight%}
