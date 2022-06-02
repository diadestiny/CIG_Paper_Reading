# Super Resolution 超分辨率修复

**1. Blueprint Separable Residual Network for Efficient Image Super-Resolution** [paper](https://arxiv.org/abs/2205.05996) | [code](https://github.com/xiaom233/BSRN) NTIRE 2022 1st & CVPR2022 workshop*

author: Zheyuan Li, Yingqi Liu, Xiangyu Chen et al. Shenzhen Institutes of Advanced Technology, Chinese Academy of Sciences

> 1. 在[RFDN](https://openaccess.thecvf.com/content_CVPR_2020/papers/Liu_Residual_Feature_Aggregation_Network_for_Image_Super-Resolution_CVPR_2020_paper.pdf)的基础上，采用[BSConv(蓝图卷积)](https://arxiv.org/abs/2003.13549)提取shallow feature，BSConv是DSConv深度可分离卷积的变种，参数量少，减少冗余卷积操作。
>
> 2. 引入ESDB(Efficient Separable Distillation Block), 将原始RFDB模块的SRB改成带BSConv的BSRB进行特征浓缩/细化，引入ESA增强空间注意模块和CCA对比度感知通道注意模块进行特征增强。

思考：ESA和CCA注意力模块虽然增加一定计算量，但采用BSConv优化卷积，相比于RFDN有效减少参数量。但是论文表明即使参数量的减少，推理速度并没有提高，初步猜测和注意力模块、多尺度级联并行Concat有关。

![image-20220602173802338](./screen/BSRN1.png)

![image-20220602173852170](./screen/BSRN2.png)

