---
title: 个人密码管理
category: personal knowledge management
---

密码管理，对于大部分人来说可能就是简单的所有账户都使用一个密码，这种做法的危险性不言而喻。为什么我们需要管理好自己的密码呢？

老牌密码明文存储先驱 CSDN，通讯录自动云存储「聚合数据」都证明了无节操国内公司遍地都是。加上你注册的大量论坛都是基于各种开源的程序搭建，站长或多或少没有及时更新补丁。一旦一个网站的密码泄露，黑客通过自动化的程序就可以把你所有用了一样密码的服务都找出来。

其次，设置简单的密码，黑客通过社会工程学可以很轻易的猜解到密码（如果你没什么名，可以无视这条）。例如「Machook 事件」的某位参与者的密码被轻易人肉出，再比如[「黑客是如何发现女朋友出轨的」](http://www.codeceo.com/article/hecker-girlfriend.html)这剧。

最后，如果公司的企业账户因为设置了简单的密码被猜解出后果更加严重。

那么如何设置安全的密码呢？我们先将密码的属主进行分类

- 个人密码
- 公司密码
- 亲人/好友密码

个人密码也可以再分，按照重要程度，使用场景

- 不重要的网站
- 涉及金钱或重要个人资料的网站（支付宝，Github 什么的）
- 需要经常输入密码的服务（Apple ID 什么的）

 比如我的分类如下：

![1Password Folder](/assets/images/1password-folder.png)

相应的密码生成策略应运而生：

- 公司密码使用 1Password 生成随机强密码
- 亲人/好友的密码用 1Password 记录，尊重他们的习惯
- 自己不重要的网站可以用一个统一的密码
- 自己重要的密码全部用 1Password 生成随机强密码
- 自己经常需要输入的密码可以用一定的策略生成容易记忆的强密码

如何生成容易记忆的强密码呢？

- 密码由数字+大小写字母+特殊字符组成
- 不同网站可以对应不同的密码

聪明的你一定会想到方法了，用一个固定的字符串加上网站的名称就可以让不同网站的密码不一样，我们这里将规则加强一些，得到下面的方法

- 密码第一部分由固定的字符串组成，切记不要用生日电话昵称之类的，这里我用 Maple888 作为例子
- 第二串包含特殊字符，我选了 @
- 第三串，使用网站英文名的第 2、4、6 三个字母，没有 6 个字母的网站用 0 补全

比如我在 Google 下的密码就是 Maple888@oge，包含了数字，大小写字母，特殊字符，而且不容易被猜到是 Google 的。

第三串的规则大家可以自己来生成规则，比如倒着的 1、3、5 个字母之类的，再比如第 2、4、6 个字母在键盘上面的字符等。

最后，隆重推荐 1Password 这个密码管理工具（支持 iOS/Mac/Windows/Android），以及建议不要使用 LastPass，原因如下：

- LastPass 多次爆出安全漏洞
- LastPass 出现过多次用户密码被全部清除
- LastPass 密码存储在 LastPass 的服务器上面，和 1Password 的存储在 Dropbox 上有很大区别，1Password 的 Dropbox 就算被攻破，但是只要主密码不被攻破密码就很安全

这里不打算介绍如何使用 1Password，仅仅分享下自己积累过的 1Password 使用技巧，送给看得懂有缘人

- [How to create, share a vault with family or coworkers](https://blog.agilebits.com/2013/11/13/1password-tip-how-to-create-share-a-vault-with-family-or-coworkers-mac/)
- [Quickly copy passwords from 1Password in iOS](http://thesweetsetup.com/quick-tip-quickly-copy-passwords-1password-ios/)
- [1Password with Launch Center Pro's lists and prompt fallback](http://philgr.com/blog/onepassword-with-launch-center-pro-list-and-prompt-fallback)
