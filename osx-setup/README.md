# OSX - Setup for Web Developer
> This is an opinionated guide 

# Package manager 📦

**Homebrew** is a free and open-source software package management system that simplifies the installation of software on Apple's macOS operating system and Linux. 

Link: https://brew.sh/

To install it, run the following command in a terminal

```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

# Fonts 💎

Programmers use a lot of symbols, often encoded with several characters. For the human brain, sequences like ->, <= or := are single logical tokens, even if they take two or three characters on the screen. Your eye spends a non-zero amount of energy to scan, parse and join multiple characters into a single logical one.

To solve that, we can use a monospaced font with programming ligatures like **Fira Code** 

Link: https://github.com/tonsky/FiraCode

Installing font:

```
brew tap caskroom/fonts
brew cask install font-fira-code
```

With the steps below, we'll use it in the terminal and in our favorite IDE.

# Console under steroids 💪

## Terminal 🖥

**Hyper** is a beautifull and higly customizable terminal built on web technologies.

Get the latest version here https://hyper.is/

To use the **Fira Code** font into it, open up **Hyper** and go to `Hyper > Preferences`. It will open, `.hyper.js` in your default text editor.

Search the `fontFamily` key and set `"Fira Code"` in the begining of the list:

```
fontFamily: '"Fira Code", "DejaVu Sans Mono", "Lucida Console", monospace',
```

Then, update your list of plugins to include `hyperterm-atom-dark` beautiful theme, like so:

```
plugins: [
  'hyperterm-atom-dark'
],
``` 

Fully reload HyperTerm with `Cmd+Shift+R`.

## Unix Shell ⚙️

**Zsh** is a shell designed for interactive use (much better than Bash, the OSX default shell). It includes some great features: better completions, command history, shortcuts, spell checke, variable handling, and many others.

Follow these steps for the setup => [Install-and-set-up-zsh-as-default](https://github.com/robbyrussell/oh-my-zsh/wiki/Installing-ZSH#install-and-set-up-zsh-as-default)

Then, run **Zsh** for the first time, it will prompt you a wizzard.
Recommanded options work fine.

```
zsh
```

A `.zshrc` file should have been generated in your home directory (it's a hidden file)

## Shell framework 🛠

**Oh My Zsh** collects third-party plug-ins and themes for the Zsh shell.

Link: https://ohmyz.sh/

Installation via curl

```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

Some interesting plugins:

- `git` - git aliases and shortcuts (shipped with **Oh My Zsh**)
- `zsh-syntax-highlighting` - to have commands colorized (setup [here](https://github.com/zsh-users/zsh-syntax-highlighting/blob/master/INSTALL.md#oh-my-zsh))
- `zsh-autosuggestions` - to have browser-like autocompletions (setup [here](https://github.com/zsh-users/zsh-autosuggestions/blob/master/INSTALL.md#oh-my-zsh))

Check the whole list of plugins [here](https://github.com/robbyrussell/oh-my-zsh/tree/master/plugins).

## Prompt 🚀

**Spaceship Prompt** is a minimalistic, powerful and extremely customizable Zsh prompt. It displays some icons and useful information about the current directory such as the git status or the node version used. 

Link: https://denysdovhan.com/spaceship-prompt/

Installation with Oh My Zsh:

```
git clone https://github.com/denysdovhan/spaceship-prompt.git "$ZSH_CUSTOM/themes/spaceship-prompt"
```

Symlink `spaceship.zsh-theme` to your oh-my-zsh custom themes directory:

```
ln -s "$ZSH_CUSTOM/themes/spaceship-prompt/spaceship.zsh-theme" "$ZSH_CUSTOM/themes/spaceship.zsh-theme"
```

Finally, set `ZSH_THEME="spaceship"` in your `.zshrc` file.

And tada! ⭐️️ ⭐️️ ⭐️️ 

![alt text](terminal.gif)

# Node.js / npm 🌱
**Node.js** allows you to run JavaScript on the server and comes with **npm**, a powerful package manager to consume and distribute JavaScript modules. 

Get the lastest version available:

```
brew install node
```

# Git 📖
Git is a distributed version-control system for tracking changes in source code during software development.

```
brew install git
```

Then set your user name and email address. This is important because every Git commit uses this information:

```
git config --global user.name "John Doe"
git config --global user.email johndoe@example.com
```

Optionally, set **VS Code** as default Git editor
```
git config --global core.editor "code --wait"
```

# Visual Studio Code ⌨
**VS Code** is a lightweight but powerful source code editor which runs on your desktop and is available for Windows, macOS and Linux. It comes with built-in support for JavaScript, TypeScript and Node.js.

Install it from the official website [here](https://code.visualstudio.com/).

Follow these [instructions](https://github.com/tonsky/FiraCode/wiki/VS-Code-Instructions) to use **Fira Code** font with your favorite IDE.

# Bonus 💯
You can show/hide quickly your terminal with hotkeys thanks to that **Hyper** [plugin](https://github.com/CWSpear/hyperterm-visor)

Or even better you can use custom gesture like _3 fingers Swipe down_ to show up the terminal and _3 fingers Swipe up_ to hide it.

Take a look on **BetterTouchTool** and that [post](https://www.howtogeek.com/364227/how-to-customize-mac-trackpad-gestures-with-bettertouchtool/) to do so

Some others useful resources:
- https://github.com/hmml/awesome-zsh
- https://github.com/bnb/awesome-hyper