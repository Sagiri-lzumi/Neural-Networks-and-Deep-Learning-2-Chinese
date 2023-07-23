---
description: Perceptrons
---

# 视觉感知器

#### [Perceptrons](http://neuralnetworksanddeeplearning.com/chap1.html#perceptrons)

什么是神经网络？首先，我要解释一种名为Perceptron的人工神经元。Perceptron是科学家弗兰克-罗森布拉特（Frank Rosenblatt）在沃伦-麦库洛克（Warren McCulloch）和沃尔特-皮茨（Walter Pitts）早期研究的启发下，于20世纪50年代和60年代开发出来的。如今，使用其他人工神经元模型更为常见--在本书中，以及在许多现代神经网络研究中，使用的主要神经元模型是一种叫做西格码神经元（sigmoid neuron）的模型。我们很快就会讲到西格玛神经元。不过，要理解为什么要这样定义西格玛神经元，我们不妨先花点时间了解一下Perceptron。

那么，Perceptron是如何工作的呢？Perceptron接受多个二进制输入，并产生一个二进制输出：x1,x2,…

<figure><img src="../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

在所示的例子中，感知器有三个输入，x1、x2和x3。一般情况下，它可以有更多或更少的输入。Rosenblatt提出了一个简单的规则来计算输出。他引入了权重w1、w2等，这些是实数，表示相应输入对输出的重要性。神经元的输出，0或1，取决于加权和∑jwjxj是否小于或大于某个阈值。与权重一样，阈值是神经元的一个实数参数。更精确地用代数术语表示：
