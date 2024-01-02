---
layout: post
title: 理解数据的范围
---

有了问题或拿到数据后，我们首先要分析问题的目标人群和数据的接入人群，这就是数据范围（Scope）的问题。

## 目标人群和访问框架

数据的范围有两个方面：首先，对于我们研究的问题来说，它指的是该问题的“目标人群”是哪些。其次，对于我们收集的数据来说，它指的是这个数据的“访问框架”（Access Frame），就是它实际接入，进行测量和观察的人群。

让我们看四个例子：

第一个例子是研究“奖励对网络用户做出贡献的激励作用”。比如“知乎”这样的网站，它靠的是用户贡献内容。那么，这个网站的运营者想分析一下：如果我发奖的话，用户是不是会更加积极地回答问题呢？这就是他的问题。那么，针对这个问题，他怎么设计实验呢？你看他首先画一个大框，这个框就是他的所有用户。但当他把所有的这些用户画出来之后，他发现啊，有一部分人现在已经在收网站的奖励金了。所以这时他就明白，他要把实验面向的“目标人群”是这些“还没有收到奖励的人”。那么，他不能给所有的这些人都发奖励吧？他肯定只能随机地挑选一部分人，发发奖励，然后和那些没有受到奖励的人比较，看发奖励的人是不是贡献的更多，这样来做实验。所以他的 Access Frame 就是他在这些“还没有收到奖励的人”中，随机选一些人。

上面这个例子说明了思考数据范围的好处，即：通过思考数据范围，我们就发现了有一些用户已经收到了奖励，他们不是我们要研究的问题的“目标人群”，所以得把他们从我们的实验中排除掉。这样也就确定了我们实验的 Access Frame。否则，我们就会错误地包括这些已经收到了奖励的人，那么他们的行为就会干扰我们最后的实验结果，比如让我们误以为奖励的激励作用并不大。这就从一开始就把整个实验引入了歧途，让后面所有的工作都白费了。

第二个例子是选举的民调。选举之前，大家都想先通过民调，做个随机抽样调查，预测一下谁赢。那么，在做调查之前，第一件事也是要研究一下数据的 Scope。为此，我们就会画两个框：下面这个框是那些真正会投票的人，但是有些人在框的外面，因为他是不会去投票的。那么，我们的“目标人群”其实是框里的人。那么，如果我们实验的 Access Frame 控制得不好的话，我们会抽样到框外的这些不投票的人。那么，他都不投票，你去抽样他，有啥用？甚至会调查的结果带来偏差。

第三个例子是对环境危险因素的探索。我们发现我们获得的数据是把一个城市分成了很多的小格子，每个格子里记录了它里面的环境危险因素，比如这个小格子里面有一个垃圾场，那个小格子里面有一个化工厂。然后每个格子里还记录了小格子里面的人的平均健康指标，比如哮喘发病率、白血病发病率，等等。那么，拿到这个数据后，我们就要分析它的 Scope。我们就会发现，它的 Access Frame 是以小格子为单位的。它只给出了一个格子里的人的平均健康情况，它不能区分每个人会怎么样。因此，如果我们想要研究的目标人群是“个人”，那么它们就不匹配。所以，如果有人说，基于这个格子的数据，得到了面向“个人”的研究结果，我们就要明白他的数据是有缺陷的。

第四个例子是自然科学测量数据的 Access Frame。考虑自然科学数据的 Access Frame，需要注意三个东西：第一是数据测量的点位，第二是仪器的准确性，第三是测量样本的情况，比如多少。这些都直接影响研究的有效性。

所以，在问题提出，或者拿到一个数据后，分析数据的 Scope 是首先要做的事，而且必须细致，因为它决定了整个研究的有效性。因为如果目标人群和 Access Frame 不匹配的话，就会从一开始就把整个研究引入歧途，后面所有的工作做得再好，也是白费了。大家要首先要根据我们的问题分析目标人群，然后再比较数据的 Access Frame，看它们匹不匹配。

无论是自己做实验，还是网上下载公开数据，一定要首先确认它的数据范围是否和我们的目标人群匹配。我们的数据一般有两种数据来源。一种是我们专门为了这个问题做实验，收集的数据。比如用户调查，我们自己去测；还有一种就是我们在网上 kaggle 这些网站下载的公开数据。前一种的开销大一点，后一种就比较简单一点。无论是哪种，大家用起来都要非常小心。这个很重要，否则的话后面的所有分析都是无效的，结论也是错的。

收集了数据之后，首先要做的，是检查数据质量，并进行数据清洗，对其进行必要的变换等等。我们要检查数据是否有缺失值，异常值，或者其它异常。评估数据的代表性，是否有偏差，可信性如何等等。确保最后进行分析的数据，是高质量的。我们也要对数据做必要的变换，比如把一些编号，替换为有意义的文本，方便后续分析；或者对一些值进行 Log 变换。这些工作都非常重要。

总之，来了一个数据之后，首先要请大家思考一下三个东西：第一个是这个问题的目标人群是什么；第二个是这个数据的的访问框架是什么。访问框架这个词是英文翻译过来的，叫做 Access Frame，就是这个数据是从哪些人那里访问得到的。第三个是看它们是不是匹配。这三个问题是最重要的。用术语说，就是数据的 Scope（范围）。这是因为我们能够测量的人群，是有限的。如果 Access Frame 和目标人群不匹配的话，测量得到的样本就会有偏差。那一旦你的样本就有偏差，那你这个数据分析出来的结果，就可能是错的，就并不能够完整地帮助你做准确的决策，反而带来错误的决定。这后果就严重了。所以，要首先思考这三个问题。

## 小结

我们接到任何一个数据科学的任务和数据后，要问下面几个问题：

- who & why：这个数据是谁收集的，他为什么要收集？他收集的目的，可能和我们的研究目的不一样。这样的话，要评估它的 Access Frame 和我们的目标人群是否匹配，以决定这个数据是否适用于解决我们感兴趣的问题。
- when & where：数据是在哪里收集的，在何时收集的。这个数据是不是已经“老”了，它收集的地方是不是和我要面对的问题的地方不一样？
- 目标人群和测量方法：用了什么仪器，怎么校准的仪器，用什么方法来选择的样本，怎么访问这些目标人群的，怎么记录的控制变量

## 参考文献

- 辛普森悖论，[Wikipedia](https://zh.wikipedia.org/wiki/%E8%BE%9B%E6%99%AE%E6%A3%AE%E6%82%96%E8%AE%BA)

<br/>

|[Index](../) | [Previous](13-1-lifecycle) | [Next](13-3-error)|
