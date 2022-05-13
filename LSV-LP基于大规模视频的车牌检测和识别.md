## LSV-LP: Large-Scale Video-Based License Plate Detection and Recognition

## *LSV-LP基于大规模视频的车牌检测和识别*

#### 项目背景

------------

1. LPDR系统依靠CNN有了长足的进步，但仅仅限于小型和不具有代表性的数据集。
2. 传统LPDR系统在复杂自然环境中表现不佳。
3. 传统基于单张图像，现实中信息源往往基于视频，主流忽略了连续帧职之间的动态线索。
4. **LSV-LP：**大规模视频车牌数据集，具有多个车牌，更贴切复杂实际。
5. **设计了MFLPR-Net框架。**
6. 通过对比该MFLPR-Net模型和其他主流方法的性能，**证明前者优于后者。**

#### 简介

-----------

1. LPDR系统基于CNN，主要做的是LP检测识别的。  *缺点：使用场景比较简单，不能适应复杂多变的现实环境.   (对AOLP进行举例)*
2. LPDR在图像距离变化\模糊度\天气变化\分辨率等等各方面有突出的优点.
3. 基于LSV-LP数据集,提出了一个MFLPR-Net的车牌识别网络.
4. 接下来文章介绍了几种不同的几个基于图像的数据集.
5. LP识别算法:传统模式匹配+基于深度学习的YOLO.

#### LSV-LP数据集

----------

1. LSV-LP数据集:数据收集与规范\标注工具\数据集特征三方面.
   - 摄影师和车之间的关系:动vs不动\ 动vs动 \ 不动vs不动\不动vs动
   - 使用标签工具*License_labeler*进行标注
   - 排除 resolution 小于20 * 8的情况帧.

2. 五个优点
   - Distrubitonal Diversity 分布多样性
   - Negative samples 消极样本
   - Temporal Complexity 时间复杂度
   - Various Resolution 多种分辨率
   - Large Appearacne Variation 大量的外观变化
   
3.  MFLPR-Net 多帧车牌识别网络（多尺度特征融合结构、引入仿射变换、将相邻帧的特征与检查帧的特征链接起来，而不是融合他们）

4. MFLPR-Net的优点

   - 不依赖于从前的多帧信息
   - 不需要将检测和追踪分开

5. 核心

   1. 检测模块。融合了VGG16和Resnet等网络为主干（提取四个不同大小的特征）.
   2. 光流模块。使用视频的上下文信息，增强检测帧的效果。

      - 光流模块检测模块是⼀个⽔平的处理过程，然而光流模块是⼀个穿插其中的垂直过程。
      - 其中C1表示1×1卷积层， wref表示特征frefi、fref-i的权重，它们相对于检查帧fcur是对称的。相邻帧的特征通过权重分配⽣成新的特征图fref，整合相邻帧的信息，对被检帧起到辅助作用。

   ![image-20220513160413413](https://gitee.com/datie666/images/raw/master/img/202205131604473.png)

   3. 识别模块。利用仿射变换进行修正。

      *注：仿射变换：一个向量空间进行一次线性变换并接上一个平移，变换为另一个向量空间。*

      - 目的是对形状不规则的车牌进行车牌识别，但是对车牌的识别准确率方面的问题有待提高。
      - 三大核心是：feature encoder, feature alignment and decouled text decoder   *特征编码器、特征对齐和解耦文本解码器*

   <img src="https://gitee.com/datie666/images/raw/master/img/202205051619723.png" alt="image-20220505161904641" style="zoom:33%;" />

6. 与主流且常用的车牌检测方法进行比较

   - LP检测方法

     - EfficientDet

     简单高效的加权双向特征金字塔Net，引入可学习的权重，进行多尺度的特征融合。

     - YOLOV3

     利用多尺度特征进行对象检测提升了预测进度，特别是针对较小的物体而言。

     - Faster-RCNN

     提出了区域建议网络，可以检测小的物体，但是牺牲了检测时间

     - SSD512

     不需要Pooling和RPN操作

     - DFF(Deep feature flow network)

     时间优势，利用光流网络

     - PLDNet

     通过回归LP的四个角来定位倾斜LP的四边形边界框

   - LP识别方法

     - CRNN

     CNN提取图像，RNN对序列进行预测，通过Connectionist Temporal Classification

     - Attention OCR

     注意力机制的文本识别方法，端对端训练。

     - MORAN

     弱监督方式训练。

     - DAN(Decoupled Attention Network)

     解耦比较重点

     - LPRNet

     不解和RNN的实时LP识别系统

### 总结

--------

1. 设计了一个基于大规模视频的LSV-LP数据集。*采用动静结合的拍摄手法*
2. 基于LSV-LP数据集，我们设计并且提出了一个MFLPR-Net的框架。结合了从被检查的相邻帧中提取的特征框架。
3. 留下三个问题
   - 如何结合上下文信息
   - 如何协调速度和精度
   - 优化系统中如何平衡检测和识别