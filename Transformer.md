# Transformer

Transformer 是谷歌在2017年提出的经典NLP模型，有“变形金刚”之称，利用self—attention机制，不采用RNN的顺序结构，使得模型可以并行训练，能够兼顾全局。

TF框架简单来说就是在编码译码的过程，利用attention机制，对不同词语赋予不同权重，在这种情况下解码，就可以兼顾整体和局部，且可以分析长句

Transformer 由两部分组成，Encoder（编码器）和Decoder（解码器）两部分。



![image-20230710203519767](C:\Users\Luyao\AppData\Roaming\Typora\typora-user-images\image-20230710203519767.png)

Encoders与Decoders包括两部分self—attention（自注意力机制）和feed forward（前馈神经网络）

Encoder模块也被称为自编码（auto-encoding）模型，在每个阶段注意力层都可以访问到原始的输入句子中的所有词语，即具有“双向”注意力。纯 Encoder 模型通常通过破坏给定的句子（例如随机遮盖其中的词语），然后让模型进行重构来进行预训练，最适合处理那些需要理解整个句子语义的任务，例如句子分类、命名实体识别（词语分类）、抽取式问答。（BERT）

Decoder模块，每个阶段对于给定的词语，注意力层只能访问句子中位于他之前的词语，即只能迭代的基于已生成的词语来逐个预测后面的词语，也被称为自回归（auto-regressive）模型

Encoder-Decoder 模型（又称 Seq2Seq 模型）同时使用 Transformer 架构的两个模块。在每个阶段，Encoder 的注意力层都可以访问初始输入句子中的所有单词，而 Decoder 的注意力层则只能访问输入中给定词语之前的词语（即已经解码生成的词语）。****

顺序：Transformer并没有像RNN那样输入的是时序的且有先后顺序，但是Tranformer并没有考虑顺序信息，故提出了另一个概念位置编码：给每个词向量加上有顺序的特征向量（利用$sin$       

$cos$函数）

![img](C:\Users\Luyao\AppData\Roaming\Typora\typora-user-images\image-20230710204605902.png)





参考：https://zhuanlan.zhihu.com/p/82312421

http://jalammar.github.io/illustrated-transformer/