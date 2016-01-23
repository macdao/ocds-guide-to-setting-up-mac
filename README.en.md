# Mac Setup Guide for OCD

## How to setup a efficient working environment

*Translated from [强迫症的 Mac 设置指南](https://github.com/macdao/ocds-guide-to-setting-up-mac#强迫症的-mac-设置指南), thanks to author: QiXi from Thoughtworks China - fff*

## Table of Contents
  * [1. OS X](#1-os-x)
    * [Function Keys](#function-keys)
    * [Keyboard Only Control](#keyboard-only-control)
    * [Others](#others)
    * [Change `click` of Trackpad to `Tap`](#change-`click`-of-trackpad-to-`tap`)
    * [Voice](#voice)
    * [Dock Position](#dock-position)
    * [Change `Caps Lock` to `Control`](#change-`caps-lock`-to-`control`)
    * [Remove all Dock icons[OCD]](#remove-all-dock-icons[ocd])
    * [Reset the order of icons on Launchpad[OCD]](#reset-the-order-of-icons-on-launchpad[ocd])
  * [2. Daily Tools](#2-daily-tools)
    * [Homebrew](#homebrew)
    * [Homebrew Cask](#homebrew-cask)
    * [iTerm2](#iterm2)
    * [Oh My Zsh](#oh-my-zsh)
    * [Stow](#stow)
    * [Git Alias](#git-alias)
    * [ShiftIt](#shiftit)
    * [Sublime Text 2](#sublime-text-2)
    * [MarkDown](#markdown)
    * [z](#z)
    * [Vimium](#vimium)
    * [LastPass](#lastpass)
    * [SourceTree](#sourcetree)
    * [CheatSheet](#cheatsheet)
    * [Alfred](#alfred)
  * [3. Tools for developers](#3-tools-for-developers)
    * [Java](#java)
    * [rbenv](#rbenv)
    * [Ruby Daily Alias](#ruby-daily-alias)
  * [References](#references)

I was always thinking about to write this article, to share all the experiences I've learnt from other colleagues. Though there are already some really good books, from which I've learnt a lot also. But I still want to share my own experiences.

In project, I normally work with 1 to 10 people, and paring a lot by sharing the same laptop, with external display, and extra mouse, keyboard. I'm most working on Java, Ruby, Node.js, Web and etc, and using lots softwares from [JetBrains](https://www.jetbrains.com/), like IntelliJ IDEA, RubyMine, WebStorm and ect.

I know my knowledge is so limited, so I want the opinions from you by sharing you this article. Now days, more efficient way and better tools are still keeping comming, I'll keep updating it, to collect the better ways and tools here, it's my greedy wish. For latest version please visit: <https://github.com/macdao/ocds-guide-to-setting-up-mac>. Issues or Pull Requests are welcomed. Looking forward to your feedbacks.

Several points of efficient Mac environment in my opinion:

- Automate

  Take a example, there are several steps to install an application manually: 
  1. Open your browser, 
  2. Search by the application name,
  3. Open the official site for the applicaiton,
  4. Find the download link,
  5. Downloading,
  6. Install it,
  7. Some post steps.
  
  But with automatic tools, you only required to do:
  1. Open terminal,
  2. Type in commands,
  3. Wait to be finished.

  Automate helps to limit the steps and increase the efficiency a lot.

- Consistence

  When I'm paring, sometime the shortcuts or commands are different between each other's laptop. I strogly recommend that, at least in the team, try to keep using the same shortcut and commands(I forget the practice name, there have to be one, please let me know if you get it).

- Just enough

  Enough is perfect. If the system itself provides the function, I won't install any other third party tools.

- Efficience

  Everything is about efficience.

*For third party applications only simple steps are provided, please go to offial site for detailed installation and instruction documents.*

*Some sections are marked with [OCD], that means it's quite personal choices from me, take it or ignore it all depends on if you like it or not.*

*[OCD(obsessive-compulsive disorder)](https://www.google.co.za/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&cad=rja&uact=8&ved=0CBsQFjAAahUKEwiDve-b7JHJAhUDxxQKHXF2DOE&url=https%3A%2F%2Fen.wikipedia.org%2Fwiki%2FObsessive%25E2%2580%2593compulsive_disorder&usg=AFQjCNGDkJsHHtm6hy60uzEMBn2ee3rSoA&bvm=bv.107467506,d.d24), I didn't mean it, just make fun. Yes, I don't have that disease ;)*



## 1. OS X

Things related with OS X settings.

### Function Keys

By default, F1-F12 are special funtion keys, like adjust screen brightness. You are required to press Fn at the same time, when you need input F1-F12(like IntelliJ IDEA shortcuts). It's not so convenient for developers.

To avoid pressing Fn: go to `System Preferences` > `Keyboard`，select `Use all F1, F2, etc. keys as standard function keys` in `Keyboard` tab。

### Keyboard Only Control

You may see this dialog before, when you try to close files in Sublime Text:

![dialog-box-without-all-controls](dialog-box-without-all-controls.png)

You may notice that the `Save` button is quite different with the other two, it's BLUE. This kind of blue button is called `default button`, except triggering by clicking, you also can trigger it by `enter`.

What else, how to trigger `Don't Save` without mouse clicking?

Go to `System Preferences` > `Keyboard`, select `All controls` in `Shortcuts` tab or just press `⌃F7`. And the dialog will turn into:

![dialog-box-with-all-controls](dialog-box-with-all-controls.png)

The `Don't Save` button has borders now, so you can trigger it by `space`. And also, you can move the focus(blue borders) to other buttons by press `tab`, you can get rid of your mouse now.

Except the way above, you can also select `Don't Save` by click `⌘⌫`(command+delete). This shortcut means select any button which means 'delete' or 'do not save'.

Of course, you may click `Esc` to trigger `Cancel`.

*Some lines are missing here. As not helping a lot - fff*

### Others

Reduce using of Mouse and Trackpad may increase your efficiency.

- [Mac keyboard shortcts](https://support.apple.com/kb/HT201236)

  Apple official documents. Like how to move cursor between lines, words and so on.
  
- [Mac keyboard shortcuts for accessibility features](https://support.apple.com/kb/HT204434)

  Apple official documents. The selection of blue button part is from this.

### Change `click` of Trackpad to `Tap`

By default Trackpad is triggered by click, but you can change it to tap.

Goto `System Preferences` > `Trackpad`，check `Tap to click` in `Point & Click` tab.

### Voice

OS X can speak by：

```sh
say hello
```

Combine it with other bash commands using `&&` or `;` like this:

```sh
brew update && brew upgrade && brew cleanup ; say mission complete
```

Also you can let it speak almost anywhere by selecting one word and press `⌥+Esc`(Alt/Option+Esc). Before that you need goto `System Preferences` > `Dictation & Speech`, check `Speak selected text when the key is pressed` in `Text to Speech` tab. 

*Some lines are missing here. As not helping a lot - fff*

### Dock Position

Dock comes at the bottom of screen as default, but as the resolution is 16:10, we'd better move it to left or right of screen to gain more vertical space.

### Change `Caps Lock` to `Control`

I use `Control` a lot, but it's at the left buttom corner, which is quite hard to reach. And I prefer `Shift` to input capitals, or input lower case and transform them with shortcut, so I use `Caps Lock` quite few.

So, I change `Caps Lock` into `Control`. And I found that lots twers are doing the same thing, may be influenced by [HHKB](https://en.wikipedia.org/wiki/Happy_Hacking_Keyboard).

Howto: goto `System Preferences` > `Keyboard`, click `Modifier Keys...` in `Keyboard` tab, in the popup window change the option `Caps Lock (⇪) Key:` to `⌃ Control`.

### Remove all Dock icons[OCD]

*本条目对于强迫症适用。It's for OCD(obsessive-compulsive disorder)*

There are some default icons on the docker, I hardly use most of them. And after opening several daily applications, the docker comes so noisy, and the icons turn to really small. So I remove all the default icons on the docker, to make space for runing applications.

*Finder cannot be removed.*

### Reset the order of icons on Launchpad[OCD]

*本条目对于强迫症适用。It's for OCD(obsessive-compulsive disorder)*

```sh
defaults write com.apple.dock ResetLaunchPad -bool true; killall Dock
```

*Some lines are missing here. As not helping a lot - fff*

## 2. Daily Tools

Some daily softwares, and not related with developing.

### [Homebrew](http://brew.sh)

Package management, official decription: "The missing package manager for OS X".

Go to official site for installation steps.

After installation, you only need to run command below to install mysql, gradle, maven, node：

```sh
brew install mysql gradle maven node
```

PS: install brew will download and install Apple Command Line Tools automatically.

*Some lines are missing here. As not helping a lot - fff*

### [Homebrew Cask](http://caskroom.io)

brew-cask helps you to install OS X Applications. Like to install Chrome：`brew cask install google-chrome`. Also Evernote, Skype, Sublime Text, VirtualBox, Java7 ...

brew-cask is driven by community, you may raise a pull request when you found any missing or outdated application.

Installation:

```sh
brew install caskroom/cask/brew-cask
```

You would like to search if you not sure if some application is already in cask.
```sh
brew cask search java7
```

*Some lines are missing here. As not helping a lot - fff*

### [iTerm2](https://www.iterm2.com/)

iTerm2 is the most widely used terminal tool, considered as the replacement of Terminal. It provides [a group of practical features](https://www.iterm2.com/features.html), include `Split Panes`. Its default black background makes me throw away terminal without any hesitation.

Installation:

```sh
brew cask install iterm2
```
Thanks to brew-cask ~

In iTerm2, except the commond shortcuts like `^E`(ctrl+E)(find more [here](#Others)). And after some configuration you can have more shortcuts like `⌥B`(alt+B), `⌥F`(alt+F). 
HowTo: go to `Preferences` > `Profiles` > `Keys`, change the option of `Left option (⌥) key acts as` and `Right option (⌥) key acts as` to `+ESC`.

When you open new window/tab, by default you're at user home directory, and need input commands to go somewhere else. If you want to open new window/tab in previous directory, you can set it like this:
`Preferences` > `Profiles`, and select your profile('Default' for most of time), go to `General` tab, check `Reuse previous seesion's directory` for `Working Directory`.

If you want to save all the current windows/tabs layout, press `⌘⇧S`(command+shift+S) to save the window arrangement. Also you can find this item in the `Window` menu on the top.(*added by fff*)

Till now, Terminal should be given up, and turn to use iTerm2.

And in iTerm2, double click will select the according word, triple click will select the current line. Also the selected content will be in your clip-board, no addition `⌘C`(command+C) is required.

### [Oh My Zsh](http://ohmyz.sh)

By default Bash is only white and black, there is no more colors there. And On-My-Zsh brings the colorful world to you. Oh-My-Zsh also brings you a set of plugins and tools, which is quite handy for simplify commands input. In the below you will find that I love it to death.

Go to official site for installation steps.

Plugins I'm using: `git z sublime history rbenv bundler rake`

Oh-My-Zsh uses Z shell（zsh）, which is quite close to Bash, but it's not Bash.

In Z shell, `~/.zshrc` is the most important configure file. Oh-My-Zsh will set the current path into `~/.zshrc` as `$PATH` during installation. As I'm using brew, this is not something that I want to have. With brew, we are not encouraged to customize `$PAHT`, and by default Oh-My-Zsh already set `$PAHT` with quite good value:`$HOME/bin:/usr/local/bin:$PATH`, in which contains the `$HOME/bin`, it means we can put our self defined script under `$HOME/bin`.

so I recommend you to reset the `~/.zshrc`:

```sh
cp ~/.oh-my-zsh/templates/zshrc.zsh-template ~/.zshrc
```

Oh-My-Zsh gets [more valuable plugins](https://github.com/robbyrussell/oh-my-zsh/wiki/Plugins-Overview).

Besides Oh-My-Zsh, there is [Oh My Fish](https://github.com/oh-my-fish/oh-my-fish)，which take [Fishshell](http://fishshell.com/) as fundation.

### [Stow](http://www.gnu.org/software/stow/)
GNU stow is the super girl(-.-) of symlink management. Mainly it's used to symlink your [dotfiles](http://dotfiles.github.io/), like emacs，git configuration files of fish/zsh.

Installation:

```
brew install stow
```

After installing, we can symlink the dotfiles. The full instructions of stow and dotfiles are here:<https://github.com/jcouyang/dotfiles>.

After symlinking all your dotfiles to `~/dotfiles`, push it to github. There is no worries any more for setuping another new laptop.

### Git Alias

Almost everyone is looking for ways to make himself efficient, like git alias, using `git st` instead of `git status`. But it requires some manual configuration, which makes everyone's some different.

Oh-My-Zsh provides a set of system aliases to achieve the same prepose. For example take `gst` as the alias of `git status`. Also the git plugin of Oh-My-Zsh is enabled by default, which means if you're using Oh-My-Zsh, you are having a set of efficient aliases, which is been commonly used globally, isn't that wonderful?!

Some frequently used aliases for me:

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


The full list is here: <https://github.com/robbyrussell/oh-my-zsh/wiki/Plugin:git>, or simply run command `alias | grep git` in Oh-My-Zsh window.


*Some lines are missing here. As not helping a lot - fff*


### ShiftIt

In OS X you only can adjust window size by dragging. I've tried lots of window management tools, but most of them have the conflict key mapping(mostly with IntelliJ IDEA). ShiftIt is the apparently rare one without any conflicts.

Installation:

```sh
brew cask install shiftit
```

SizeUp is one replacer，share the same main shortcuts with ShiftIt.

Divvy is another replacer, need to purchase through appstore.(*added by fff*)

For hackers: [Slate](https://github.com/jigish/slate), configuration reference: <http://thume.ca/howto/2012/11/19/using-slate/>

### Sublime Text 2

Installation:

```sh
brew cask install sublime-text
```

Open file with Sublime Text in command line is quite handy, normally we need to link it first(following:[OS X Command Line](https://www.sublimetext.com/docs/2/osx_command_line.html)) with: `ln -s "/Applications/Sublime Text 2.app/Contents/SharedSupport/bin/subl" ~/bin/subl`. 

But if you install it with brew-cask, the problem is already sorted by brew-cask, and it will remove the link when you uninstall Sublime Text.

At the same time, Oh-My-Zsh also provides the plugin for Sublime Text: `sublime`(<https://github.com/robbyrussell/oh-my-zsh/tree/master/plugins/sublime>), which is perfectly compliant with brew installed Sublime Text.

Replacers: Atom, TextMate, Sublime Text 3 etc. For all of them, brew-cask will manage the links for you.

### [MarkDown](https://daringfireball.net/projects/markdown/)

MacDown is a Markdown editor. As Mou doesn't support code highlighting, I switched to MacDown, which supports [GFM](https://help.github.com/articles/github-flavored-markdown/) perfectly.

I like Markdown a lot, and I write articles(include this one) with Markdown, also for slides([reveal.js](https://github.com/hakimel/reveal.js/)). Markdown makes me focus on the content itself, and won't waste me too much time on the styles and layouts.

Installation:

```sh
brew cask install macdown
```

### [z](https://github.com/rupa/z)

After opening new terminal, how do you get to the working directory? `cd xxx` or `^R`(ctrl+R, bash reverse search), or alias?

z helps you get the target directory easily. Like running `z cask` in my term, it will lead me to `/usr/local/Library/Taps/caskroom/homebrew-cask/Casks`.

It's quite easy to install, nothing is required to be downloaded, as it's already in Oh-My-Zsh. Open `~/.zshrc`, find plugins configuration line like this:`plugins=(git)`, and put `z` inside the parentheses like:`plugins=(git z)`, then re-initial terminal by `source ~/.zshrc`, it's there now.

Autojump is a replacer, which requires to be installed by brew.

### [Vimium](https://vimium.github.io/)

Vimium is a Google Chrome extension, which turns your chrome into a "hackers's browser", you can operate your chrome all by keyboard.

For installation please go to Chrome extension market.

For firefox there is a similar solution: [KeySnail](https://github.com/mooz/keysnail).

### [LastPass](https://lastpass.com)

LastPass is a password management tool, support a second login step, provides plugins for every browser and also Mac desktop version.

The most important thing, it provides **command line** version, install it by:

```sh
brew install lastpass-cli --with-pinentry
```

then, login into your account:

```sh
lpass login you@email.com
```

So you can copy password or integrate into other commands:

```sh
lpass show --password gmail.com -c
```

### [SourceTree](https://www.sourcetreeapp.com/)

SourceTree is an outstanding git GUI client from Atlassian. You may try if you want more than command line.

Installation:

```sh
brew cask install sourcetree
```

Brew-cast will add `stree` to `$PATH` when installing it. Run `stree` from terminal will invoke SourceTree open the Git repository under current path. for more: `stree --help`.

### [CheatSheet](http://www.mediaatelier.com/CheatSheet/)

CheatSheet will show a list of all active short cuts of the current application. Just hold the `⌘` for a bit longer.

![CheatSheet](http://www.mediaatelier.com/CheatSheet/imgs/main.png)

Installation:

```sh
brew cask install cheatsheet
```

### [Alfred](https://www.alfredapp.com)

The msut have tool for Mac user, comes together with a bunch of workflows, which will extremely save your operating time.

Easy to start, but takes more time to setup your self-defined workflows, but anyway there are already lots of workflows shared by nice peoples, visit [here](http://www.alfredworkflow.com/), choose what you like, and modify it in your way.

Installation:

```sh
brew cask install alfred
```

## 3. Tools for developers

### Java

There is no default JDK any more for new version of OS X, so you need to download and install it before you want to do some Java projects.

Before brew-cask, we are used to download from: <https://developer.apple.com/downloads/>. But which worse is that uninstall or upgrade takes such time.
For JDK package, which is pkg format, there is no automatic way to uninstall it.

But good news is brew-cask can do it for you:

```sh
brew cask install java
```

If you need Java-7 or Java-6, you can get from `homebrew-cask-versions`：

```sh
brew tap caskroom/versions
brew cask install java6
```

You can install several versions of JDK in Mac OS X, `/usr/libexec/java_home -V` will list all of them.

So here is the problem, Which one is the one used by running `java` or any Java application? normally, OS X invoke the newest version of all those installed JDK versions. But you can change it by set `JAVA_HOME`:

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

You may change `JAVA_HOME=/Library/Java/JavaVirtualMachines/1.6.0.jdk/Contents/Home` into `` JAVA_HOME=`/usr/libexec/java_home -v 1.6` ``, which is more widly used.

*Some lines are missing here. As not helping a lot - fff*

### [rbenv](https://github.com/sstephenson/rbenv)

Everyone need a Ruby version management tool. That's rbenv, which is quite light and can be installed by brew.

Installation:

```sh
brew install rbenv ruby-build
```

Then you need to enable `rbenv` plugin of Oh-My-Zsh, or you need to add `eval "$(rbenv init -)"` to `~/.zshrc` or `~/.zprofile`

Sometimes project will depend on some odd version, like: `ruby-2.1.0`, you should go checkout [rbenv-aliases](https://github.com/tpope/rbenv-aliases).

```sh
brew install rbenv-aliases
```

Replacer: RVM, chruby. But as RVM is unable to be installed by brew, and it also changes a bunch of files without any respect, that's why I already give RVM up. chruby is another light weight tool, and works perfactly with Oh-My-Zsh, it seems someone is using it in production enviroment.

### Ruby Daily Alias

Almost every Rubyist takes `bi` as alias of `bundle install`. Oh-My-Zsh provides `builder` plugin to setup a set of alias, like `bi`, `be`. Also allow you to run `rspec` directly, without any leading `be` or `bundle exec`. 

For detail list please go to <https://github.com/robbyrussell/oh-my-zsh/tree/master/plugins/bundler>.

Zsh shell has special usage for `[` and `]`, so `rake task[parameter]` will fail, you need to run it like this: `rake task\[parameter\]` or `noglob rake task[parameter]`. However Oh-My-Zsh already solves it, using the buildin rake plugin: `brake task[parameter]`.

Be aware of that, put `rake` after `bundler` when modifying the plugin settings in `~/.zshrc`, like:
```
plugins=(git z sublime history rbenv bundler rake)
```

## References

- [Hacker's Guide to Setting up Your Mac](http://lapwinglabs.com/blog/hacker-guide-to-setting-up-your-mac)
- [Setting up a new (OS X) development machine](https://mattstauffer.co/blog/setting-up-a-new-os-x-development-machine-part-1-core-files-and-custom-shell)
- [高效 MacBook 工作环境配置](http://www.xialeizhou.com/?p=71) **"Efficient MacBook working configurration", you need google translate*
- [程序员如何优雅地使用 Mac？](http://www.zhihu.com/question/20873070) **"How to use Mac elegantly for programmer", you need google translate also*
