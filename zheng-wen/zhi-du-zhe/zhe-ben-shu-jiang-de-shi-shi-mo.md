---
description: What this book is about
---

# 这本书讲的是什么？

神经网络是有史以来发明的最美丽的编程范例之一。在传统的编程方法中，我们告诉计算机要做什么，将大问题分解成许多计算机可以轻松执行的精确定义的小任务。相比之下，在神经网络中，我们不会告诉计算机如何解决我们的问题。相反，它从观测数据中学习，找出自己对当前问题的解决方案。

从数据中自动学习听起来很有前途。然而直到2006年，我们才知道如何训练神经网络来超越更为传统的方法，除了几个特殊的问题。2006年发生的变化是在所谓的深度神经网络中学习的技术。这些技术现在被称为深度学习，它们得到了进一步的发展，今天深度神经网络和深度学习在计算机视觉、语音识别和自然语言处理的许多重要问题上都取得了突出的表现。谷歌、微软和Facebook等公司正在大规模部署和使用它们。

这本书的目的是帮助你掌握神经网络的核心概念，包括深度学习的现代技术。读完这本书后，您将编写使用神经网络和深度学习来解决复杂模式识别问题的代码。你将有一个使用神经网络和深度学习来解决你自己设计的问题的基础。

### 以原则为导向的问题

这本书背后的一个信念是：最好对神经网络和深度学习的核心原理有一个扎实的理解，而不是对其的模糊理解。如果你已经很好地理解了核心思想，你就可以迅速理解其他新的材料。在编程语言术语中，可以将其视为掌握一门新语言的核心语法、库和数据结构。您可能仍然只“了解”整个语言的一小部分--许多语言都有庞大的标准库--但新的库和数据结构可以快速、轻松地被理解。

这意味着，这本书显然不是一本关于如何使用某个特定神经网络库的教程。如果你最想在图书馆里学习，那就别读这本书！找到您想要学习的库，并阅读教程和文档。但请注意。虽然这会立即带来解决问题的回报，但如果你想了解神经网络的真实情况，如果你想要几年后仍然相关的见解，那么仅仅学习一些热门的机器学习的书是不够的。你需要了解神经网络是如何工作的、并且对神经网络工作原理有很深刻的理解。技术在不断的升级，但对技术的深刻见解是难以磨灭的。

### 亲身实践的方法

我们将通过解决一个具体问题来学习神经网络和深度学习背后的核心原理：教计算机识别手写数字的问题。我们使用传统的编程方法很难解决这个问题。然而，正如我所见，使用一个简单的神经网络就可以很好地解决这个问题，只需几十行代码，而且不需要特殊的库。更重要的是，我们将通过多次迭代来改进程序，逐步纳入越来越多关于神经网络和深度学习的核心思想。

这种实践方式意味着您需要一些编程经验才能读懂本书。但是你不需要成为一名十分专业的程序员。我已经用Python2.7版编写了代码，即使您不会用Python语言编程，只要稍加努力就应该很容易理解本书的代码。通过这本书的课程，我们将开发一个小型神经网络库，您可以使用它来进行实验和建立您对神经网络的理解。所有的代码都可以在这里下载。当您读完了这本书，您就可以轻松地拿走一个功能更齐全的神经网络库用于生产中。

与此相关的是，阅读这本书的数学要求并不高。虽然在大多数章节中都有一些数学，但通常只是初等代数和函数的曲线图，我希望大多数读者都不介意，我偶尔会使用更高级的数学，但是我对我所使用的材料进行了系统的编写，这样即使有些数学细节让你摸不着头脑，你也能跟上本书的进度。使用较多使用数学的一个章节是第二章，它需要一点多变量微积分和线性代数。如果你对这些都不熟悉，我将在第二章讨论如何驾驭数学的这些相关知识。如果你觉得这仍然很难，你可以简单地跳到这一章的主要结果的摘要。其实无论如何，在学习的一开始就没有必要担心这一点，功到自然成。

本书既以原则性为导向，又以实践为目标，这是很罕见的。但是我相信，如果我们能够建立起神经网络的基本概念，你会学得如鱼得水。我们将编写鲜活的代码，而不仅仅是学习抽象的理论，你可以探索和扩展这些代码。这样，你就会从理论和实践上更深刻的理解这些基础知识，并为进一步增加你的知识储备做好准备。