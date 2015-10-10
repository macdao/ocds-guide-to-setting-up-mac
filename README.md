# 强迫症的 Mac 设置指南

## 如何配置一个高效的 Mac 工作环境

使用合适的工具，可以大大提高效率。总结了一些工具和方法，可以提高效率。

- 自动化

- 统一

现在有了很多虚拟化工具可以方便的让软件运行环境相同，不过对于IDE等一些工具还是无法被虚拟化。
我和很多人结对编程过，经常会遇到问题，比如快捷键不一样，命令不同等

- 效率

够用，如果系统本身已经满足了我的需求，我不会再使用第三方工具。

一般的章节，有些章节有[OCD]字样，如果不能被稳定重现，我就认为是不安全的。

我把这篇文章放到GitHub上，

虽然本文名为“强迫症”，但其实并不是[真正意义上的强迫症](https://zh.wikipedia.org/wiki/强迫症)，真正意义上的强迫症是一种会对患者的日常生活产生负面影响的疾病。

## 1. OS X

### 功能键

默认情况下，F1-F12 都是特殊功能，比如调节屏幕亮度。而当你需要键入 F1-F12 时（比如在使用 IntelliJ IDEA 的快捷键时），需要同时按住 Fn。这对于开发人员来说是非常不方便的。

把 F1-F12 改成标准功能键：选择`System Preferences` > `Keyboard`，在`Keyboard`标签页中选中`Use all F1, F2, etc. keys as standard function keys`。

### 全键盘控制

当你在 Sublime Text 里关闭文件时，可能会遇到这样的对话框：

![dialog-box-without-all-controls](dialog-box-without-all-controls.png)

注意这个`Save`按钮跟其他两个按钮不太一样，它的底色是蓝的。像这种按钮，除了用鼠标点击触发外，还可以通过回车键触发。

那么问题来了，如果你不想保存，想点击`Don't Save`，是不是只能用鼠标点击了呢？

并不是这样：选择`System Preferences` > `Keyboard`，在`Shortcuts`标签页中选择`All controls`；或者使用快捷键`⌃F7`。之后这个对话框会变成这样：

![dialog-box-with-all-controls](dialog-box-with-all-controls.png)

这个`Don't Save`按钮有了一圈蓝边，这个意味着你可以通过空格键触发。不仅如此，你还可以用`Tab`键把蓝边转移到其他按钮，来实现全键盘控制。

### Spotlight快捷键

一般来说 Spotlight 的快捷键是`⌃Space`。这个快捷键有一些问题：

- 对于没有添加中文输入法的 Mac 来说，Spotlight 的快捷键是`⌘Space`。英语国家的人都是这样的，所以如果你跟老外结对可能会遇到问题。
- JetBrains 的 IDE，比如 IntelliJ IDEA、WebStorm 等都使用`⌃Space`作为自动完成这个最常用功能的快捷键。

所以建议把 Spotlight 的快捷键设置为`⌘Space`，可以避免上述两个问题。

### 输入法快捷键

一般来说切换输入法的快捷键是`⌘Space`。由于我建议把 Spotlight 的快捷键设置为`⌘Space`，所以我建议把切换输入法的快捷键设置为`⌥Space`。

### 其他快捷键

- [Mac keyboard shortcts](https://support.apple.com/kb/HT201236)

  苹果官方文档。当你在写代码，怎么通过快捷键让光标转移到行首、行尾、向上翻页或者将光标移左移一个词？都在这片文档里。
  
- [Mac keyboard shortcuts for accessibility features](https://support.apple.com/kb/HT204434)

  苹果官方文档。回车触发蓝底按钮，空格触发蓝边按钮，都出自这里。

### 设置 Trackpad 轻拍以点击

默认情况下按下触摸板才是点击。我喜欢设置成用轻拍作为点击：

选择`System Preferences` > `Trackpad`，在`Point & Click`标签页中选中`Tap to click`。

### Say

OS X 自带了朗读功能，可以用`say`命令让Mac开口说话：

```sh
say hello
```

可以和`&&`或者`;`配合使用来提示你某任务已经完成：

```sh
brew update && brew upgrade && brew cleanup ; say done
```

通过命令行来听取发音还是有点麻烦。其实我们几乎可以在任何地方选中单词，然后使用快捷键`⌥+ESC`发音。仅仅需要这样设置一下：选择`System Preferences` > `Dictation & Speech`，在`Text to Speech`标签页中选中`Speak selected text when the key is pressed`。

### 词典

OS X 自带了词典。你几乎可以在任何应用中通过三指轻拍触摸板来现实对应单词的释义。

也可以打开 Dictionary 应用来查找单词。

可以在 Dictionary 应用中添加英汉汉英词典。

### Dock Position

默认 Dock 在屏幕下方。我们的屏幕一般都是16:10，Dock 在屏幕下方的话会占据本来就不大的垂直空间。建议把 Dock 放到左边或者右边。

### Remove all Dock icons[OCD]

本条目对于强迫症适用。

默认情况下 Dock 被一堆系统自带的 App 占据着，而其中大部分我都很少使用，当我打开几个常用 App 后，Dock 上会有很多图标，每个图标都会被挤得很小。所以我会把所有 Dock 上固定的图标都删掉，这样一来 Dock 上只有我打开的应用。

PS：Finder 图标是删不掉的。

### 重置 Launchpad 上图标位置[OCD]

本条目对于强迫症适用。

新的 App 被安装后，经常会跑到 Launchpad 的第一屏，所以它们的位置跟安装的顺序有关系，而我更希望它们可以按照某种更加稳定的顺序排列，比如按照系统默认的顺序：

```sh
defaults write com.apple.dock ResetLaunchPad -bool true; killall Dock
```

在默认顺序中，Launchpad 第一屏只有 Apple 自家 App。

## 2. 常用工具

常用的，跟开发没有直接关系的第三方应用。

### [Homebrew](http://brew.sh)

包管理工具，官方称之为`The missing package manager for OS X`。

安装：

```sh
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

有了 brew 以后，要下载工具，比如 MySQL、Gradle、Maven、Node.js 等工具，就不需要去网上下载了，只要一行命令就能搞定：

```sh
brew install mysql gradle maven node
```

PS：安装 brew 的时候会自动下载和安装 Apple 的 Command Line Tools。

brew 的替代品有 [MacPorts](https://www.macports.org/)，现在基本没人用它。

### [Homebrew Cask](http://caskroom.io)

brew-cask 允许你使用命令行安装 OS X 应用。比如你可以这样安装 Chrome：`brew cask install google-chrome`。还有 Evernote、Skype、Sublime Text、VirtualBox等都可以用 brew-cask 安装。

brew-cask 是社区驱动的，如果你发现 brew-cask 上的应用不是最新版本，或者缺少你某个应用，你可以自己提交 pull request。

安装：

```sh
brew install caskroom/cask/brew-cask
```

应用也可以通过 App Store 安装，而且有些应用只能通过 App Store 安装，比如 Xcode 等一些 Apple 的应用。但是不能通过命令行安装，还需要 Apple ID，倒是更新起来很方便。

几乎所有常用的应用都可以通过 brew-cask 安装，所以你要安装新的应用时，建议用 brew-cask 安装。如果你不知道应用在 brew-cask 中的 ID，可以先用`brew cask search`命令搜索。

### [iTerm2](https://www.iterm2.com/)

iTerm2 是最常用的终端应用。

安装：

```sh
brew cask install iterm2
```

感谢 brew-cask，我们可以通过命令行自动安装 iTerm2 了。

在终端里，除了可以用`⌃E`等快捷键（详见[其他快捷键](#其他快捷键)）之外，还可以使用`⌥B`、`⌥F`等快捷键（具体可以参考[这里](http://ss64.com/bash/syntax-keyboard.html)）。前提是这样设置一下：

选择`Iterm`菜单 > `Preferences` > `Profiles`，选择你在使用的 Profile（默认是Default），在`Keys`标签页中把`Left option (⌥) key acts as`和`Right option (⌥) key acts as`都设置成`+ESC`。

在打开新的窗口/标签页的时候，默认情况下新窗口总是 HOME 目录，还需要我每次敲命令才能进入工作目录。如果想要这个新窗口在打开的时候就自动进入工作目录，需要如下设置：

选择`Iterm`菜单 > `Preferences` > `Profiles`，选择你在使用的 Profile（默认是Default），在`General`标签页中的`Working Directory`部分中选择`Reuse previous seesion's directory`。

### [Oh My ZSH](http://ohmyz.sh)

默认的 bash 是黑白的，没有色彩。而 Oh My Zsh 可以让你的 Shell 变得漂亮。Oh My Zsh 同时提供一套插件和工具，可以简化命令行操作。后面我们会看到很多，你会看到我爱死这家伙了。

安装：

```sh
sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

目前我使用的插件有：git z sublime history rbenv bundler rake

Oh My Zsh 使用了 Z shell（zsh），一个和 bash 相似的shell，而非 bash。

在 Z shell 中，`~/.zshrc`是最重要的配置文件。Oh My Zsh 在安装的时候会把当前环境的`$PATH`写入`~/.zshrc`中。这并不是我期望的行为，因为使用了 brew，我们不再需要去定制`$PATH`。而文件`~/.oh-my-zsh/templates/zshrc.zsh-template`，也就是`~/.zshrc`的模版，其默认的`$PATH`值是`$HOME/bin:/usr/local/bin:$PATH`，它把`$HOME/bin`加入了`$PATH`，可以让我们把自己用的脚本放到`$HOME/bin`下。

所以建议把`~/.zshrc`重置：

```sh
cp ~/.oh-my-zsh/templates/zshrc.zsh-template ~/.zshrc
```

替代品有 [Oh My Fish](https://github.com/oh-my-fish/oh-my-fish)，使用了 [Fishshell](http://fishshell.com/) 作为基础。

### Git

几乎每个人都会使用一些方法比如 alias 来提高效率，几乎所有人都会把使用`git st`来代替`git status`。然而这需要手动设置，每个人也都不完全一样。

Oh My Zsh 提供了一套 alias，来达到相同的功能。比如`gst`作为`git status`的别名。而且 Git 插件是 Oh My Zsh 默认启用的，相当于你使用了 Oh My Zsh，你就拥有了一套高效率的别名，而且还是全球通用的。是不是很棒啊？下面是一些 Oh My Zsh 提供的别名：

Alias | Command
----- | -------
gapa  | `git add --patch`
gc!   | `git commit -v --amend`
gcl   | `git clone --recursive`
gclean| `git reset --hard && git clean -dfx`
gcm   | `git checkout master`
gcmsg | `git commit -m`
gco   | `git checkout`
gd    | `git diff`
gdca  | `git diff --cached`
glola | `git log --graph --pretty = format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit --all`
gp    | `git push`
grbc  | `git rebase --continue`
gst   | `git status`
gup   | `git pull --rebase`
gwip  | `git add -A; git rm $(git ls-files --deleted) 2> /dev/null; git commit -m "--wip--"`


完整列表请参考：<https://github.com/robbyrussell/oh-my-zsh/wiki/Plugin:git>


### Scroll Reverser

默认情况下，在 Trackpad 上双指下滑，以及鼠标滚轮向下滚动，都会让网页向下滚动。这是被称作“自然”的滚动方向。我习惯于这样的 Trackpad，但是不习惯这样的鼠标，这和 Windows 下相反。而 OS X 下鼠标和 Trackpad 的滚动方向是同一个设置，要改变鼠标的滚动方向必须同时改变 Trackpad 的。为了让鼠标滚轮和 Windows 下表现一致，我们需要 Scroll Reverser：

```sh
brew cask install scroll-reverser
```

PS：这货会让三指点击失效

### ShiftIt

原生 OS X 下只能手动调整窗口大小，所以我们需要窗口管理工具。我用过很多窗口管理工具，可惜大部分工具都存在快捷键冲突的问题（貌似主要是 IntelliJ IDEA）。ShiftIt 是少见的没有冲突的应用：

```sh
brew cask install shiftit
```

PS：之前的版本需要安装 X11，最新版本已经修正了这个问题。

替代者有 SizeUp，主要快捷键和 ShiftIt 相同。

### Sublime Text 2

安装：

```sh
brew cask install sublime-text
```

在命令后中指定使用 Sublime Text 打开某文件，是一个非常常用的功能，一般我们会按照 [OS X Command Line](https://www.sublimetext.com/docs/2/osx_command_line.html) 中所说执行 `ln -s "/Applications/Sublime Text 2.app/Contents/SharedSupport/bin/subl" ~/bin/subl` 来增加`subl`命令。但是如果你用 brew-cask 安装的话，恭喜你，你不需要运行这个命令，因为 brew-cask 自动帮你做了这件事情。而且你卸载 Sublime Text 的时候 brew-cask 会自动删掉这个链接。

同时 Oh My Zsh 也提供了 Sublime Text 插件，叫做`sublime`。参考：<https://github.com/robbyrussell/oh-my-zsh/tree/master/plugins/sublime>，这个插件和通过 brew-cask 安装的 Sublime Text 完美兼容。

替代品有 TextMate，Sublime Text 3等。

### MacDown

MacDown 是 Markdown 编辑器。自从 Mou 不再开发后，我就转向了 MacDown。完美支持 [GFM](https://help.github.com/articles/github-flavored-markdown/)。

我特别喜欢 [Markdown](https://daringfireball.net/projects/markdown/)，我用 Makdown 来写文章（包括这篇文章），写幻灯片（[reveal.js](https://github.com/hakimel/reveal.js/)）。

安装：

```sh
brew cask install macdown
```

### z

在打开终端后，你是怎么进入项目的工作目录？是`cd`，`⌃R`还是用别名？

[z](https://github.com/rupa/z) 工具可以帮你快速进入目录。比如在我的 Mac 上运行`z cask`就会进入`/usr/local/Library/Taps/caskroom/homebrew-cask/Casks`目录。

这货的安装非常方便，甚至都不需要下载任何东西，因为它已经整合在了 Oh My Zsh 中。编辑`~/.zshrc`文件，在`plugins=(git)`这行中加上`z`变成`plugins=(git z)`，然后运行`source ~/.zshrc`就可以使用 z 了。

替代品有 autojump，autojump 需要使用 brew 安装。

## 3. 开发工具

### Java

现在 OS X 都不会自带 JDK 了，所以进行 Java 开发的话，需要下载 JDK。在 brew-cask 之前，我们需要从 <https://developer.apple.com/downloads/> 或者 Oracle 网站上下载。还有更麻烦的－－卸载 JDK 和升级 JDK。

JDK 安装文件是 pkg 格式，卸载和 .app 不一样，且没有自动卸载方式。

而 brew-cask 提供了自动安装和卸载功能，能够自动从官网上下载并安装 JDK 8。

```sh
brew cask install java
```

如果你需要安装 JDK 7 或者 JDK 6，可以使用`homebrew-cask-versions`：

```sh
brew tap caskroom/versions
brew cask install java6
```

在 OS X 上，你可以同时安装多个版本的 JDK。你可以通过命令`/usr/libexec/java_home -V`来查看安装了哪几个 JDK。

那问题来了，当你运行`java`或者 Java 程序时使用的是哪个 JDK 呢？在 OS X 下，`java`也就是`/usr/bin/java`在默认情况下指向的是已经安装的最新版本。但是你可以设置环境变量`JAVA_HOME`来更改其指向。

```sh
$ java -version
java version "1.8.0_60"
Java(TM) SE Runtime Environment (build 1.8.0_60-b27)
Java HotSpot(TM) 64-Bit Server VM (build 25.60-b23, mixed mode)
$ JAVA_HOME=/System/Library/Java/JavaVirtualMachines/1.6.0.jdk/Contents/Home java -version
java version "1.6.0_65"
Java(TM) SE Runtime Environment (build 1.6.0_65-b14-466.1-11M4716)
Java HotSpot(TM) 64-Bit Server VM (build 20.65-b04-466.1, mixed mode)
```

### IntelliJ IDEA

Java 开发必备工具 IntelliJ IDEA。可以安装 Ultimate Edition：

```sh
brew cask install intellij-idea
```

也可以安装开源免费的 Community Edition：

```sh
brew cask install intellij-idea-ce
```

IntelliJ IDEA 有几套内建的快捷键方案（Keymap）。其中适用于 OS X 的有`Mac OS X`和`Mac OS X 10.5+`两种。区别是:

- `Mac OS X`方案和其他OS上的快捷键类似，
- 而`Mac OS X 10.5+`更加符合 OS X 常用的快捷键。

一个团队使用不同的快捷键严重影响效率。可以用`View | Quick Switch Scheme`（`⌃ Back Quote`）快速切换 Keymap。

如果可以选择的话，我建议使用`Mac OS X`方案。因为在客户现场，客户很可能使用的是 Windows，默认的快捷键和`Mac OS X`方案类似，重构时，你可以直接告诉客户用什么快捷键，而不需要再去查询一遍。

### [rbenv](https://github.com/sstephenson/rbenv)

人人都需要一个 Ruby 版本管理工具。rbenv 就是这样一个轻量级工具，它可以通过 brew 安装。

安装：

```sh
brew install rbenv ruby-build
```

有时候项目会依赖一些奇怪的版本号，比如`ruby-2.1.0`，这个时候你需要 [rbenv-aliases](https://github.com/tpope/rbenv-aliases) 帮你：

```sh
brew install rbenv-aliases
```

替代品 RVM、chruby。因为 RVM 不能通过 brew 安装，并且安装的时候会没有节操的修改一堆文件，所以被我早早的弃用了。chruby也是一个轻量级工具，可以完美的和 Oh My Zsh 集成在一起，我看到有些生产环境在用它。

### `bi`

几乎所有 Ruby 开发人员都会把`bi`作为`bundle install`的别名。Oh My Zsh 提供`builder`插件，这个插件提供了一套别名，比如`bi`、`be`。同时还能让你在运行一些常用 gem 的时候直接输入`rspec`，不需要`be rspec`这样了。具体包括哪些命令请参考[这里](https://github.com/robbyrussell/oh-my-zsh/tree/master/plugins/bundler)。

Z shell 对于`[`和`]`符号有特殊的处理，所以在运行`rake task[parameter]`的时候会报错，你需要改成`rake task\[parameter\]`或者`noglob rake task[parameter]`。然而 Oh My Zsh 已经看穿这一切，自带的 rake 插件已经解决了这个问题：`brake task[parameter]`。

添加插件的时候注意把`rake`放到`bundler`后面，例如这样：

```
plugins=(git z sublime history rbenv bundler rake)
```

## 参考资料

- [Hacker's Guide to Setting up Your Mac](http://lapwinglabs.com/blog/hacker-guide-to-setting-up-your-mac)
- [Setting up a new (OS X) development machine](https://mattstauffer.co/blog/setting-up-a-new-os-x-development-machine-part-1-core-files-and-custom-shell)
- [高效MacBook工作环境配置](http://www.xialeizhou.com/?p=71)
- [程序员如何优雅地使用 Mac？](http://www.zhihu.com/question/20873070)