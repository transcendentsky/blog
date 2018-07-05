---
title: 【Python】Multiprocess and Subprocess and threading 
tags: programme
---
### Multiprocess and Subprocess
The `subprocess` module lets you run and control other programs. Anything you can start with the command line on the computer, can be run and controlled with this module. Use this to integrate external programs into your Python code.

The `multiprocessing` module lets you divide tasks written in python over multiple processes to help improve performance. It provides an API very similar to the` threading` module; it provides methods to share data across the processes it creates, and makes the task of managing multiple processes to run Python code (much) easier. In other words, `multiprocessing` lets you take advantage of multiple processes to get your tasks done faster by executing code in parallel.

### Mlutiprocess and threading
[摘自 莫烦python]
这次我们来看看为什么说 python 的多线程 threading 有时候并不是特别理想. 最主要的原因是就是, Python 的设计上, 有一个必要的环节, 就是 Global Interpreter Lock (GIL). 这个东西让 Python 还是一次性只能处理一个东西.

我从这里摘抄了一段对于 GIL 的解释.

尽管Python完全支持多线程编程， 但是解释器的C语言实现部分在完全并行执行时并不是线程安全的。 实际上，解释器被一个全局解释器锁保护着，它确保任何时候都只有一个Python线程执行。 GIL最大的问题就是Python的多线程程序并不能利用多核CPU的优势 （比如一个使用了多个线程的计算密集型程序只会在一个单CPU上面运行）。

在讨论普通的GIL之前，有一点要强调的是GIL只会影响到那些严重依赖CPU的程序（比如计算型的）。 如果你的程序大部分只会涉及到I/O，比如网络交互，那么使用多线程就很合适， 因为它们大部分时间都在等待。实际上，你完全可以放心的创建几千个Python线程， 现代操作系统运行这么多线程没有任何压力，没啥可担心的。

线程间通信
问题
你的程序中有多个线程，你需要在这些线程之间安全地交换信息或数据

解决方案
从一个线程向另一个线程发送数据最安全的方式可能就是使用 queue 库中的队列了。创建一个被多个线程共享的 Queue 对象，这些线程通过使用 put() 和 get() 操作来向队列中添加或者删除元素。