---
description: Perceptrons
---

# 感知器

#### [Perceptrons](http://neuralnetworksanddeeplearning.com/chap1.html#perceptrons)

什么是神经网络？首先，我要解释一种名为Perceptron的人工神经元。Perceptron是科学家弗兰克-罗森布拉特（Frank Rosenblatt）在沃伦-麦库洛克（Warren McCulloch）和沃尔特-皮茨（Walter Pitts）早期研究的启发下，于20世纪50年代和60年代开发出来的。如今，使用其他人工神经元模型更为常见--在本书中，以及在许多现代神经网络研究中，使用的主要神经元模型是一种叫做西格码神经元（sigmoid neuron）的模型。我们很快就会讲到西格玛神经元。不过，要理解为什么要这样定义西格玛神经元，我们不妨先花点时间了解一下Perceptron。

那么，Perceptron是如何工作的呢？Perceptron接受多个二进制输入，并产生一个二进制输出：x1,x2,…

<figure><img src="../../.gitbook/assets/image (3) (1).png" alt=""><figcaption></figcaption></figure>

在所示的例子中，感知器有三个输入，x1、x2和x3。一般情况下，它可以有更多或更少的输入。Rosenblatt提出了一个简单的规则来计算输出。他引入了权重w1、w2等，这些是实数，表示相应输入对输出的重要性。神经元的输出，0或1，取决于加权和：

$$
\sum_j w_j x_j
$$

是否小于或大于某个阈值。与权重一样，阈值是神经元的一个实数参数。更精确地用代数术语表示：

<figure><img src="../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

这就是感知器工作的全部内容！

这是基本的数学模型。你可以将感知器视为一种通过加权证据来做出决策的设备。让我举个例子。虽然这不是一个非常现实的例子，但很容易理解，而且我们很快就会讨论更加现实的例子。假设即将到来的周末，你听说你所在城市将举行一个奶酪节。你喜欢奶酪，现在正在考虑是否要去参加这个节日。你可以通过权衡以下三个因素来做决定：

1. 天气是否好？&#x20;
2. 你的男朋友或女朋友是否愿意陪伴你？&#x20;
3. 奶酪节是否靠近公共交通？（你没有车）。

我们可以用相应的二进制变量x1、x2和x3来表示这三个因素。例如，如果天气好，我们令x1=1；如果天气不好，令x1=0。类似地，如果你的男朋友或女朋友想要一起去，我们令x2=1；如果不想去，令x2=0。对于x3和公共交通，也是类似的表示方式。

现在，假设你非常喜欢奶酪，以至于即使你的男朋友或女朋友对此不感兴趣，而且奶酪节的交通不便，你仍然很愿意去参加。但或许你真的很讨厌坏天气，如果天气不好，你绝对不会去参加奶酪节。你可以使用感知器来模拟这种决策过程。一种方法是为天气选择权重w1=6，而对于其他条件选择w2=2和w3=2。w1的较大值表示天气对你非常重要，比你的伴侣是否与你一起去，或者公共交通是否靠近更重要。最后，假设你为感知器选择了阈值5。有了这些选择，感知器实现了所需的决策模型，当天气好时输出1，当天气不好时输出0。无论你的男朋友或女朋友是否想去，或者公共交通是否靠近，对输出结果都没有影响。

通过调整权重和阈值，我们可以得到不同的决策模型。例如，假设我们选择了阈值为3。那么感知器会在天气好的时候或者在奶酪节靠近公共交通并且你的男朋友或女朋友愿意参加的情况下决定让你去参加奶酪节。换句话说，这将是一个不同的决策模型。降低阈值意味着你更愿意去参加奶酪节。

显然，感知器并不是人类决策的完整模型！但是这个例子说明了感知器如何通过权衡不同类型的证据来做出决策。而且，复杂的感知器网络应该能够做出相当微妙的决策：

<figure><img src="../../.gitbook/assets/image (8) (1).png" alt=""><figcaption></figcaption></figure>

在这个网络中，第一列感知器 - 我们称之为第一层感知器，通过加权输入证据来做出三个非常简单的决策。那么第二层感知器呢？每个第二层感知器都是通过权衡第一层决策结果来做出决策的。通过这种方式，第二层中的感知器可以在比第一层感知器更复杂和更抽象的层次上做出决策。而第三层的感知器甚至可以做出更复杂的决策。通过这种方式，一个多层感知器网络可以进行复杂的决策。

顺便提一下，在我定义感知器时，我说感知器只有一个输出。在上面的网络中，感知器看起来好像有多个输出。实际上，它们仍然只有一个输出。多个输出箭头只是一种有用的方式，用来表示感知器的输出被用作多个其他感知器的输入。这比绘制一个输出线然后再分裂要方便得多。

让我们简化描述感知器的方式。条件：

$$
\sum_j
w_j x_j > \mbox{threshold}
$$

实际上有些繁琐，我们可以进行两个符号上的改变来简化它。第一个改变是将：

$$
\sum_j w_j x_j
$$

写成点积形式，如下所示：

$$
w \cdot x \equiv \sum_j w_j x_j
$$

其中 w 和 x 分别是权重和输入的向量，它们的分量分别对应着感知器的权重和输入值。第二个改变是将阈值移动到不等式的另一边，并用所谓的感知器偏置来代替阈值如：

$$
b \equiv
-\mbox{threshold}
$$

使用偏置代替阈值，感知器的规则可以被重新写成：

<figure><img src="../../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

你可以将偏置视为使感知器输出1的容易程度。或者用更生物学的术语来说，偏置是衡量感知器发射动作的容易程度。对于具有非常大偏置的感知器来说，输出1是非常容易的。但是如果偏置非常负值，那么感知器输出1就很困难。显然，引入偏置只是对我们描述感知器的一个小改变，但是后面我们会看到它导致了进一步的符号简化。因此，在本书的其余部分，我们将不再使用阈值，而始终使用偏置。

我已经描述过感知器是一种用于加权证据以做出决策的方法。感知器的另一种用途是计算通常被认为是基础计算的基本逻辑函数，例如`AND、OR`和`NAND`等函数。举个例子，假设我们有一个有两个输入的感知器，每个输入的权重为-2，整体偏置为3。下面是我们的感知器图示：

<figure><img src="../../.gitbook/assets/image (5) (1).png" alt=""><figcaption></figcaption></figure>

然后我们可以看到，输入00产生输出1，因为`(−2)∗0+(−2)∗0+3=3`是正数。在这里，我引入了∗符号来明确表示乘法。类似的计算显示，输入01和10产生输出1。但是输入11产生输出0，因为`(−2)∗1+(−2)∗1+3=−1`是负数。因此，我们的感知器实现了一个NAND门！

NAND门的例子表明我们可以使用感知器来计算简单的逻辑函数。实际上，我们可以使用感知器网络来计算任何逻辑函数。原因是NAND门是通用计算的，也就是说，我们可以用NAND门来构建任何计算。例如，我们可以使用NAND门来构建一个将两个位x1和x2相加的电路。这需要计算按位求和x1⊕x2，以及当x1和x2都为1时设置为1的进位位，即进位位只是按位乘积x1 \* x2：

<figure><img src="../../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

为了得到等效的感知器网络，我们将所有的NAND门替换为具有两个输入的感知器，每个输入的权重为-2，整体偏置为3。以下是得到的网络。请注意，我稍微移动了与底部右侧NAND门对应的感知器，只是为了更容易在图表上画箭头：

<figure><img src="../../.gitbook/assets/image (11) (1).png" alt=""><figcaption></figcaption></figure>

这个感知器网络的一个显著特点是，最左边的感知器的输出被用作底部最后一个感知器的输入两次。当我定义感知器模型时，并没有说明是否允许这种重复输出到同一个地方的情况。实际上，这并不重要。如果我们不想允许这种情况，那么可以简单地将这两条线合并成一个单一的连接，权重为-4，而不是两个带有-2权重的连接。（如果你觉得这不明显，你可以停下来自己证明它是等效的。）通过这样的改变，网络看起来如下所示，所有未标记的权重均为-2，所有的偏置都为3，而标记为-4的是一个单一的权重：

<figure><img src="../../.gitbook/assets/image (10) (1).png" alt=""><figcaption></figcaption></figure>

到目前为止，我一直在将输入x1和x2绘制为漂浮在感知器网络左侧的变量。实际上，习惯上绘制一个额外的感知器层 - 输入层 - 来表示输入：

<figure><img src="../../.gitbook/assets/image (1) (2).png" alt=""><figcaption></figcaption></figure>

这种用于输入感知器的符号表示中，我们有一个输出，但没有输入，

<figure><img src="../../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

这种对于输入感知器的符号表示实际上是一种简写。它并不意味着一个没有输入的感知器。要理解这一点，假设我们确实有一个没有输入的感知器。那么加权和:

$$
\sum_j w_j x_j
$$

将始终为零，因此感知器会在b>0时输出1，在b≤0时输出0。也就是说，感知器将简单地输出一个固定值，而不是所需的值（在上面的例子中是x1）。更好的做法是将输入感知器看作根本不是感知器，而是特殊的单元，其定义是输出所需的值x1，x2等等。

这个加法器的例子展示了感知器网络如何用来模拟包含多个NAND门的电路。由于NAND门是通用计算的，因此感知器也是通用计算的。

感知器的计算普适性既令人放心又让人失望。令人放心的是，它告诉我们感知器网络可以与任何其他计算设备一样强大。但同时也令人失望，因为它似乎只是新型的NAND门。这并不是什么大新闻！

然而，情况比这种观点所暗示的要好。事实证明，我们可以设计出能够自动调整人工神经元网络的权重和偏置的学习算法。这种调整是对外部刺激的响应，在没有程序员直接干预的情况下发生。这些学习算法使我们能够以与传统逻辑门截然不同的方式使用人工神经元。我们的神经网络可以简单地学习解决问题，有时这些问题在直接设计传统电路会非常困难。

