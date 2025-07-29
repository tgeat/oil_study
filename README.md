---
description: 一种可以实现油藏模型预测与计算的算法，其主要目的是为了解渗流控制方程，即一个非稳态偏微分方程。
---

# 无网格算法

1.计算流程

test

2.Dirichlet边界条件

2.1 偏微分方程是什么：偏微分方程是一个包含时间和空间等多个自变量的方程，方程中包含一个物理量（如温度、压力、位移等）对这些自变量的偏导数。求解这个偏微分方程的目的，是为了在任意时间和空间点上，得到该物理量的数值分布。

知道偏微分方程是什么，并知道解偏微分方程的目的就是为了获取某一时间，某一空间的物理量的值，下一步就是开始看如何解偏微分方程。

2.2 求解一个偏微分方程都需要什么：

a.偏微分方程本身

b.初始条件

<figure><img src=".gitbook/assets/image (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

c.边界条件

<figure><img src=".gitbook/assets/image (3) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src=".gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

d.求解域和时间范围

e.其他确定的物理性质的参数的值

f.离散偏微分方程的离散方法

对于边界条件来说，分别有三种边界条件：

<figure><img src=".gitbook/assets/image (2) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src=".gitbook/assets/image (1) (1).png" alt=""><figcaption></figcaption></figure>

综上最终可以得到，dirichlet边界条件就是控制了空间边界上的物理值。

在渗流过程中，控制含水饱和度和聚合物浓度为固定的物理值的实际意义就是，在边界源源不断的注入对应的含有聚合物的水来进行驱油。

3. 守恒方程的构建

<figure><img src=".gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

<figure><img src=".gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

其中源汇项q，正负及其实际物理意义为：

<figure><img src=".gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

<figure><img src=".gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

此时当前点的流入流出和注入采出可以实现平衡。

4. 获取所有的物质守恒方程（构建要求解物理量的偏微分方程）：

水相的物质守恒方程；油相的物质守恒方程；总的物质守恒方程；聚合物的物质守恒方程。

5. 将总的物质守恒离散化求解偏微分方程：

5.1 将物质守恒方程积分

5.2 积分以后对达西速度的散度的积分应用散度定理：

<figure><img src=".gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src=".gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

积分完以后，并且应用完散度定理后：

<figure><img src=".gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

散度定理就是一个区域产生或消失了多少的流体，就等于此区域的边界即表面一共流出流入多少。
