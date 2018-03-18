---
layout: post
title:  "INstall tensorflow with GPU"
author: "yzpwslc"
date: 2018-03-18 00:41
---

<p>支持GPU的tensorflow要求显卡的compute capability >= 3.0，之前查询nvidia官网，把1000M同本机的K1000M混淆了，一致以为自己的古董机不支持，后来不甘心又查了一下，才发现刚好3.0.废话不多说了，本次安装的硬件环境为THINKPAD W530(CPU I7-3740QM@2.7GHzx8,显卡 Quadro K1000M 2G)。<br>软件环境：ubuntu16.04LTS python2.7。</p>
<p>采用的是tensorflow提供的pip专用whl文件(github上)。安装过程被某中文社区古老的教程坑了个遍，掉进了各种坑，最终几经折腾才爬了出来。</p>
<p>安装前的依赖环境配置：<br>
{% highlight %}
sudo apt-get install python-numpy swig python-dev
{% endhighlight %}
</p>
<p>CUDA</p>
{% highlight markdown%}
[下载cuda8.0](https://developer.nvidia.com/cuda-80-ga2-download-archive)
{% endhighlight %}
<p>直接下载runfile，按照官方使用说明运行。</p>
<p>cuDNN</p>
{% highlight markdown%}
[下载cuDNN](https://developer.nvidia.com/rdp/cudnn-download)
{% endhighlight %}
<p>这是一个用于深度神经网络的GPU加速库，GPU版tensorflow必选，教程上的连接是V5版，当前的tensorflow新版使用时会报找不到libcudnn.so.6的错误，建议安装v6以上对应版本，下载解压后，将相应文件复制到cuda安装目录对应文件夹下，就ok了。</p>
<p>Bazel</p>
<p>源码编译工具，从源码安装必装。官网给了多种安装方法，如果使用 Using Bazel custom APT repository 安装，过程中出现个别来自googleapi.com的资源连接失败，无需担心，该地址没被墙掉，多试几次可以成功。</p>
<p>依赖环境安装好后，使用pip安装tensorflow，过程一切顺利。</p>
<p>测试时使用mnist</p>
{% highlight python%}
from tensorflow.examples.tutorials.mnist import input_data
{% endhighlight %}
<p>提示错误：</p>
{% highlight %}
m tensorflow.examples.tutorials.mnist import input_data
[libprotobuf FATAL google/protobuf/stubs/common.cc:79] This program was compiled against version 3.3.0 of the Protocol Buffer runtime library, which is not compatible with the installed version (3.5.1).  Contact the program author for an update.  If you compiled the program yourself, make sure that your headers are from the same version of Protocol Buffers as your link-time library.  (Version verification failed in "external/protobuf_archive/src/google/protobuf/any.pb.cc".)
terminate called after throwing an instance of 'google::protobuf::FatalException'
  what():  This program was compiled against version 3.3.0 of the Protocol Buffer runtime library, which is not compatible with the installed version (3.5.1).  Contact the program author for an update.  If you compiled the program yourself, make sure that your headers are from the same version of Protocol Buffers as your link-time library.  (Version verification failed in "external/protobuf_archive/src/google/protobuf/any.pb.cc".)

{% endhighlight%}
<p>使用pip安装的protobuf版本太高，需要降级为3.3.0版本</p>
<p>折腾完后，tensorflow终于可以正常使用了</p>
