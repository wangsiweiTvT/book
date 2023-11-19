---
layout: post
title: 数字基带通信 Quiz
---

# 数字基带传输

1. 数字通信的优点是？
1. 什么是数字基带传输？什么是数字频带传输？什么是数字基带信号，什么是数字频带信号？可画图说明
1. 短距离有线信道上传输数字信号，通常用基带信号，还是频带信号？
1. 长距离无线信道上传输数字信号，通常用基带信号，还是频带信号？
1. 画出数字基带传输和数字频带传输系统的模型框图

# 数字基带信号

1. 什么是数字基带信号的码型？请举出几种基本码型
1. 码元周期和脉冲宽度的区别是？试举例说明
1. 什么是绝对码，什么是相对码？什么是传号差分，什么是空号差分？
1. 数字基带信号的时域表示可以分解为哪两部分，为什么？
1. 请写出数字基带信号随机序列的稳态波的时域表达式
1. 请写出数字基带信号功率谱密度函数中离散谱和连续谱的数学表达式，并根据数学表达式说明它们一定存在吗？
1. 数字基带信号功率谱，我们关心它的三个特征，是哪三个？为什么？
1. 单极性归零码数字信号功率谱的三个特征如何？请画出其功率谱（p=0.1. 占空比0.5）
1. 单极性不归零码数字信号功率谱的三个特征如何？请画出其功率谱（p=0.5）
11. 双极性归零码数字信号功率谱的三个特征如何？请画出其功率谱（p=0.1. 占空比0.5）
11. 双极性不归零码数字信号功率谱的三个特征如何？请画出其功率谱（p=0.5）
11. 100Mbps的单极性归零码（占空比0.5），有效带宽多少？
11. 100Mbps的单极性不归零码，有效带宽多少？

# 常用码型

1. 数字基带信号码型的可靠性和有效性用什么评估？
1. 分别画出1101001的双相Manchester码、CMI码、AMI码的数字基带信号波形，并分析其功率谱三个特性
1. 什么是AMI码的连0问题？如何解决？
1. 简述HDB3码的编码和解码过程
1. 根据HDB3码的编码过程，分析HDB3码的功率谱三个特性
1. 多电平码，M=1. 如每个码等概率出现，则每个码能传递几个bit信息？
1. 100Mbps的4电平码（每个码等概率出现），有效带宽多少？
1. 为什么CMI码有效带宽是2/T？
1. 为什么AMI码有效带宽是1/T？

# 波形形成

1. S-D-R 的英文全名是？
1. ISI 的英文全称是？
1. 画出基带传输系统的分析模型框图（无噪声），并写出码型编码输出和SDR输入的数学表达式
1. 结合框图，说明为什么会出现符号间干扰（码间干扰）？
1. 结合框图和SDR输入的数学表达式，给出无ISI时域条件的数学形式
1. 画图说明，为什么带宽为1/(2Ts)的低通滤波器产生的时域信号能够符合无ISI时域条件。其信道频带利用率多少？
1. 什么是奈奎斯特第一准则？它是无ISI的时域条件还是频域条件？写出其数学表达式。它的物理意义是？
1. 比较带宽为1/(2Ts)的低通滤波器和奈奎斯特第一准则，它是否符合该准则？
1. 符合奈奎斯特第一准则的滤波器的H(f)，关于哪个频点，怎么对称？我们称这样的滤波器是什么理想低通滤波器？
11. 为什么不存在信道频带利用率超过 2 符号/s/Hz 的无ISI数字基带传输系统？
11. 理想低通系统的H(f)是什么形状？它的信道频带利用率是多少？它是不是无ISI数字基带传输系统？它的时域波形有什么缺点？
11. 什么叫奈氏带宽？什么叫奈氏传输速率？什么叫基带理想传输？
11. 画出滚降系数为a的互补对称滚降低通系统的H(f)形状，标明奈氏传输速率B_N的位置。它的带宽是多少？信道利用率是多少？其时域特征有什么优点？
11. 什么叫全滚降？
11. 相对于理想低通系统，互补对称滚降低通系有什么优缺点？

# 部分响应系统

1. 画出相关电平编码的原理框图和数学表达式（发送/接收端）。为什么它叫“部分响应”？它发送的电平有几种？
1. 画出相关电平编码的冲激响应波形。该波形有什么优点？它符合奈氏第一准则的无ISI时域条件吗？为什么它能实现无ISI传输？怎么做到的？
1. 画出相关电平编码的系统传递函数。它的带宽是多少？是否达到奈氏带宽？信道利用率是多少？
1. 什么是奈氏第二准则？
1. 实际中相关电平编码可能会出现什么问题？如何解决？
1. 画出第一类部分响应系统的原理框图和数学表达式（发送/接收端）。为什么它叫“部分响应”？它发送的电平有几种？写出1100110011经过它传输时的每一步输出。
1. 实际系统中，第一类部分响应系统接收端的模2操作，可以用什么代替？举例说明此时系统的抗差错传播能力。
1. 第一类部分响应系统的缺点是？如何改进？
1. 画出第四类部分响应系统的原理框图和数学表达式（发送/接收端）。它发送的电平有几种？它的优点是？写出1100110011经过它传输时的每一步输出。
11. 部分响应信号的带宽是否达到奈氏带宽？信道的频带利用率是多少？
11. 部分响应系统在可靠性上的问题是？为什么？
11. 为什么I类和IV类应用广泛？

# 基带系统误码性能
1. 画图分析二进制基带信号传输的抗高斯噪声性能，写出其数学表达式、最佳阈值电平方程，在图上标出p(0)=p(1)时的最佳阈值电平，写出此时误码率的数学表达式，证明信噪比相同时，双极性的误码率低于单极性。
1. 影响基带系统误码性能的因素有哪些？说出误码率随它们变化而变化的规律。
1. 如何产生眼图？
1. 眼图可以用来做什么？
1. 分别画出存在和不存在码间干扰的眼图，解释产生这样的图形的原因
1. 分别画出存在和不存在噪声的眼图，解释产生这样的图形的原因
1. 画出一个眼图，标出最佳取样时刻、闭合斜率、噪声边际、可抽样时间、过零失真、最大信号失真量
1. 时域均衡的作用是？
1. 画出时域均衡滤波器在基带传输系统中的位置
11. 画出利用横向滤波器实现时域均衡的原理图，为什么它被称为“迫零”调整？

<br/>

|[Index](./) | [Previous](4-11-error) | [Next](5-3-2-ary) |