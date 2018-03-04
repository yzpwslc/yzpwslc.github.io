---
layout: post
title:  "leet561"
author: "yzpwslc"
date: 2018-03-03 16:20
---

   <p>题目：将一个有2n个整数的数组，划分为2个一组的数据对，使得数据对最小值之和最大。</p>
   <p>分析：要求数据对最小值之和最大，即每个数据对差的绝对值之和最大，也就是每个数据对两个数据尽可能接近。通过将数组排序后，依次组合获得的数据满足要求</p>
   <p>代码如下：</p>
   {% highlight python %}
import json
class Solution(object):
    def arrayPairSum(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        nums.sort()
        newNums = nums[::2]
        ret = sum(newNums)
        return ret


def stringToIntegerList(input):
    return json.loads(input)


def intToString(input):
    if input is None:
        input = 0
    return str(input)


def main():
    import sys
    def readlines():
        for line in sys.stdin:
            yield line.strip('\n')

    lines = readlines()
    while True:
        try:
            line = lines.next()
            nums = stringToIntegerList(line)

            ret = Solution().arrayPairSum(nums)

            out = intToString(ret)
            print out
        except StopIteration:
            break


if __name__ == '__main__':
    main()
   {% endhighlight %} 		


