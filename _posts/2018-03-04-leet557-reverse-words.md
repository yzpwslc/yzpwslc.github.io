---
layout: post
title:  "leet557"
author: "yzpwslc"
---

<p>题目：将字符串每个单词逆序输出</p>
<p>分析：将字符串分割为列表，将列表中每个子字符串逆序，再将列表组合为字符串</p>
<p>代码如下：</p>
{% highlight python %}
ass Solution(object):
    def reverseWords(self, s):
        """
        :type s: str
        :rtype: str
        """
        sList = s.split(" ")

        ret = [sList[i][::-1] for i in range(len(sList))]
        ret = ' ' . join(ret)
        return ret


def stringToString(input):
    return input[1:-1].decode('string_escape')


def main():
    import sys
    def readlines():
        for line in sys.stdin:
            yield line.strip('\n')

    lines = readlines()
    while True:
        try:
            line = lines.next()
            s = stringToString(line)

            ret = Solution().reverseWords(s)

            out = (ret)
            print out
        except StopIteration:
            break


if __name__ == '__main__':
    main()
{% endhighlight%}

