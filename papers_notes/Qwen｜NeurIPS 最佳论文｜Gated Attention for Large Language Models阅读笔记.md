本质其实是在SDPA后加入了一个门控机制，这个idea之所以可以work是因为

A=$\operatorname{softmax}\!\left(\frac{QK^{T}}{\sqrt{d}}\right)$  $Q,K\in\mathbb{R}^{n\times d}$

$\operatorname{rank}(QK^{T})\le d$

本质上embedding 维度 d 决定最大 rank，理论上最大rank不会改变，变的是effective rank

奇异值、特征方程全忘了哦，要补一下

反正意思就是：

* 奇异值越均匀 → effective rank 越大
* 奇异值集中 → effective rank 小。

加了门控机制的，奇异值比较均匀，所以effective rank越大，相当于说能表示的信息更多了。
