---
title: "为什么你应该用 Editor 而不是 IDE"
category: tech
---

曾经的我也是一名IDE funs，为了给他添加上各种强大的功能尝试了各种插件。直到有一天，我听说IDE这些功能用神奇的emacs加上插件都可以更简单的实现，想一探究竟的我从此开始了emacs之旅，直到现在一发不可收拾，连常用的操作系统也换成了unix。

作为一个VS/emacs/vim各有1年用龄的用户，简单的总结下他们的区别和使用感受，当然我这里的IDE指的是非苹果的IDE。

Editor v.s. IDE
===============

IDE慢
----
IDE能做到启动比emacs慢，恩 :P

IDE天天变
---------
M$的IDE就和他的技术名词(MFC/COM/.NET/WinRT)以及操作系统(98/xp/7/8)一样天天变，对于用户和开发者都极其不友好，对比下M$的IDE(vc/vs2005/vs2008/vs2010/vs2012)的UI就知道从vc到最新的vs发生了多大变化。反观Apple的产品，系统的UI从10.1-10.7居然没有多少变化([Apple 谈论产品 vs Microsoft 谈论技术](http://chinese.catchen.me/2010/02/apple-vs-microsoft.html))。

同样，editor除了版本号的更新，其他的都不会改变了([Command Line and User Friendliness](http://www.terminally-incoherent.com/blog/2012/05/30/command-line-and-user-friendliness/))。总有人认为每次都有更新的产品才是好产品，才是好系统，真正的情况往往相反，经过了时间考验的才是优秀的，这也能说明为什么国内的程序员为什么都不知道IRC/Mailing List。

IDE难看
-------
![vim](/assets/images/vim.jpg)

IDE没有复用性
------------
IDE一般都和一个语言进行了绑定，你想使用新的语言就要熟悉新IDE和他一系列的新功能（快捷键，调试工具等），太麻烦了。但是editor却不同，你只需要安装新的syntax和indent的文件就可以漂亮的支持新的语言了。
当然这个也不是绝对的，现在很多IDE已经可以支持其他语言，比如eclipse和Xcode。

IDE没有插件机制
--------------
IDE提供给你的功能都是已经集成好了的，你想换个，没门！或者你需要折腾很久，但是editor却可以简单随意的添加删除你需要的插件来实现想要的任何功能。前几天emacs给我的一个惊喜就是emacs+minimap插件居然可以实现sublime text的缩略图功能!

![emacs-minimap](http://randomsample.de/minimap1.jpg)

简单的说，IDE中编辑器和他提供的功能是紧耦合的，editor和插件却是松耦合，所以editor才可以如此自由和灵活。

IDE没有学习成本
--------------
良好的编程习惯需要头脑，当别人给你帮助的时候，你就失去了提高的机会。

很典型的例子就是我身边的同学到了大二大三都依然解决不了链接过不了的问题。为什么？因为IDE什么都帮你做了，于是你什么也学不会。你知道代码补全/代码模板/代码格式化/代码折叠/类视图/定义跳转/代码重构/调试的实现原理吗？如果你用的是windows，你一定不知道。

任何东西，第一眼看上去方便好用的不代表效率高，第一眼看上去不好用的也不不代表效率低。现实生活中常常如此，一样东西经历了一定的学习时间后才可以很高效的使用([推迟满足感](http://www.lixiaolai.com/archives/426.html))。

IDE没有快乐
-----------
用vim的时候，我用tagbar插件的时候知道了原来函数列表都是ctags工具实现的，他还可以帮忙实现函数跳转；用gdb的时候知道了原来调试是通过编译时生成的调试信息实现的；用makefile时知道了一个大项目是怎么由小程序组成的；用ack时知道了原来修改别人的代码可以这么简单。

IDE有debugger
------------
用logger吧（[Coders at Work （二）](http://wangcong.org/blog/archives/949)）。A debugger is the mother of all evil(excerpted from stackoverflow):

* you're wasting your time because all that time put into debugging can never be reused. It's a one time hack in the sense that if you have another bug later, you'll probably need to start all over again, and
* you've only solved this one bug, and while it might only occur for this specific scenario that you tested, you most likely did not solve a more general problem. That's because you're not thinking in generality, you're in a debugging mindset, not a general mindset.

IDE的哲学是恶心的
---------------
IDE就是一坨又大又恶心的东西的集合。真正该做的是永远「写」小东西，「组合」大东西(《Linux/Unix设计思想》)

这里推荐一下王垠的[『完全用 GNU/Linux 工作』](http://shaohui.ycool.com/post.21909.html)，里面也有关于ide的论述。

利用小工具动手组合强大的IDE(vim)
===============================
IDE中我们需要的功能有啥？

* 编辑 - 重点
* 编译 - 终端里面进行或者交给插件
* 调试 - 交给logger吧

剩下的就参考我的vim配置文件吧，在`readme.md`中有详细的文档:
[Maple's vim configiration files](https://github.com/humiaozuzu/dot-vimrc)
