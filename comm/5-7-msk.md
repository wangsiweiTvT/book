---
layout: post
title: 最小频移键控
---

最小频移键控（MSK）是一种神奇的二元 FSK。它有以下特征：

首先，它的两个频率“正交”，以减小载波间的相互干扰，提高频谱利用率。这有两个结果：

第一个结果是：它的两个频率的差正好是 $$R_b/2$$。因此，如果我们画出它的波形，会发现它的两种码元包括的载波周期的数目，会差 1/2。

第二个结果是：它两个频率的值是 $$R_b/4$$ 的整数倍。因此，如果我们画出它的波形，会发现它的两种码元包括的载波周期的数目，一定是 1/4 个周期的整数倍。

其次，它的波形是连续的，也就是说，它是一种连续相位的 FSK。这一点非常重要。它带来的直接后果就是，它的有效性，即带宽非常低：等于 $$1.5 R_b$$。这一结果超出了我们的想象，因为 ASK 的带宽都还有 $$2 R_b$$ 呢！怎么 FSK 比 ASK 还小了？没错。这就是我们的前辈的神奇的创造。

最后，它的生成非常简单，也能利用类似 QAM 那样的两路并行的 ASK 方式实现。听到这里的时候，已经熟悉了 QAM 和 PSK 的星座图的你，是不是觉得听错了？因为这是 2 FSK，它应该只有 2 个星座点啊，怎么会像 QAM 那样用两路 sin 和 cos 传输？没错。那么，如果我告诉你，它实际上利用了 4 个星座点，你作何感想？有没有一点崩溃的感觉。

这就是我们的 MSK。下面我们来看它是怎么被设计出来的。

## MSK 信号的连续相位模型

我们首先建立它的连续相位条件。我们引入“附加相位”的概念。它指的是我们的信号在两个载波的“中频”带来的相位变化之外，“附加”的相位变化。显然，它是随时间变化的一个线性函数：当信号频率比“中频”高时，它会随着时间而线性增长；而当信号频率比“中频”低时，它会随着时间而线性减少；这个增长和减少的斜率就是 $$R_b/4$$。因此，我们可以把它表示为一个线性函数。

我们然后获得该线性函数的“截距”的约束条件，即：为了在连续两个符号周期的间隔处，保持信号的相位连续，我们需要前后两个符号比特的附加相位的截距满足如下两个约束条件：

第一个约束条件是：当两个比特的值相等时，截距 $$x$$ 保持不变。这一点很好理解：两个比特的值相等时，我们的信号频率也不变化，所以“附加相位路径”的线性函数是不变的，那它的截距自然也不变化。

第二个约束条件是：当两个比特的值不等时，截距 $$x$$ 会发生变化，变化的幅度是 $$n \pi$$，这里的 n 是比特的序号。假设 $$x$$ 的初始值是 0，这个性质告诉我们 $$x$$ 会是 $$\pi$$ 的整数倍。这个性质非常有用。

## MSK 信号的正交载波调制

我们然后获得 MSK 信号的正交载波调制的表示形式。我们对它的带有附加相位形式的信号公式进行展开。这时，我们就可以利用 “x 是 pi 的整数倍”这个性质，对它进行化简。这就得到了它的正交载波调制的表示形式。

从 MSK 的正交载波调制表示形式中我们可以发现两点：

第一点是：它的两路信号，一路是 $$cos(x)$$，另一路则是对 $$ cos(x)$$ 的“空号差分”的结果。我们分别用 p 和 q 来表示它们。

第二点是：这两路信号，首先要经过一个周期为 4 TB 的 sin 或 cos 的信号相乘，然后再去和“中频”的载波相乘。

只要满足了上面两点，我们就能得到连续相位的 MSK 调制信号。这是不是非常神奇？

而且，它的两路信号，还满足一个神奇的性质，即：当 n 为偶数时，p 这一路信号不变，当 n 为奇数时，q 这一路信号不变。这让你想到了什么？是不是想到了 OQPSK ？是的，就是这么神奇。你会想，这是 MSK 的设计者事先想要这么设计，还是她设计出来后，发现它有这样的特征的呢？有兴趣的同学，可以探索这个问题。

我们最后证明一个神奇的方法，那就是要得到 p 和 q，我们只需要初始化一个 x，得到它的 cos x，作为 p 这路信号的起始值（记作 p1），然后，基于输入比特不断做“空号差分”，就能够得到 p，q 相间的值。

我们首先证明 q2 是 p1 和 a2 的空号差分。因为 p 在 n 为偶数的时候，不变，因此 p2 = p1，而 q2 是 p2 和 a2 的空号差分，所以 q2 = p1 和 a2 的空号差分。

我们然后证明 p3 是 q2 和 a3 的空号差分。因为 q 在 n 为奇数的时候，不变，因此 q3 = q2，而 p3 是 q3 和 a3 的空号差分，所以 p3 = q2 和 a3 的空号差分。

我们的 PPT 上有张鹏学长的另一个证明，请大家感受。

总结上面的内容，我们最后就得到了 MSK 的正交载波调制生成方法。它包括四步：

首先，对输入比特 a 做“空号差分”，得到 b。

然后，将 b 做“串并转换”，分为 p 和 q 两路。其中 q 的这一路，延时 $$T_b$$。

然后，将 p 和 q 分别和周期为 $$4 T_b$$ 的 cos 和 sin 波形相乘。

最后，将乘完的波形，分别做 cos 和 sin 的正交载波调制，然后相减，就得到了连续相位的二元调频信号 MSK。

怎么样？神奇吗？

## 在实际系统中的优化

在通过数学分析，完成了 MSK 的上述设计后，在实际系统的时间中，我们聪明的前辈又做了如下两个优化：

第一个优化是：因为差分编码也是生成 +1/-1 的比特，所以，我们可以跳过这一步，直接发生 +1/-1 比特，也是可以的，对吧？这样就节省了“差分编码”这一步，降低了系统的复杂性和成本。

第二个优化是：当我们送进去的基带信号波形是 +1/-1 这样的方波时，我们的波形在两个连续符号的间隔处，会突然从一个频率变成另外一个频率，这种频率的突变还是不太好。因此，我们能不能像基带调制中的“波形生成”那样，不是送进去方波，而是送进去一个比较光滑的基带信号波形呢？答案是肯定的。因为我们的基带信号是控制发生信号的频率的，所以，这时，我们的“附加相位”的变化曲线，就不是两条直线了，而是变得光滑了起来。如果我们用“高斯低通滤波器”来把输入矩形脉冲变得光滑一些，这样获得的 MSK 就叫 GMSK。我们的第 2 代蜂窝移动通信系统 GSM 就是采用这种方法哦！GMSK 的好处是它的信号频谱的旁瓣比 MSK 下降得更快，因此能够减少用户之间的干扰。但是，我们知道，有得必有失。因为把基带信号的波形变宽了，它的码间干扰也会增加。

## MSK 的解调

我们下面来看 MSK 的解调。如果我们来观察一下 MSK 信号的功率谱，就会发现，它的两个频率很难分开了。因此，它不能通过我们前面讲过的、先带通滤波器滤出各个频率的 ASK、做 ASK 解调，然后做比较判决的 FSK 解调方法。那么，它怎么解调呢？

第一种解调方法，当然是通过鉴频器，做非相干解调。这是因为它不管怎么样，还是一个 FSK，所以，从它的信号的频率变化，就可以“鉴别”出来，它传输的是 1 还是 0。

第二种是与它的正交载波调制方法相对应的解调方法。我们回忆一下，它是用 p 和 q 的“相同还是不同”来传递信息的：如果 a 是 -1，p 和 q 就不同；a 是 +1， p 和 q 就相同。因此，我们通过这个规律，就可以从 p 和 q 这两路信号中，恢复出 a 出来。

## MSK 的星座图理解

我们最后看 MSK 信号的星座图。因为有 cos 和 sin 两个分支，所以，如图所示，它有四个星座点。首先，当 a 是 +1 时，它有两个星座点，分别在第一象限和第三象限。这时，p 和 q 是同号的；而当 a 是 -1 时，它的两个星座点，分别在第二象限和第四象限；这时，p 和 q 是异号的。

基于这张图，我们也可以感受到 MSK 的工作过程。因为 p 在奇数的时候不变，q 在偶数的时候不变，所以，当 MSK 工作时，它的信号点，是在这四个星座点组成的矩形上移动的，不会像 QPSK 那样，会在对角线上移动，这样就避免了 QPSK 的“零包络”问题。

## 小结

我们要能够理解 MSK 的原理，画出它的波形（包括正交载波调制的各个步骤的波形）。最后，请大家一定要记住：MSK 的带宽是 1.5 $$R_b$$。它就是这么神奇地获得的。

<br/>

|[Index](./) | [Previous](5-6-quiz) | [Next](5-8-quiz) |