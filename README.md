# Normalization

+ **Batch Normalization: Accelerating Deep Network Training by Reducing Internal Covariate Shift**
> 原始数据经过标准化处理后输入网络，通过多层网络的运算后，导致数据分布发生偏移，可能会落入激活函数的失活部分或者梯度较小部分，造成训练收敛过程较慢，因此BN在每个mini-batch将运算结果输入到激活函数前对数据进行标准化处理，使其分布满足0均值1标准差，同时通过引入可学习参数$\gamma$和$\beta$将标准化后的分布进行缩放和平移，使其能够标准化到一个合适的分布，因而能够有效提升网络训练的收敛速度和泛化性能。

+ **Instance Normalization: The Missing Ingredient for Fast Stylization**
> 将一张风格图像（style）和一张内容图像（content）通过网络进行融合被称为风格化（stylization），当将网络中的批标准化替换为样本标准化时，即对每个样例和通道计算各自的均值和方差进行标准化，能够有效提升生成风格化图像的质量。

+ **Group Normalization**
> 是一种Instance Normalization和Layer Normalization的普遍情况，将所有通道（神经元）分为多个组，每组内进行均值和方差的计算，同时每个通道再通过缩放和平移参数进行调整，能够有效克服Batch Normalization在小batch情况下性能的下滑。

+ **Layer Normalization**
> 计算一个样本在所有神经元上输入的均值和方差用于标准化，因此不受小batchsize的影响，同时能够有效应用于RNN中。

+ **Weight Normalization: A Simple Reparameterization to Accelerate Training of Deep Neural Networks**
> 不同于其他几种normalization的方法对特征进行处理，WN对模型参数进行重参数化操作以提升模型训练的收敛速度，通过将权重向量分解为模长和方向向量两个参数实现重参数，但该方法对模型参数的初始化有一定要求。

+ **Differentiable Learning-to-Normalize via Switchable Normalization**
> 提出将BN、LN、IN三种方法统一的标准化方法——SN，引入6个控制参数（加权系数）分别将BN、LN、IN计算得到的均值和方差统计量进行加权组合，在网络训练的过程中同时对这6个参数进行学习，SN能够在不显著增加计算量的前提下在多种任务场景下提升模型的性能。

+ **Cosine Normalization: Using Cosine Similarity Instead of Dot Product in Neural Networks**
> 采用输入向量和权重向量的夹角余弦代替输入向量和权重向量的点积，从而使得在输入激活函数前的结果被约束在±1之间，具有更稳定更好的模型性能，同时也可以采用中心化的点积，即皮尔森相关系数。