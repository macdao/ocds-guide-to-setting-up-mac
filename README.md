# 强迫症的 Mac 设置指南

## 如何配置一个高效的 Mac 工作环境

[English Version](https://github.com/macdao/ocds-guide-to-setting-up-mac/blob/master/README.en.md)

本文的最初版本写于 2015 年，那时候我用的是一台 2013 款的 MacBook Pro，操作系统刚升级到 OS X El Capitan 10.11。

转眼到了 2019 年，我刚刚拿到 2019 款的 MacBook Pro，操作系统是 macOS Catalina 10.15。我特意没有从 Time Machine 恢复，而选择从头配置。当我按照本文配置时我发现，很多地方都变了。本次更新也由此而来。

想要怀旧的可以来这里：[2015 Version](https://github.com/macdao/ocds-guide-to-setting-up-mac/tree/2015)

## Table of Contents

1. [macOS](#1-macos)

   - [功能键](#功能键)
   - [全键盘控制](#全键盘控制)
   - [Spotlight 快捷键](#spotlight-快捷键)
   - [输入法快捷键](#输入法快捷键)
   - [其他快捷键](#其他快捷键)
   - [设置 Trackpad 轻点来点按](#设置-trackpad-轻点来点按)
   - [语音](#语音)
   - [词典](#词典)
   - [Dock Position](#dock-position)
   - [更改 Caps Lock 键为 Control 键](#更改-caps-lock-键为-control-键)
   - [Remove all Dock icons [OCD]](#remove-all-dock-icons-ocd)
   - [重置 Launchpad 上图标位置 [OCD]](#重置-launchpad-上图标位置-ocd)
   - [创建大小写敏感的工作区](#创建大小写敏感的工作区)
   - [Keychain Access](#keychain-access)
   - [三指拖动](#三指拖动)
   - [在 menu bar 上显示日期](#在-menu-bar-上显示日期)
   - [高效的光标](#高效的光标)

2. [常用工具](#2-常用工具)

   - [Homebrew](#homebrew)
   - [Homebrew Cask](#homebrew-cask)
   - [iTerm2](#iterm2)
   - [Oh My Zsh](#oh-my-zsh)
   - [Git 常用别名](#git-常用别名)
   - [Scroll Reverser](#scroll-reverser)
   - [ShiftIt](#shiftit)
   - [Sublime Text 3](#sublime-text-3)
   - [Visual Studio Code](#visual-studio-code)
   - [MacDown](#macdown)
   - [z](#z)
   - [Vimium](#vimium)
   - [LastPass](#lastpass)
   - [SourceTree](#sourcetree)
   - [CheatSheet](#cheatsheet)
   - [Alfred](#alfred)
   - [Stow](#stow)
   - [安装字体](#安装字体)

3. [开发工具](#3-开发工具)

   - [Java](#java)
   - [jEnv](#jenv)
   - [民间使用的 Java 版本切换方法](#民间使用的-java-版本切换方法)
   - [Java [OCD]](#java-ocd)
   - [IntelliJ IDEA](#intellij-idea)
   - [rbenv](#rbenv)
   - [Ruby 常用别名](#ruby-常用别名)
   - [Node 版本管理](#node-版本管理)

一直想写这么一篇文章，把我从同事那里学到的经验分享出来。市面上有很多类似的文章，写得都非常好，让我受益匪浅。不过我还是有一些自己总结出来的经验想要分享。

在工作中，我一般会在 1 到 10 人的团队中，经常会结对编程，即两个人共用一台 Mac 工作，因此也经常会把 Mac 外接一个大显示器、鼠标和键盘。我的常用开发平台有 Java、Ruby、Node.js、Web 等，使用 [JetBrains](https://www.jetbrains.com/) 的开发工具，比如 IntelliJ IDEA、RubyMine、WebStorm 等。

我深知自己的知识有限，所以写下本文以便和大家切磋交流。同时更有效率的方法和更好的工具也在不断涌现，我也贪心的希望把更好的方法和工具都收集更到到这里，我会不断更新本文，让它尽量不过时。最新内容请访问：<https://github.com/macdao/ocds-guide-to-setting-up-mac>。欢迎通过 GitHub 的`Issues`或者直接`Pull Requests`方式来分享你的经验。期待你的反馈。

我认为“一个高效的 Mac 工作环境”有以下几个特点：

- 自动化

  举个例子。手动安装一个应用，需要1)打开浏览器，2)搜索应用的名字，3)打开应用网站，4)寻找下载链接和安装方法，5)下载并等待下载完成，6)安装下载文件，7)可能还有后续的安装步骤。而自动化安装一个应用，只需要1)打开终端工具，2)敲入安装命令，3)等待完成这几个步骤。

  自动化可以大大简化操作，提高效率。

- 统一

  我经常结对编程，偶尔会遇到快捷键不一样，命令不同等问题。我强烈建议，至少在一个团队中，大家尽量使用相同的快捷键、命令等环境。（我记得有个实践就是这个，可是我一直没找到该实践的名字和出处，求告诉）

   同时，为了方便统一，我会优先考虑默认配置。只有当默认配置明显不如定制配置时，我才会采用定制配置。

- 够用

  够用就好，如果系统本身已经满足了我的需求，我不会再使用第三方工具。

- 效率

  效率，一切都是为了效率。

本文对于第三方应用如何安装和使用只有最简单的介绍，具体还请参考官方网站和相关文档。

有些章节标题标注了 [OCD]，意思是这些章节带有我强烈的个人色彩，如果你跟我臭味相投，欢迎借鉴，如果你并不认同，请忽略掉好了。

PS：虽然本文名为“强迫症”，但其实并不是[真正意义上的强迫症](https://zh.wikipedia.org/wiki/强迫症)，真正意义上的强迫症是一种会对患者的日常生活产生负面影响的疾病。

## 1. macOS

本节介绍操作系统本身的一些设置。

### 功能键

默认情况下，F1-F12 都是特殊功能，比如调节屏幕亮度。而当你需要键入 F1-F12 时（比如在使用 IntelliJ IDEA 的快捷键时），需要同时按住 Fn。这对于开发人员来说是非常不方便的。

把 F1-F12 改成标准功能键：选择`System Preferences` > `Keyboard`，在`Keyboard`标签页中选中`Use F1, F2, etc. keys as standard function keys`。

PS：在带 Touch Bar  的机型上，只能修改外接键盘的对应设定：在`Keyboard`标签页中选中`Use F1, F2, etc. keys as standard function keys on external keyboards`。

### 全键盘控制

当你在 Sublime Text 里关闭文件时，可能会遇到这样的对话框：

![dialog-box-without-all-controls](dialog-box-without-all-controls.png)

注意这个`Save`按钮跟其他两个按钮不太一样，它的底色是蓝的。这种按钮被称为默认按钮，除了用鼠标点击触发外，还可以通过回车键触发。

那么问题来了，如果你不想保存，想点击`Don't Save`，是不是只能用鼠标点击了呢？

并不是这样：选择`System Preferences` > `Keyboard`，在`Shortcuts`标签页中选择`Use keyboard navigation to move focus between controls`。之后这个对话框会变成这样：

![dialog-box-with-all-controls](dialog-box-with-all-controls.png)

这个`Don't Save`按钮有了一圈蓝边，这个意味着你可以通过空格键触发。不仅如此，你还可以用`Tab`键把蓝边转移到其他按钮，来实现全键盘控制。

除了`All controls`这个方法，你还可以用`⌘⌫`来选择`Don't Save`。`⌘⌫`的作用是在包含“删除”或“不存储”按钮的对话框中选择“删除”或“不存储”。

除了上述两个办法之外，居然还有个方法！就是按`⌘D`！据说是因为按`⌘+按钮的大写首字母`可以触发该按钮。可是！我按了`⌘C`和`⌘S`想取消和保存都没用！但是`⌘D`真的有用！如果仅仅是这也就算了，可是我又手贱试了下 TextEdit，在关闭未保存的文件时弹出的对话框上有三个按钮`Delete`、`Cancel`和`Save`。然而`⌘D`和`⌘C`都没用，但是！`⌘S`可以保存！我完全不能理解！我整个人几乎都是崩溃的，只好以咆哮体写下这段文字。如果谁能解释请务必告诉我，必有重谢！

`⌘C`不能用应该是因为它绑定到了复制功能；而`⌘D`不能用因为它的作用是从“打开”对话框或“存储”对话框中选择“桌面”文件夹。

在这个对话框上，你可以用`Esc`来执行`Cancel`操作。

### Spotlight 快捷键

Spotlight 的快捷键（不论是英文版还是中文版）都已经统一成了`⌘Space`，此处没有什么修改建议。

### 输入法快捷键

输入法我一直使用系统自带的拼音输入法。

由于 JetBrains 的 IDE，比如 IntelliJ IDEA、WebStorm 等都使用`⌃Space`作为自动完成这个最常用功能的快捷键。这和输入法切换的快捷键冲突了。我不建议更改 IDE 的快捷键，因此我建议更改输入法的快捷键。而由于 macOS 已经默认使用`Caps Lock`键来切换输入法，这个非常方便，所以我建议将`⌃Space`快捷键释放。

进入`System Preferences` > `Keyboard`，在`Shortcuts`标签页中选中`Input Sources`进行修改。

### 其他快捷键

让双手尽量多的键盘和快捷键，少使用鼠标和触摸板，可以大大提高效率。

- [Mac keyboard shortcuts](https://support.apple.com/kb/HT201236)

  苹果官方文档。当你在写代码，怎么通过快捷键让光标转移到行首、行尾、向上翻页或者将光标移左移一个词？都在这篇文档里。

- [Mac keyboard shortcuts for accessibility features](https://support.apple.com/kb/HT204434)

  苹果官方文档。回车触发蓝底按钮，空格触发蓝边按钮，都出自这里。

### 设置 Trackpad 轻点来点按

默认情况下按下触摸板才是点按（click）。我喜欢设置成用轻点作为点按：

选择`System Preferences` > `Trackpad`，在`Point & Click`标签页中选中`Tap to click`。

### 语音

macOS 自带了语音功能，可以用`say`命令让 Mac 开口说话：

```sh
say hello
```

可以和`&&`或者`;`配合使用来提示你某任务已经完成：

```sh
brew update && brew upgrade && brew cleanup ; say mission complete
```

通过命令行来听取发音还是有点麻烦。其实我们几乎可以在任何地方选中单词，然后使用快捷键`⌥+ESC`发音。仅仅需要这样设置一下：选择`System Preferences` > `Accessibility`， 选中左边的`Speech`，然后勾选`Speak selected text when the key is pressed`。

### 词典

macOS 自带了词典（Dictionary）。你几乎可以在任何应用中通过重按触摸板来现实对应单词的释义。如果你更喜欢三指轻拍触摸板，可以在`System Preferences` > `Trackpad`，在`Point & Click`标签页中把`Look up & data detectors`改成`Tap with three fingers`。

也可以打开 Dictionary 应用来查找单词。

可以在 Dictionary 应用中添加英汉汉英词典。

### Dock Position

默认 Dock 在屏幕下方。我们的屏幕一般都是 16:10，Dock 在屏幕下方的话会占据本来就不大的垂直空间。建议把 Dock 放到右边或者左边。

选择`System Preferences` > `Dock`，在`Position on screen:`中选择不同的位置。

### 更改 Caps Lock 键为 Control 键

我经常用到`Control`键，但这个键在键盘的左下角，很难按到。同时我发现我很少使用`Caps Lock`键，我一般会用`Shift`键加字母来输入大写字母，或者先输入小写再（通过快捷键）转换成大写。

基于以上原因，我把`Caps Lock`键的功能改成了`Control`键。很多同事也都这么做的，可能是受到 [HHKB](https://en.wikipedia.org/wiki/Happy_Hacking_Keyboard) 的影响。

设置方法：选择`System Preferences` > `Keyboard`，在`Keyboard`标签页中点击`Modifier Keys...`按钮，在弹出的窗口中，把`Caps Lock (⇪) Key:`对应的选项改成`⌃ Control`。

PS：由于现在`Caps Lock`用来切换输入法，所以如果要把`Caps Lock`键改成`Control`，那还需要设置输入法快捷键。我正在尝试习惯不更改`Caps Lock`。

### Remove all Dock icons [OCD]

本条目对于强迫症适用。

默认情况下 Dock 被一堆系统自带的应用占据着，而其中大部分我都很少使用，当我打开几个常用应用后，Dock 上会有很多图标，每个图标都会被挤得很小。所以我会把所有 Dock 上固定的图标都删掉，这样一来 Dock 上只有我打开的应用。

PS：Finder 图标是删不掉的。

除了一个一个删除图标，也可以通过这个命令来删除所有的固定图标：

```sh
defaults write com.apple.dock static-only -bool true; killall Dock
```

PS：Dock 上的`Downloads`也会被隐藏掉。

如何恢复（之前只改变`static-only`的方法已经不生效了）：

```sh
defaults delete com.apple.dock; killall Dock
```

PS：使用这个方法会让所有的 Dock 配置重置，包括 Dock Position。

### 重置 Launchpad 上图标位置 [OCD]

本条目对于强迫症适用。

新的应用被安装后，经常会跑到 Launchpad 的第一屏，所以它们的位置跟安装的顺序有关系，而我更希望它们可以按照某种更加稳定的顺序排列，比如按照系统默认的顺序：

```sh
defaults write com.apple.dock ResetLaunchPad -bool true; killall Dock
```

在默认顺序中，Launchpad 第一屏只有 Apple 自家应用。

### 创建大小写敏感的工作区

> unverified

在多人合作的项目开发时，因为 Mac 文件系统默认是大小写不敏感的，所以经常会出现一些诡异的问题。创建一个大小写敏感的工作区（workspace）来解决避免这些问题：

```sh
hdiutil create -type SPARSE -fs 'Case-sensitive Journaled HFS+' -size 100g -volname workspace ~/Documents/workspace.dmg.sparseimage
```

可以通过三种方式挂载镜像：

- 直接双击打开`~/Documents/workspace.dmg.sparseimage`
- `open ~/Documents/workspace.dmg.sparseimage`
- `hdiutil attach ~/Documents/workspace.dmg.sparseimage`

### Keychain Access

钥匙串访问（Keychain Access）是一个 macOS 应用程序，对我来说它最大的功能就是查看已经保存的各种账号和密码，包括 Wi-Fi 密码。

### 三指拖动

我习惯于三指拖动窗口。设置方法：选择`System Preferences` > `Accessibility`，选中左边`Pointer Control`菜单，打开`Trackpad Options…`，选中`Enable dragging`和`three finger drag`。

### 在 menu bar 上显示日期

我喜欢让菜单栏上显示日期，这样可以方便的看到当天的日期。设置方法：选择`System Preferences` > `Date & Time`，在`Clock`标签页选中`Show date`。

### 高效的光标

默认情况下，光标的闪烁速度和移动速度是相当慢的。当你需要用退格键删除大段文字的时候，会觉得痛不欲生，因为即使长按退格键，光标也移动的很缓慢。

调节光标移动速度：选择`System Preferences` > `Keyboard`，在`Keyboard`标签页中把`Key Repeat`以及`Delay Until Repeat`的滑块拉到最右端，从此享受飞一般的速度。

## 2. 常用工具

本节介绍一些常用的，跟开发没有直接关系的第三方应用及其设置。

### [Homebrew](http://brew.sh)

包管理工具，官方称之为`The missing package manager for macOS`。

安装步骤见官网。

有了 Homebrew 以后，要下载工具，比如 Wget、Gradle、Maven 等工具，就不需要去网上下载了，只要一行命令就能搞定：

```sh
brew install wget gradle maven
```

PS：安装 Homebrew 的时候会自动下载和安装 Apple 的 Command Line Tools。

执行`install`的时候经常会执行更新，有时候会比较慢，我们可以设置环境变量`HOMEBREW_NO_AUTO_UPDATE`关闭更新：

```sh
echo export HOMEBREW_NO_AUTO_UPDATE=1 >> ~/.zprofile
```

Homebrew 的替代品有 [MacPorts](https://www.macports.org/)，我没有用过。

#### 使用国内镜像安装 Homebrew

有时候在国内访问 GitHub 非常慢，导致安装 Homebrew 总是失败。我查阅了一些资料，可以使用国内镜像来安装 Homebrew。我这里给出一个方便的方法。

先看原理。官网上安装 Homebrew 的方法是执行命令：`/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`

在这个`install`脚本里，和 GitHub 有关的有两步：

- 通过 Git 获取`https://github.com/Homebrew/brew`
- 通过`brew update --force`来`Tap` `Homebrew/core`。

知道了之后，我们就可以直接修改下这个安装命令，将`https://github.com/Homebrew/brew`替换成国内镜像并暂时跳过`brew update --force`；然后使用镜像手动`Tap` `Homebrew/core`；最后执行`brew update --force`完成安装：

```sh
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install | sed 's#"https://github.com/Homebrew/brew"#"https://mirrors.ustc.edu.cn/brew.git"#' | sed '/system.*brew.*update/s/^/#/')" && \
brew tap homebrew/core https://mirrors.ustc.edu.cn/homebrew-core.git && \
brew update --force
```

PS：这是一句命令，不是三句。

> 本方法基于 <https://github.com/Homebrew/install/blob/c744a716f9845988d01e6e238eee7117b8c366c9/install>，如果`install`脚本更新有可能导致本方法失效。若发现失效请提交`issue`。

另外下载安装包也可以使用国内镜像，具体参考：<https://lug.ustc.edu.cn/wiki/mirrors/help/homebrew-bottles>

### [Homebrew Cask](https://github.com/Homebrew/homebrew-cask)

Homebrew Cask 允许你使用命令行安装 macOS 应用。比如你可以这样安装 Chrome：`brew cask install google-chrome`。还有 Evernote `evenote`、Sublime Text `sublime-text`、VirtualBox `virtualbox`、Docker `docker`、Firefox `firefox`、Visual Studio Code `visual-studio-code` 等都可以用 Homebrew Cask 安装。

Homebrew Cask 是社区驱动的，如果你发现 Homebrew Cask 上的应用不是最新版本，或者缺少你某个应用，你可以自己提交 pull request。

目前 Homebrew Cask 已经和 Homebrew 深度集成，不需要单独安装了。

应用也可以通过 App Store 安装，而且有些应用只能通过 App Store 安装，比如 Xcode 等一些 Apple 的应用。App Store 没有对应的命令行工具，并且还需要 Apple ID，相对有些麻烦。倒是更新起来很方便。

几乎所有常用的应用都可以通过 Homebrew Cask 安装，而且是从应用的官网上下载，所以你要安装新的应用时，建议用 Homebrew Cask 安装。如果你不知道应用在 Homebrew Cask 中的 ID，可以先用`brew search`命令搜索。

#### 使用国内镜像安装 Homebrew Cask

可以使用国内镜像安装 Homebrew Cask：

```sh
brew tap homebrew/cask https://mirrors.ustc.edu.cn/homebrew-cask.git
```

### [iTerm2](https://iterm2.com/)

iTerm2 是最常用的终端应用，是 Terminal 应用的替代品。提供了诸如`Split Panes`等[一群实用特性](https://iterm2.com/features.html)。它默认的黑色背景让我毫不犹豫的抛弃了 Terminal。

安装：

```sh
brew cask install iterm2
```

感谢 Homebrew Cask，我们可以通过命令行自动安装 iTerm2 了。

在终端里，除了可以用`⌃E`等快捷键（详见[其他快捷键](#其他快捷键)）之外，还可以使用`⌥B`、`⌥F`等快捷键（具体可以参考[这里](http://ss64.com/bash/syntax-keyboard.html)）。前提是这样设置一下：

选择`Iterm2`菜单 > `Preferences` > `Profiles`，选择你在使用的 Profile（默认是`Default`），在`Keys`标签页中把`Left option (⌥) key acts as`和`Right option (⌥) key acts as`都设置成`ESC+`。

在打开新的窗口/标签页的时候，默认情况下新窗口总是 HOME 目录，还需要我每次敲命令才能进入工作目录。如果想要这个新窗口在打开的时候就自动进入工作目录，需要如下设置：

选择`Iterm2`菜单 > `Preferences` > `Profiles`，选择你在使用的 Profile（默认是Default），在`General`标签页中的`Working Directory`部分中选择`Reuse previous seesion's directory`。

至此，Terminal 应用已经出色的完成了其历史使命。后面命令行就交给 iTerm2 啦。

在 iTerm2 中双击会自动选中对应的词，三击会选中对应的整行。选中的内容会自动进入剪贴板，不需要再按`⌘C`复制。

### [Oh My Zsh](http://ohmyz.sh)

默认的 Bash （Catalina 已经默认使用 Zsh）是黑白的，没有色彩。而 Oh My Zsh 可以带你进入彩色时代。Oh My Zsh 同时提供一套插件和工具，可以简化命令行操作。后面我们会看到很多介绍，你会看到我爱死这家伙了。

安装方法见官网。

目前我使用的插件有：`git z sublime history rbenv bundler rake`

Oh My Zsh 使用了 Z shell（Zsh），一个和 Bash 相似的 Shell，而非 Bash。

在 Zsh 中，`~/.zshrc`是最重要的配置文件。Oh My Zsh 在安装的时候会把当前环境的`$PATH`写入`~/.zshrc`中。这并不是我期望的行为，因为使用了 Homebrew，我们基本不再需要去定制`$PATH`，而 Oh My Zsh 提供的默认`$PATH`值`$HOME/bin:/usr/local/bin:$PATH`是非常合适的一个值，它把`$HOME/bin`加入了`$PATH`，可以让我们把自己用的脚本放到`$HOME/bin`下。

所以建议把`~/.zshrc`重置：

```sh
cp ~/.oh-my-zsh/templates/zshrc.zsh-template ~/.zshrc
```

> [2016年6月17号的一次提交](https://github.com/robbyrussell/oh-my-zsh/commit/551abfcbb48a0c001eadef80abc3276af4e9ad26)后，`zshrc.zsh-template`就不再修改`$PATH`了。如果需要，可以找到`# export PATH=$HOME/bin:/usr/local/bin:$PATH`这一行，把前面的`#`去掉。

Oh My Zsh 还有很多[有价值的插件](https://github.com/robbyrussell/oh-my-zsh/wiki/Plugins-Overview)。

替代品有基于 [fish shell](https://fishshell.com/) 的 [Oh My Fish](https://github.com/oh-my-fish/oh-my-fish)，基于 Bash 的 [Oh My Bash](https://github.com/ohmybash/oh-my-bash)。

### Git 常用别名

几乎每个人都会使用一些方法比如 Git 别名来提高效率，几乎所有人都会把使用`git st`来代替`git status`。然而这需要手动设置，每个人也都不完全一样。

Oh My Zsh 提供了一套系统别名（alias），来达到相同的功能。比如`gst`作为`git status`的别名。而且 Git 插件是 Oh My Zsh 默认启用的，相当于你使用了 Oh My Zsh，你就拥有了一套高效率的别名，而且还是全球通用的。是不是棒棒哒？下面是一些我常用的别名：

Alias | Command
----- | -------
gapa  | `git add --patch`
gc!   | `git commit -v --amend`
gcl   | `git clone --recurse-submodules`
gclean| `git clean -id`
gcm   | `git checkout master`
gcmsg | `git commit -m`
gco   | `git checkout`
gd    | `git diff`
gdca  | `git diff --cached`
glola | `git log --graph --pretty='%Cred%h%Creset -%C(auto)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --all`
gp    | `git push`
grbc  | `git rebase --continue`
gst   | `git status`
gup   | `git pull --rebase`
gwip  | `git add -A; git rm $(git ls-files --deleted) 2> /dev/null; git commit --no-verify --no-gpg-sign -m "--wip-- [skip ci]"`

完整列表请参考：<https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/git/>

### Scroll Reverser

> unverified

当你在浏览一个很长的网页时，你看完了当前显示的内容，想要看后续的内容，你可以在 Trackpad 上双指上滑，或者鼠标滚轮向上滚动。这是被称作“自然”的滚动方向。

然而在 Windows 里鼠标滚动的行为是相反的：鼠标滚轮向下滚动才会让浏览器显示后续的内容，向上滚动会达到页面的顶部。你可以在 macOS 的系统偏好设置里修改（选择`System Preferences` > `Trackpad`，在`Scroll & Zoom`标签页中不选中`Scroll direction: natural`），但是这样会同时改变鼠标滚轮的方向和 Trackpad 的方向。

要想只改变鼠标滚轮的方向，而保持 Trackpad 依旧是“自然”的，我们需要 Scroll Reverser：

```sh
brew cask install scroll-reverser
```

PS：这货会让三指点击失效

### ShiftIt

原生 macOS 下只能手动调整窗口大小，所以我们需要窗口管理工具。我用过很多窗口管理工具，可惜大部分工具都存在快捷键冲突的问题（对我来说主要是 IntelliJ IDEA）。ShiftIt 是少见的没有冲突的窗口管理工具：

```sh
brew cask install shiftit
```

替代者有 SizeUp，主要快捷键和 ShiftIt 相同。

当然如果喜欢 hacking，[Slate](https://github.com/jigish/slate)  是个不错的 hackable 的窗口管理工具。配置可以参照 <http://thume.ca/howto/2012/11/19/using-slate/>

### Sublime Text 3

安装：

```sh
brew cask install sublime-text
```

在命令行中指定使用 Sublime Text 打开某文件，是一个非常常用的功能，一般我们会按照 [OS X Command Line](https://www.sublimetext.com/docs/3/osx_command_line.html) 中所说执行 `ln -s "/Applications/Sublime Text.app/Contents/SharedSupport/bin/subl" ~/bin/subl` 来增加`subl`链接。但是如果你用 Homebrew Cask 安装的话，恭喜你，你不需要运行这个命令，因为 Homebrew Cask 自动帮你做了这件事情。而且你卸载 Sublime Text 的时候 Homebrew Cask 会自动删掉这个链接。

同时 Oh My Zsh 也提供了 Sublime Text 插件，叫做`sublime`。参考：<https://github.com/ohmyzsh/ohmyzsh/wiki/Plugins#sublime>，这个插件和通过 Homebrew Cask 安装的 Sublime Text 完美兼容。

替代品有 Atom、TextMate、Sublime Text 2 等，跟 Sublime Text 3 一样，用 Homebrew Cask 安装的话命令行工具会被自动加入`$PATH`。

### Visual Studio Code

我现在使用 Visual Studio Code 更多一些。Visual Studio Code 同样也有 Homebrew Cask 自动建立`code`链接，也有 Oh My Zsh 插件支持。

```sh
brew cask install visual-studio-code
```

### MacDown

MacDown 是 Markdown 编辑器。由于 Mou 一直不支持代码高亮，我就转向了 MacDown。完美支持 [GFM](https://help.github.com/articles/github-flavored-markdown/)。

我特别喜欢 [Markdown](https://daringfireball.net/projects/markdown/)，我用 Makdown 来写文章（包括本文），写幻灯片（[reveal.js](https://github.com/hakimel/reveal.js/)）。Markdown 可以让我专注于内容本身，而无需花精力在排版和样式上。

安装：

```sh
brew cask install macdown
```

Homebrew Cask 还会增加`macdown`命令，可以在命令行方便的使用 MacDown 打开文件。

### z

在打开终端后，你是怎么进入项目的工作目录？是`cd xxx`，`⌃R`还是用别名？

[z](https://github.com/rupa/z) 工具可以帮你快速进入目录。比如在我的 Mac 上运行`z cask`就会进入`/usr/local/Homebrew/Library/Taps/homebrew/homebrew-cask`目录。

这货的安装非常方便，甚至都不需要下载任何东西，因为它已经整合在了 Oh My Zsh 中。编辑`~/.zshrc`文件，在`plugins=(git)`这行中加上`z`变成`plugins=(git z)`，然后运行`source ~/.zshrc`重新加载配置文件，就可以使用 z 了。

替代品有 autojump。autojump 需要使用 Homebrew 安装。

### [Vimium](https://vimium.github.io/)

Vimium 是一个 Google Chrome 扩展，让你可以纯键盘操作 Chrome，把你的 Chrome 变成“黑客的浏览器”。

安装方法请参考官方网站。

其他浏览器也有类似的工具，比如 Firefox 的 Vimium-FF。

### [LastPass](https://lastpass.com)

> unverified

LastPass 是管理密码的工具，支持二次验证，提供所有浏览器插件以及 Mac 桌面版本。

最重要的是，它提供**命令行**的版本，可以直接通过 Homebrew 安装

```sh
brew install lastpass-cli --with-pinentry
```

之后，只需要命令：

```sh
lpass login you@email.com
```

就可以拷贝密码或者集成到其他命令中了：

```sh
lpass show --password gmail.com -c
```

### [SourceTree](https://www.sourcetreeapp.com/)

> unverified

SourceTree 是 Atlassian 公司出品的一款优秀的 Git 图形化客户端。如果你发现命令行无法满足你的要求，可以试试 SourceTree。

安装：

```sh
brew cask install sourcetree
```

用 Homebrew Cask 安装会自动增加命令行工具`stree`到`$PATH`里。在命令行中输入`stree`可以快速用 SourceTree 打开当前 Git 仓库。详细用法请参见`stree --help`。

### [CheatSheet](http://www.mediaatelier.com/CheatSheet/)

> unverified

CheatSheet 能够显示当前程序的快捷键列表，默认的快捷键是长按`⌘`。

![CheatSheet](http://www.mediaatelier.com/CheatSheet/imgs/main.png)

安装：

```sh
brew cask install cheatsheet
```

### [Alfred](https://www.alfredapp.com)

> unverified

Mac 用户不用鼠标键盘的必备神器，配合大量 Workflows，习惯之后可以大大减少操作时间。

上手简单，调教成本在后期自定义 Workflows，不过有大量雷锋使用者提供的现成扩展，访问[这里](http://www.alfredworkflow.com/)挑选喜欢的，并可以极其简单地根据自己的需要修改。

安装：

```sh
brew cask install alfred
```

### [Stow](http://www.gnu.org/software/stow/)

> unverified

GNU Stow 是管理符号链接（symlink）的一个小公举。主要用于 symlink 你的 [dotfiles](http://dotfiles.github.io/) 如 Emacs、Git、fish shell/Zsh 的配置文件。安装只需要

```
brew install stow
```

安装了 stow 之后，我们可以开始 symlink 一些 dotfiles 了。完整使用 stow 和 dotfiles 的流程可以参考 <https://github.com/jcouyang/dotfiles>

当你的 dotfiles 都妥妥的 symlink 到 `~/dotfiles` 后，push 到 GitHub 上就再也不怕换电脑了。

### 安装字体

我经常会使用一些开源字体，比如`Open Sans`。之前我会从网上寻找并下载字体，后来使用 [SkyFonts](https://www.monotype.com/products/skyfonts) 安装字体，直到我发现了 [homebrew-cask-fonts](https://github.com/Homebrew/homebrew-cask-fonts)：

```sh
brew tap homebrew/cask-fonts
brew cask install font-open-sans
```

## 3. 开发工具

### Java

macOS 都不会自带 JDK 了，所以进行 Java 开发的话，需要下载 JDK。在 Homebrew Cask 之前，我们需要从 <https://developer.apple.com/downloads/> 或者 Oracle 网站上下载。还有更麻烦的－－卸载 JDK 和升级 JDK。

JDK 安装文件是 pkg 格式，卸载和`.app`不一样，且没有自动卸载方式。

而 Homebrew Cask 提供了自动安装和卸载功能，能够自动从官网上下载并安装最新的 JDK。

```sh
brew cask install java
```

目前有`java`、`oracle-jdk`、`adoptopenjdk`可以安装 JDK 13，分别来自 OpenJDK、Oracle 和 AdoptOpenJDK。

如果你需要安装其他版本，可以使用 [homebrew-cask-versions](https://github.com/Homebrew/homebrew-cask-versions)：

```sh
brew tap homebrew/cask-versions
brew cask install java11
```

目前 homebrew-cask-versions 提供`java11`、`java6`和`adoptopenjdk8`。

在 macOS 上，你可以同时安装多个版本的 JDK。你可以通过命令`/usr/libexec/java_home -V`来查看安装了哪几个 JDK。

那问题来了，当你运行`java`或者 Java 程序时使用的是哪个 JDK 呢？在 macOS 下，`java`也就是`/usr/bin/java`在默认情况下指向的是已经安装的最新版本。但是你可以设置环境变量`JAVA_HOME`来更改其指向：

```sh
$ java -version
java version "1.8.0_60"
Java(TM) SE Runtime Environment (build 1.8.0_60-b27)
Java HotSpot(TM) 64-Bit Server VM (build 25.60-b23, mixed mode)
$ JAVA_HOME=/Library/Java/JavaVirtualMachines/1.6.0.jdk/Contents/Home java -version
java version "1.6.0_65"
Java(TM) SE Runtime Environment (build 1.6.0_65-b14-466.1-11M4716)
Java HotSpot(TM) 64-Bit Server VM (build 20.65-b04-466.1, mixed mode)
```

其中`JAVA_HOME=/Library/Java/JavaVirtualMachines/1.6.0.jdk/Contents/Home`可以用`` JAVA_HOME=`/usr/libexec/java_home -v 1.6` ``这种更加通用的方式代替。

需要 Oracle JDK 8/9？很遗憾，由于一些原因（[Java8 not working anymore](https://github.com/Homebrew/homebrew-cask-versions/issues/7253)），Homebrew Cask 不再提供 Oracle JDK 这些版本的安装。不过你可以尝试 [AdoptOpenJDK](https://github.com/AdoptOpenJDK/homebrew-openjdk)，或者从 [Oracle](https://www.oracle.com) 官网手工下载安装。

### [jEnv](https://github.com/gcuisinier/jenv)

> unverified

也可以使用 jEnv 来管理不同版本的 JDK，这个工具跟 [rbenv](#rbenv) 类似，通过当前目录下的`.java-version`来决定使用哪个 JDK。jEnv 也可以用 Homebrew 安装。不过要使用 jEnv 要有几个问题：

- 需要手动把`eval "$(jenv init -)"`加入 profile，没有 Oh My Zsh 插件。这点是我非常反感的。

  可以把`eval "$(jenv init -)"`加入`~/.zlogin`，这样可以避免修改`~/.zshrc`。
- 需要手动添加 JDK，不会自动采集系统 JDK。跟 Ruby 不同，macOS 已经提供`/usr/libexec/java_home`工具来管理安装的 JDK。
- 需要 `jenv rehash`。这个是跟 rbenv 学的。

所以我建议不要使用 jEnv。

### 民间使用的 Java 版本切换方法

添加以下脚本到当前 shell 配置文件中：`~/.zprofile`或者`~/.bash_profile`。

```sh
function setjdk() {
    export JAVA_HOME=`/usr/libexec/java_home -v $@`
}
```
这样我们就可以通过输入一条命令进行版本切换了：

```sh
setjdk 1.8
```

### Java [OCD]

作为一个强迫症患者，每当我看到 Java 的错误写法就想纠正过来。

当指编程语言时，Java 的正确写法是首字母大写，其余小写。其他写法比如`JAVA`、`java`都是不对的。

在其他一些地方会使用小写的`java`：

- `java`命令
- 原文件`Main.java`
- 包名`java.lang`

只有在全大写的标题里使用`JAVA`或者环境变量`JAVA_HOME`。

### IntelliJ IDEA

Java 开发必备工具 IntelliJ IDEA。可以安装 Ultimate Edition：

```sh
brew cask install intellij-idea
```

也可以安装开源免费的 Community Edition：

```sh
brew cask install intellij-idea-ce
```

IntelliJ IDEA 有几套内建的快捷键方案（Keymap）。其中适用于 macOS 的有`macOS`和`IntelliJ IDEA Classic`两种。区别是:

- `macOS`更加符合 macOS 常用的快捷键
- `IntelliJ IDEA Classic`方案和其他平台上的快捷键类似

一个团队使用不同的快捷键会影响效率。可以用`View | Quick Switch Scheme`（`⌃ Back Quote`）快速切换 Keymap。

因为我经常会在 macOS 和 Windows 平台上使用 IDEA，所以我一般使用`IntelliJ IDEA Classic`方案。

可以从 IDEA 的`Help > Keymap Reference`打开快捷键的参考手册。不过从这里打开的是`macOS`方案的，而`IntelliJ IDEA Classic`方案的可以从这里找到：<http://android.cs.uchicago.edu/content/slides/keymap_mac.pdf>。

IntelliJ IDEA 自带了 [Fira Code](https://github.com/tonsky/FiraCode) 字体，支持字体连笔（font ligatures）。使用 Fira Code 可以让我们在不同平台使用相同的编辑器字体，设置方法：`Intellij IDEA` > `Preference...`，在左边选择`Editor` > `Font`，在右边选择`Font:` - `Fira Code Retina`，然后选中`Enable font ligatures`。

### [rbenv](https://github.com/sstephenson/rbenv)

> unverified

人人都需要一个 Ruby 版本管理工具。rbenv 就是这样一个轻量级工具，它可以通过 Homebrew 安装。

安装：

```sh
brew install rbenv ruby-build
```

然后在`~/.zshrc`中加上`rbenv`插件。否则你需要手动添加`eval "$(rbenv init -)"`到`~/zshrc`或者`~/.zprofile`文件里。

有时候项目会依赖一些奇怪的版本号，比如`ruby-2.1.0`，这个时候你需要 [rbenv-aliases](https://github.com/tpope/rbenv-aliases) 帮忙：

```sh
brew install rbenv-aliases
```

替代品有 RVM、chruby。因为 RVM 不能通过 Homebrew 安装，并且安装的时候会没有节操的修改一堆文件，所以被我早早的弃用了。chruby 也是一个轻量级工具，而且可以完美的和 Oh My Zsh 集成在一起，我看到有些生产环境在用它。

### Ruby 常用别名

> unverified

几乎所有 Ruby 开发人员都会把`bi`作为`bundle install`的别名。Oh My Zsh 提供`builder`插件，这个插件提供了一套别名，比如`bi`、`be`。同时还能让你在运行一些常用 gem 的时候直接输入`rspec`，不需要`be rspec`这样了。具体包括哪些命令请参考[这里](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/bundler)。

Zsh 对于`[`和`]`符号有特殊的处理，所以在运行`rake task[parameter]`的时候会报错，你需要改成`rake task\[parameter\]`或者`noglob rake task[parameter]`。然而 Oh My Zsh 已经看穿这一切，自带的 rake 插件已经解决了这个问题：`brake task[parameter]`。

添加插件的时候注意把`rake`放到`bundler`后面，例如这样：

```
plugins=(git z sublime history rbenv bundler rake)
```

### Node 版本管理

> unverified

Node 的版本管理工具有很多，常用的会有以下几个：

* [nodenv](https://github.com/nodenv/nodenv)

  该工具是一个类似 rbenv 的工具，命令和其完全一样，安装和配置也一样。

  ```
  brew install nodenv
  ```

  你需要手动添加以下配置到`~/.zshrc`或者`~/.zprofile`文件里。

  ```sh
  export PATH="$HOME/.nodenv/bin:$PATH"
  eval "$(nodenv init -)"
  ```

* [nvm](https://github.com/creationix/nvm)

  该工具是一个类似 RVM 的工具，命令安装方式也基本一样，可以参考官方文档。

* [n](https://github.com/tj/n)

  一个简单的工具，安装方式类似 nvm，无需额外配置。具体参考官方文档。

目前根据 GitHub Stars，这三个管理工具的排名依次是 nvm、n、nodenv。但是个人建议采用 nodenv，原因同 rbenv，尤其已经在使用 rbenv 的伙伴们会觉得 nodenv 更顺手 :smile: 。

## 参考资料

- [Hacker's Guide to Setting up Your Mac](https://github.com/lapwinglabs/blog/blob/master/hacker-guide-to-setting-up-your-mac.md)
- [Setting up a new (OS X) development machine](https://mattstauffer.co/blog/setting-up-a-new-os-x-development-machine-part-1-core-files-and-custom-shell)
- [高效 MacBook 工作环境配置](http://www.xialeizhou.com/?p=71)（已失效）
- [程序员如何优雅地使用 Mac？](http://www.zhihu.com/question/20873070)
- [装点你的 Dock：外观篇](http://sspai.com/33493)
- [6 Dock Terminal tweaks Mac users need](https://www.computerworld.com/article/3040996/6-dock-terminal-tweaks-mac-users-need.html)
