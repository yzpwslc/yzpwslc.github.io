---
layout: post
title:  "leet520"
author: "yzpwslc"
date: 2018-03-07 23:36
---

<p>题目：判断字符串大小写是否符合标准</p>
<p>分析：还是太过于偏爱正则表达式，想都没多想就用了正则</p>
<p>代码如下：</p>
{% highlight python %}
        ret = False
        pattern = re.compile(r'([A-Z]{1,})')
        if re.search(pattern,word):
            if re.search(pattern,word).start() < 1:
                if 1 < len(''.join(re.findall(pattern,word))) < len(word):
                    ret = False
                else:
                    ret = True
        else:
            ret = True

        return ret
{% endhighlight%}
<p>思考：别人的方法，简单、高效，代码如下：</p>
{% highlight python %}
return word[1:]==word[1:].lower() or word==word.upper()
{% endhighlight %}
