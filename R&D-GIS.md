---
layout: default
title: ArcGIS 关于高斯泼贱相关内容的学习心得
permalink: /zh/r&d/gis/
---

##### ArcGIS 在 2025年下半年更新了ArcGIS Pro 3.6版本，新增了关于高斯泼贱制作与发布的功能。

#### 首先，我们谈一谈目前哪些ArcGIS软件可以制作高斯泼贱

目前ArcGIS 可以制作高斯泼贱的产品有两个
一个是ArcGIS Reality
![ArcGIS Reality]({{ site.baseurl }}/assets/images/Pasted image 20260205152645.png "ArcGIS Reality")

一个是ArcGIS Pro
![ArcGIS Pro]({{ site.baseurl }}/assets/images/Pasted image 20260205152859.png "ArcGIS Pro")

ArcGIS Reality 适用大范围数据量，如城市级别，而ArcGIS Pro 则适用小范围的数据量，如典型的发电厂等工业园区。

#### 可以事前检查一下：

1.首先确认一下自己电脑的配置，官方要求CPU 至少配备 64GB RAM，Nvidia GPU 至少配备 8GB VRAM，并且计算能力为 7.5 或更高。（官方对这个要求很严苛，不满足则无法执行后续生成操作）2.下载并安装与 ArcGIS Pro 版本相关联的 ArcGIS Pro 深度学习库。地址是：https://github.com/Esri/deep-learning-frameworks 3.确认你的ArcGIS Pro版本，如3.6以下，则需要额外安装 ArcGIS Reality for ArcGIS Pro 插件，由于3.6及之后的版本默认安装包自带 ArcGIS Reality for ArcGIS Pro 插件，所以不用额外安装。（需要注意ArcGIS Reality for ArcGIS Pro的授权问题。）

#### 如何生成一个质量高的高斯泼贱模型

无人机影像的数据至少有 80% 的航向重叠和 60% 的旁向重叠，并将地面采样距离（GSD）保持优于5 厘米

#### 关于生成速度

目前有网友分享了自己的制作过程，虽然没有放出自己计算机的硬件配置，但可以作为参考。
一个小型工地，大概2000平方米，时间为7小时左右。

#### 如何加载

下面是官方生成的示例数据：
https://tiles.arcgis.com/tiles/z2tnIkrLQ2BRzr6P/arcgis/rest/services/Portcoast/3DTilesServer/tileset.json
可以通过ArcGIS API for JS 5.0及之后版本的GaussianSplatLayer类加载。
