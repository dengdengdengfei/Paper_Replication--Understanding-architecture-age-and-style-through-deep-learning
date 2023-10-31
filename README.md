# 论文复现——《利用深度学习来识别建筑年代和风格》

Paper Replication——《Understanding architecture age and style through deep learning》

## 一、文章目录

> 所有文章均可在[我的博客](https://cdn.renhai-lab.tech)和微信公众号（renhailab）中找到，欢迎关注！
> 📌 收录进专栏：【SCI论文复现】《通过深度学习了解建筑年代和风格》

- [Part1.论文解读：如何利用最近很火的深度学习来识别建筑年代和风格？——《通过深度学习了解建筑年代和风格》](https://cdn.renhai-lab.tech/archives/Understanding_architecture_age_and_style_through_deep_learning_part1)
- [Part2.下载和预处理建筑足迹数据集——《通过深度学习了解建筑年代和风格》](https://cdn.renhai-lab.tech/archives/Understanding_architecture_age_and_style_through_deep_learning_part2)
- [Part3-1.获取高质量的阿姆斯特丹建筑立面图像（上）——《通过深度学习了解建筑年代和风格》](https://cdn.renhai-lab.tech/archives/Understanding_architecture_age_and_style_through_deep_learning_part3-1)
- [Part3-2.获取高质量的阿姆斯特丹建筑立面图像（下）——《通过深度学习了解建筑年代和风格》](https://cdn.renhai-lab.tech/archives/Understanding_architecture_age_and_style_through_deep_learning_part3-2)
- [Part4-1.对建筑年代进行深度学习训练和预测——《通过深度学习了解建筑年代和风格》](https://cdn.renhai-lab.tech/archives/Understanding_architecture_age_and_style_through_deep_learning_part4-1)
- [Part4-2.对建筑年代进行深度学习结果进行展示和分析——《通过深度学习了解建筑年代和风格》](https://cdn.renhai-lab.tech/archives/Understanding_architecture_age_and_style_through_deep_learning_part4-2)
- [Part5.对建筑风格进行深度学习训练和预测以及分析——《通过深度学习了解建筑年代和风格》](https://cdn.renhai-lab.tech/archives/Understanding_architecture_age_and_style_through_deep_learning_part5-1)

## 二、仓库环境使用说明

1. 直接安装Python、或者使用Anaconda、Pycharm、VScode安装。
2. pytorch推荐单独安装，详见[PyTorch环境配置](https://cdn.renhai-lab.tech/archives/DL-01-pytorch#2.PyTorch%E7%8E%AF%E5%A2%83%E9%85%8D%E7%BD%AE)。
3. 其余依赖使用`pip install requirements.txt`。

## 三、仓库代码结构

使用方法：fork 本仓库，然后克隆到本地或者用Codespace打开。

```python
├── 1-论文阅读和解析
│   ├── Understanding architecture age and style through deep learning.pdf
│   └── 论文双语版：通过深度学习了解建筑时代和风格 - ScienceDirect.html
├── 2-获取数据集
│   ├── notebook
│   │   ├── 2.1-BAG建筑足迹数据预处理.ipynb
│   │   ├── 2.2-osmnx获取道路数据.ipynb
│   │   └── 2.2-通过streetview获取含有谷歌街景地图的网页url.ipynb
│   └── script
│       ├── 2.1-使用geopandas寻找街景点.py
│       └── 2.2-通过streetview获取含有url的csv文件.py
├── 3-selenium获取街景并进一步筛选街景图像
│   ├── notebook
│   │   ├── 3.1-2-删除损坏的文件.ipynb
│   │   ├── 3.1-selenium获取街景截图.ipynb
│   │   └── 3.2-语义分割预筛选街景照片..ipynb
│   ├── script
│   │   ├── 3.1-selenium多线程获取街景.py
│   │   └── 3.2-语义分割筛选街景完整代码.py
│   └── semantic-segmentation-pytorch-master.zip
├── 4.1-对建筑年代进行深度学习训练和预测
│   ├── models
│   ├── notebook
│   │   ├── 4.1.1-处理数据集不平衡的问题.ipynb
│   │   ├── 4.1.2-建筑年代的模型选择和训练.ipynb
│   │   ├── 4.1.3-对训练集进行预测并保存结果.ipynb
│   │   ├── 4.1.3-建筑年代模型评价3.ipynb
│   │   ├── 4.1.4-制作建筑年代预测结果的空间分布图.ipynb
│   │   ├── 4.1.6-使用ArcGIS-Pro和Arcy制作建筑年代预测结果在150米精度范围的准确度.ipynb
│   │   ├── 4.1.7-计算空间自相关(莫兰指数).ipynb
│   │   ├── 4.1.8-探讨建筑年龄和建筑风格的关系.ipynb
│   ├── script
│   │   ├── TS.py
│   │   ├── engine.py
│   │   └── train.py
├── 4.2-对建筑风格进行深度学习训练和预测
│   ├── models
│   ├── notebook
│   │   ├── 4.2.2-建筑风格模型评价.ipynb
│   ├── script
│   │   ├── engine.py
│   │   ├── predict.py
│   │   └── train.py
│   └── tensorboard-logs
├── LICENSE.txt
├── Tableau
├── data
│   └── output
├── my_tools
├── requirements.txt
└── tools
```

## 论文引用信息 Cite info

Maoran Sun, Fan Zhang, Fabio Duarte, Carlo Ratti,
Understanding architecture age and style through deep learning,
Cities,
Volume 128,
2022,
103787,
ISSN 0264-2751,
https://doi.org/10.1016/j.cities.2022.103787.
(https://www.sciencedirect.com/science/article/pii/S0264275122002268)
Abstract: Architectural styles and their evolution are central to architecture history. However, traditional approaches to understand styles and their evolution require domain expertise, fieldwork and extensive manual processes. Recent research in deep learning and computer vision has highlighted the great potential in analyzing urban environments from images. In this paper, we propose a deep learning-based framework for understanding architectural styles and age epochs by deciphering building façades based on street-level imagery. The framework is composed of two stages: Deep ‘Learning’ the architecture and Deep ‘Interpreting’ the architecture age epochs and styles. In Deep ‘Learning’, a deep convolutional neural network (DCNN) model is designed to automatically learn about the age characteristics of building façades from street view images. In Deep ‘Interpreting’ stage, three components are proposed to understand the different perspectives regarding building ages and styles. In the experiment, a building age epoch dataset is compiled for the city of Amsterdam and Stockholm to understand the evolution of architectural element styles and the relationship between building ages and styles spatially and temporally. This research illustrates how publicly available data and deep learning could be used to trace the evolution of architectural styles in the spatial-temporal domain.
Keywords: Building age; Architectural style; Street view imagery; Built environment; Deep learning

---

因为其他平台不能同步修改，论文解读文章将最先在[我的博客](https://cdn.renhai-lab.tech)发布，你可以点击[阅读原文](https://cdn.renhai-lab.tech/categories/Paper_Replication)查看本专题的所有文章。

如果你觉得本系列文章有用，欢迎关注博客，点赞👍和收藏，也欢迎在评论区讨论，有任何问题都可以私信我：

- [我的博客](https://cdn.renhai-lab.tech/)
- [我的GITHUB](https://github.com/renhai-lab)
- [我的GITEE](https://gitee.com/renhai-lab)
- 微信公众号: renhai-lab
- [我的知乎](https://www.zhihu.com/people/Ing_ideas)

<img src="assets/logo2.jpg" alt="更多账号" style="zoom:50%;" />
