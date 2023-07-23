---
description: Using neural nets to recognize handwritten digits
---

# 使用神经网络识别手写数字

人类的视觉系统是世界上的奇迹之一。考虑一下下面这一串手写的数字。

<figure><img src="../../.gitbook/assets/image.png" alt="" width="312"><figcaption></figcaption></figure>

大多数人不费吹灰之力就能认出这些数字是 504192。这种轻松是具有欺骗性的。在我们大脑的每个半球，人类都有一个初级视觉皮层，也称为 V1，包含 1.4 亿个神经元，它们之间有数百亿个连接。然而，人类的视觉不仅包括 V1，还包括一整套视觉皮层--V2、V3、V4 和 V5--进行逐渐复杂的图像处理。我们的大脑中装有一台超级计算机，经过数亿年的进化调整，已经非常适合理解视觉世界。识别手写数字并不容易。相反，我们人类在理解眼睛所显示的内容方面有着惊人的能力。但几乎所有这些工作都是在无意识的情况下完成的。因此，我们通常并不了解我们的视觉系统能解决多么棘手的问题。

如果你尝试编写一个计算机程序来识别像上面这样的数字，视觉模式识别的难度就显而易见了。我们自己做起来似乎很容易的事情，突然变得异常困难。关于我们如何识别形状的简单直觉--"9 的顶部有一个环，右下方有一个垂直的笔画"--用算法来表达却并不那么简单。当你试图使这些规则精确化时，你很快就会迷失在例外、注意事项和特殊情况的泥沼中。这似乎毫无希望。

神经网络以不同的方式解决这一问题。其思路是获取大量手写数字，即训练实例；

<figure><img src="../../.gitbook/assets/image (1).png" alt=""><figcaption><p>numbers</p></figcaption></figure>

然后开发一个能够从这些训练实例中学习的系统。换句话说，神经网络利用这些示例自动推断出识别手写数字的规则。此外，通过增加训练示例的数量，神经网络可以学习到更多关于笔迹的知识，从而提高准确率。因此，虽然我在上文只展示了 100 个训练数字，但也许我们可以通过使用数千、数百万甚至数十亿个训练示例来构建更好的手写识别器。

在本章中，我们将编写一个实现神经网络的计算机程序，学习识别手写数字。程序只有 74 行，没有使用特殊的神经网络库。但是，这个简短的程序却能在没有人工干预的情况下识别出准确率超过 96% 的数字。此外，在后面的章节中，我们还将提出一些想法，将准确率提高到 99% 以上。事实上，最好的商业神经网络现在已经非常出色，银行用它们来处理支票，邮局用它们来识别地址。

我们之所以专注于手写识别，是因为它是学习一般神经网络一个很好地例子。作为一个例子和原型，它恰到好处：它极具挑战性，但识别手写数字并非易事，但又不至于需要极其复杂的解决方案或巨大的计算能力。此外，它还是开发深度学习等更先进技术的绝佳途径。因此，我们将在本书中反复讨论手写识别问题。在本书后半部分，我们将讨论如何将这些想法应用于计算机视觉中的其他问题，以及语音、自然语言处理和其他领域。

当然，如果本章的重点只是编写一个识别手写数字的计算机程序，那么本章就会短得多！不过，在学习的过程中，我们会了解到许多关于神经网络的重要思想，包括两种重要的人工神经元（感知器和sigmoid神经元），以及神经网络的标准学习算法，即随机梯度下降算法。在整个过程中，我将重点解释为什么要这样做，以及如何建立你的神经网络直觉。这需要比我仅仅介绍基本机制更长的讨论时间，但为了让你获得更深刻的理解，这样做是值得的。本章结束时，我们将能够理解什么是深度学习，以及它为何重要。


