---
layout: post
title: 信号和噪声的基本模型
---

因为信号和噪声是通信系统研究的两个主要对象，所以我们首先建立信号和噪声的随机过程描述。

## 信号的平稳随机过程描述及其自相关函数

在通信原理中，我们分析随机变量和随机过程，特别是平稳随机过程。

首先，信源发送的信号是随机变量。正是因为我们接收端不能确定发送端会发送什么，我们才需要通信。因此，对于接收端来说，信源是随机的。比如，对于 2 进制离散信源，它有可能发 1 也有可能发 0。

然后，随机信号在通信系统中传输的过程是随机过程。比如，2 进制离散信源不断发出 1 或 0，它们在通信系统中传输，到达目的地，这个过程就是一个随机过程。此外，信号在传输中不断受到的“噪声信号”的影响，这一过程也是噪声的随机过程。

随机过程有一整套数学理论。我们讨论的是其中的一类特殊的随机过程：平稳随机过程，即：我们认为，我们发送的随机信号及其接受的噪声信号，在时间上都是平稳的。这符合真实通信系统中传输的信号和接受的噪声的特征。

一个最简单的模拟信源的例子，是一个载波发生器。因为它的初始相位是随机的，所以，它是一个相位随机的单音信号模拟信源。它是一个随机过程，可以被表示为：$$ s(t) = cos(\omega t + \theta), \theta \in [0,2\pi]$$。

对上述随机过程，在任一个时刻，它的取值是一个随机变量。这个随机变量随着 $$\theta$$ 的变化而变化，因此，我们可以求它相对于 $$\theta$$ 的期望。我们可以得到这个均值是 0。这意味着这个期望是常数，它不随时间的变化而变化，所以，它的期望是平稳的。为此，我们说它是“一维”平稳的。

类似的，我们可以计算间隔时间为 $$\tau$$ 的两个时刻的信号取值（它们是两个随机变量）的相关 $$E[XY]$$。我们会发现它只和这两个时刻的间隔时长有关，而和具体的时刻无关。为此，我们说它在“二维”上也是平稳的。我们并且把这个相关称为这个随机过程的“自相关函数”。

自相关函数对我们研究通信系统有重要的用途。首先，一个平稳随机过程的“自相关函数”在 $$\tau = 0$$ 时，$$E[X^2]$$ 就是它的平均功率。在 $$\tau = \infty$$ 时，$$E[XY] = E[X]E[Y] = E[X]^2$$。因为 $$E[X]$$ 是它的直流分量，所以 $$E[X]^2$$ 就是它的直流功率。其次，对于一个平稳随机过程，它有确定的功率谱，而且，它的自相关函数的傅立叶变换，就是它的功率谱。这就是著名的维纳－辛钦定理。

有了平稳随机过程的功率谱，我们就可以在频域上对我们的通信系统进行分析了。

## 高斯白噪声和窄带高斯噪声的正交载波调制形式

信号在信道里传输，会被加上高斯白噪声。高斯白噪声是一个符合高斯分布的噪声，而且它的功率谱密度是常数：如果从负无穷到正无穷来算的话，它的值是 $$ n_0/2 $$，这个叫“双边功率谱密度”。如果从 0 到正无穷来算的话，它的值是 $$ n_0 $$，这个叫“单边功率谱密度”。

我们在接收端收到一个信号以后，一般会经过一个带宽是 $$B$$ 的带通滤波器，把信号滤出来。这时，这个高斯白噪声也会被过滤得只剩下这个带通滤波器所在的这一块频率。此时的噪声功率就是 $$n_0 B$$。

如果这个滤波器的带宽相对于它的中心频率来说很小很小的话，比如我们听收音机，一个频点是 83.6MHz，它的带宽是 200K，这时带通滤波器的带宽相对于它的中心频率来说就很小很小。这时我们可以把它表示为 $$ n_i(t) * cos(wt) - n_q(t) * sin(wt) $$。

其中，$$ n_q(t) $$ 和 $$ n_i(t) $$ 是正交的，它们的相关系数是 0。它们都是平稳高斯过程，均值为 0，方差是$$n_0 B$$。

## 小结

我们建立了信号和噪声的基本模型。它们会在我们后面的通信系统的建模和分析中被用到。

<br/>

|[Index](./) | [Previous](0-5-quiz) | [Next](1-13-shannon) |