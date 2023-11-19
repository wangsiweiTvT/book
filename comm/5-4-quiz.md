---
layout: post
title: 数字频带通信 Quiz
---

# 数字频带传输

## 数字频带传输系统

1. 画出数字基带传输系统的框图，解释每一部分的作用
1. 画出数字频带传输系统的框图，解释每一部分的作用
1. 数字频带传输系统有哪三个优点？为什么？
1. 数字频带调制的过程是怎样的？
1. 简述三种数字调制方法，画出其已调信号波形，开关/键控法生成器原理图

## ASK

1. 写出ASK信号的时域表达式，解释其中每个符号的物理意义，其中哪一部分是调制信号，哪一部分是载波信号？
1. 为什么ASK信号也叫OOK信号？OOK的英文全称是？
1. ASK产生方法有几种？分别画出它们的原理框图
1. 画出ASK信号的功率谱图形，其平均功率是多少？带宽是多少？频带利用率是多少？
1. ASK解调方法有几种？分别画出它们的原理框图
1. 如何分析ASK信号相干解调的误码性能？请画图说明
1. 如何分析ASK信号非相干解调的误码性能？请画图说明
1. ASK信号，相干解调和非相关解调，谁的误码率大？
1. 如何修改ASK调制解调系统，降低其带宽，提高其频带利用率？

## FSK

1. FSK产生方法有哪几种？分别画出它们的原理框图
1. 画出FSK信号的波形图。它和ASK信号有什么关系？
1. 写出FSK信号的时域表达式，解释其中每个符号的物理意义。根据此数学定义，FSK信号的相位一定是连续的吗？
1. 画出连续相位FSK信号的波形图。如何生成这种信号？
1. 什么是信号正交条件？为什么FSK信号的设计要求其满足该条件？该条件要求码率和载波频率满足什么关系？
1. 写出满足信号正交条件的FSK信号数学表达式
1. 什么叫频移指数？要满足信号正交条件，FSK信号的频移指数应满足什么性质？该指数通常取值多少？
1. FSK信号的带宽和频移指数有什么关系？
1. 画出FSK信号的功率谱图形，其平均功率是多少？带宽是多少？频带利用率是多少？
11. FSK解调方法有几种？分别画出它们的原理框图。请问其中每一路的BPF的带宽是多少？
11. 如何分析FSK信号相干解调的误码性能？请画图说明。考虑其中的噪声信号，如果要用n_0*B求该噪声信号功率，该B应该是FSK信号的总带宽，还是其解调时每一路的BPF带宽？为什么？
11. FSK相干解调是否需要判决电平？其误码率和发生0/1的先验概率是否有关？为什么会有这样的性质？请给出其数学证明
11. FSK信号带宽通常是几倍的R_B？为什么？

## PSK

1. 写出PSK信号的数学表达式，解释其中每个符号的物理意义
1. 写出PSK信号的时间表达式，解释其中每个符号的物理意义
1. 画出PSK信号的波形图。它和ASK信号有什么关系？它的相位一定是连续的吗？
1. PSK产生方法有几种？分别画出它们的原理框图
1. PSK信号是否符合信号正交条件？
1. 写出PSK信号的功率谱数学表达式，画出其功率谱图形，其平均功率是多少？带宽是多少？频带利用率是多少？
1. PSK解调方法有几种？画出它们的原理框图
1. 如何分析PSK信号相干解调的误码性能？请画图说明
1. PSK相干解调是否需要判决电平？其误码率和发生0/1的先验概率是否有关？0/1先验概率相同时，其阈值电平与信号电平A是否有关？为什么？请给出其数学证明
11. 什么是PSK信号相位选择的A方式和B方式？画出其波形

## DPSK

11. PSK相干解调，需要恢复同步载波，可以从其功率谱中提取离散载频分量吗？怎么办呢？
11. 简述两种PSK载波同步环的原理
11. ”相位模糊“是什么问题？为什么它叫”倒pi“现象？为什么Costas环会有相位模糊的问题？如何解决？
11. 写出DPSK信号的数学表达式，解释其中每个符号的物理意义
11. DPSK如何产生？画出原理框图
11. 画出载频是2倍R_B时，101100的DPSK信号的波形图
11. 画出载频是1.5倍R_B时，101100的DPSK信号的波形图
11. DPSK有几种解调方法？分别画出其原理框图和101100的DPSK信号的解调过程。此时会出现”相位模糊“问题吗？请分析
11. 画出载频是2倍R_B时，101100的DPSK信号的差分相干解调过程。其判决规则是？
21. 画出载频是1.5倍R_B时，101100的DPSK信号的差分相干解调过程。其判决规则是？
21. 如何分析DPSK信号相干解调的误码性能？请给出数学过程
21. 什么是绝对相移，什么是相对相移？

# 数字调制小结

21. 相同制式（如ASK）下，相干解调的误码率和相干解调的误码率，谁大？
21. 写出2ASK，2PSK，2FSK相干解调和非相干解调的误码率公式
21. 相干解调，相同信噪比下，2ASK，2PSK，2FSK的误码率，谁最大，谁最小，谁居中？为什么？
21. 相干解调，相同信噪比下，2PSK和2DPSK的误码率，谁大？为什么？
21. 什么是信号的信道敏感性？分别简述ASK，FSK，PSK，DPSK信号的信道敏感性特征

<br/>

|[Index](./) | [Previous](5-3-2-ary) | [Next](5-5-m-ary) |
