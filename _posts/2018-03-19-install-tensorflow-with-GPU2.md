---
layout: post
title:  "INstall tensorflow with GPU"
author: "yzpwslc"
date: 2018-03-18 00:41
---

<p>支持GPU的tensorflow要求显卡的compute capability >= 3.0，之前查询nvidia官网，把1000M同本机的K1000M混淆了，一致以为自己的古董机不支持，后来不甘心又查了一下，才发现刚好3.0.废话不多说了，本次安装的硬件环境为THINKPAD W530(CPU I7-3740QM@2.7GHzx8,显卡 Quadro K1000M 2G)。软件环境：ubuntu16.04LTS python2.7。</p>
<p>采用的是tensorflow提供的pip专用whl文件(github上)。安装过程被某中文社区古老的教程坑了个遍，掉进了各种坑，最终几经折腾才爬了出来。</p>
