---
title: "如何备份与分享 dotfiles"
category: tech
---

Linux用久了，自然就积累了很多符合自己习惯配置文件，比如vim/emacs的，bash/zsh的等等，我一直想用一个比较不错的方法对他们进行管理（真实情况是我每次备份文件的时候总会忘记那么几个，重装系统后就丢失了。。。），总的来说有如下需求：

1. 多台电脑间同步方便
2. 让同类的配置文件能在一起
3. 方便的分享自己的配置文件给其他人

同步
----

我的使用的工具历史有点像vcs的发展历史，一开始的时候用的是一个移动硬盘装这些配置文件，每次一个电脑的东西更新了我还要先同步到移动硬盘，然后同步到其他的电脑。这样实在是太麻烦了，于是我开始换用云同步的工具——dropbox，换用他后效率明显提高了，然后慢慢地在使用的过程中获得了一些不错的解决方案。

我将配置文件的文件夹命名为`dotfiles`，原因是配置文件很多都是以点开头的，然后将这个文件夹放在dropbox的目录里面即可，云端同步达成。

归类
----

最简单的归类方法就是使用文件夹了，如果有`.vimrc`不在`.vim`文件夹的这种情况使用软链即可。建议把dropbox中配置文件名开头的点去掉，一是终端中方便补全，二是在你换成Mac时也不会蛋疼（用了就知道了:P）

以vim为例，我使用的如下的方法，这里显示的是vim的插件目录和vim的配置文件，去掉了点，然后`.vimrc`文件也放到了vim目录中保存以免污染全局。

```
vim           <---- ~/.vim软链指向vim
├── .git
├── .gitignore
├── .gitmodules
├── README.md
├── autoload
├── bundle
├── colors
└── vimrc     <---- ~/.vimrc软链指向vimrc
```

比如我的dotfiles目录是按照下面的方法归类的：

```
dotfiles
├── bin
├── config
├── install.sh
├── oh-my-zsh
└── vim
```

bin里面是常用的一些脚本，自己或其他人写的，在源里面没有的，记得将它加进`PATH`变量。

config是一些较为小型的配置文件（比如`.gemrc`, `.gitconfig`等）

oh-my-zsh是一个管理zsh配置文件的框架，里面的大小写不敏感补全，部分补全，自动补全的提示都比bash强大，用后可以大大提高效率。

vim在前面已经说了，install.sh是帮你自动建立软链接的脚本，在新电脑中可以快速的建立好编程需要的环境。然后看下我是如何组织这个安装脚本的：

``` bash
#!/bin/bash
# 将dotfiles文件夹链接到home目录下，以后编辑配置文件会方便很多
ln -s ~/Dropbox/unix/dotfiles ~/dotfiles

# for vim
ln -s ~/dotfiles/vim ~/.vim
ln -s ~/dotfiles/vim/vimrc ~/.vimrc

# for oh-my-zsh
ln -s ~/dotfiles/oh-my-zsh/zshrc ~/.zshrc

# for config files
ln -s ~/dotfiles/config/gemrc ~/.gemrc
ln -s ~/dotfiles/config/gitconfig ~/.gitconfig
ln -s ~/dotfiles/config/ssh ~/.ssh
```

分享
----

自己有了很好的配置文件后就一定想与他人分享了，直接同步到github即可。

但是你可能会担心一些隐私问题，比如你alise了一些远程主机或者ssh的连接之类的，这些放在你私人的dropbox中是没问题的，但是在github中别人就可以获得你vps的ip并尝试去破解你的密码或做其他坏事。

这时候`gitignore`文件就可以起作用啦，直接添加你的隐私文件的路径就可以了，有更多需求可以去`man gitignore`。

PS: Github搜集了不少经典的[dotfiles](http://dotfiles.github.com/)，赶快去看看吧:-)

