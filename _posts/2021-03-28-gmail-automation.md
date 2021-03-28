---
title: 使用 Filter + Google Script 全自动处理 Gmail 邮件
category: personal productivity system
---

一直以来自己邮件处理花了很多时间，所以自己就开始研究如何基于 Gmail 做自动化。我目前处理的流程是：

1. Inbox 的*几乎所有*邮件都自动打上分类的 Label （使用 Gmail Filter）
2. - 95% 邮件使用 Google Script 自动按天数 Archive
   - 剩下的需要回复或者阅读的，执行后手动 Archive
3. Inbox Zero _(:з」∠)_

## 邮件分类技巧

首先需要看一下自己收到的邮件都是哪些类型的，比如可以按工作，生活，学习等来区分。比如我自己的分类结构是这样：

```
├── shortcut
│   ├── finance
│   ├── vps
│   ├── tech
│   ├── life
│   └── rss
└── archive
    ├── licence
    ├── Company-a
    └── Company-b
```

具体是
- finance: 各种券商，银行，虚拟货币服务商的邮件
- vps: 各种 VPS 服务商的邮件
- tech: 技术相关服务的邮件，类似 Github/GitLab/Cloudflare/Trello 之类的，还有监控服务的邮件
- life: 生活中的各种邮件，因为在日本各种生活服务都是发邮件，所以有这个分类，在国内会很少
- rss: 订阅的各种阅读类的邮件都在这里，比如各种 xxx weekly

另外我还有一个 archive 分组，我会存
- licence: 软件的 Licence 的都丢这里
- 其他历史就职公司的邮件和之前 shortcut 中的分类但是现在已经不关注了，都可以丢这个分类下

这里具体分类需要结合自身实际情况。当你确定了自己的分类后，就可以在 Gmail 中添加 Label 和创建 Filter 了([传送门](https://support.google.com/a/users/answer/9308833))。如果还是不会创建 Label 和 Filter，请自行 Google。这里会说一些实用的 Filter 技巧。

1. 用 `|` 匹配多个发件人，例如 `noreply@a.net|noreply@b.com`
2. 用 `*` 匹配一个域名下的多个用户名，例如 `*@a.net|*@b.com`，我会默认把部分分类用户名都替换成 `*` 因为有一些不靠谱的服务商经常改发件人用户名。
3. 用 `|` 匹配多个关键词，例如 subject 下输入 `日結單|日结单|estatement` 就可以帮我把标题中含有下面任意关键字的邮件筛选出来
4. 如果你有一些分类的邮件非常重要（比如Finance分类），可以在 Filter 里面选上「Never send it to Spam」
5. 有一些服务商很烂没有取消订阅功能，可以给他们创建一个 Filter，然后选上「Skip the Inbox (Archive it)」，就不会受到邮件打扰了。当然你也可以选择 「Delete it」直接删除

更多系统的技巧，可以自行搜索「Gmail Filter Tricks」。当然默认的 Filter 还是远远不够的，我还需要更多功能，比如
- 对我来说，所有有 Label 的邮件我都不需要额外的处理了，我都看过推送通知了，请帮我过 n 天后自动 Archive（Gmail Filter 只能立刻 Archive 所以不够用），即使是 RSS 这个分类，我也希望一周内帮我自动 archive 掉，因为没读就是没时间，没必要看了，不然堆积了毫无意义。
- 把那些讨厌的 Terms & Conditions 更新邮件给我自动 archive 掉，我对你的条款更新毫无兴趣。这个用 Gmail Filter 可以实现简单的筛选，但是很可能误杀，如果想做更复杂一点的匹配，会麻烦而且维护困难。

这里就需要 Google Script 来帮忙完成，需要一些编程基础，下面以按天数自动 archive 为例，给一下我的代码

## 邮件按天数自动 Archive

请参考这个[教程](https://medium.com/@fw3d/auto-archive-emails-in-gmail-after-2-days-1ebf0e076b1c)，创建 Script，贴入下面的代码，按需更改，然后设置定时执行。

我对于不重要的分类是 1 天就帮我 archive 掉，稍微重要的 2 天，阅读的留一周。如果你觉得某个分类很重要，想要只 archive 已读的邮件，也可以修改下面的代码实现。官方的文档可以[参考这里](https://developers.google.com/apps-script/reference/gmail)，比如检查是否已读的 API [在这里](https://developers.google.com/apps-script/reference/gmail/gmail-thread#isUnread())。


```javascript
function gmailAutoarchive() {
  archive_by_label("shortcut/life", 1);
  archive_by_label("shortcut/vps", 1);
  archive_by_label("shortcut/tech", 2);
  archive_by_label("shortcut/finance", 2);
  archive_by_label("shortcut/rss", 7);
}

function archive_by_label(label, delayDays) {
  var maxDate = new Date();
  maxDate.setDate(maxDate.getDate()-delayDays);

  Logger.log('Handling ' + label);
  var threads = GmailApp.search("in:inbox label:"+ label ).filter(function(thread) {
    // Only include threads older than the limit we set in delayDays
    return (thread.getLastMessageDate() < maxDate);
  });

  var batch_size = 100;
  while (threads.length) {
    var this_batch_size = Math.min(threads.length, batch_size);
    var this_batch = threads.splice(0, this_batch_size);
    GmailApp.moveThreadsToArchive(this_batch);
  }
}
```

希望大家在做懒人的路上越走越远！
