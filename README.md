# MacBookAir first setup
-----

MBAをクリーンインストールしてから、開発環境を構築するまでの手順をまとめておく。

参考：

[brew bundle / cask で Homebrew も他の Mac アプリもまとめて管理・インストールする](http://www.d-wood.com/blog/2014/03/12_5808.html)

[新卒エンジニア向け：Macにインストールすべきアプリ達](http://tech.basicinc.jp/Mac/2014/04/20/mac_app_engineer/)


# target OS, package(software)

## System Configuration

- OS: Mac OS X 10.9.2 (marvericks)
- User
- Network

- システム環境設定
  - Dock
  - トラックパッド
  - ネットワーク
  - 共有
  - ユーザとグループ
  - 日付と時刻

- font

[powerlineとSourceCodeProで簡単につくれるキレイな開発環境](http://qiita.com/ta9to/items/4a8026fff7e177736060)を実現するために、
fontをインストールする

```
$ git clone https://github.com/Lokaltog/powerline-fonts.git
```

上記でcloneしたファイルからSourceCode Proのファイルを選択し、ダブルクリックすると、フォントが登録される。

iTermで使用するフォントを設定する


## ssh Configuration

- ssh keys

## Middleware Configuration

- xcode
- homebrew
- brew bundle Brewfile 

## Package Configuration

- dotfiles


# xcode command line tools


```
$ xcode-select --install
xcode-select: note: install requested for command line developer tools
```

gitのインストールを確認

```
$ git --version

Agreeing to the Xcode/iOS license requires admin privileges, please re-run as root via sudo.

```

xcode.appを起動するか、次のコマンドでライセンスに同意する

```
$ sudo xcodebuild -license
```


```
$ git --version
git version 1.8.5.2 (Apple Git-48)
```

# homebrew

```
$ ruby -e "$(curl -fsSL https://raw.github.com/Homebrew/homebrew/go/install)"
==> This script will install:
/usr/local/bin/brew
/usr/local/Library/...
/usr/local/share/man/man1/brew.1

Press RETURN to continue or any other key to abort
==> /usr/bin/sudo /bin/mkdir /usr/local
Password:
==> /usr/bin/sudo /bin/chmod g+rwx /usr/local
==> /usr/bin/sudo /usr/bin/chgrp admin /usr/local
==> /usr/bin/sudo /bin/mkdir /Library/Caches/Homebrew
==> /usr/bin/sudo /bin/chmod g+rwx /Library/Caches/Homebrew
==> Downloading and installing Homebrew...
remote: Counting objects: 168676, done.
remote: Compressing objects: 100% (47202/47202), done.
remote: Total 168676 (delta 120357), reused 168676 (delta 120357)
Receiving objects: 100% (168676/168676), 32.58 MiB | 554.00 KiB/s, done.
Resolving deltas: 100% (120357/120357), done.
From https://github.com/Homebrew/homebrew
 * [new branch]      master     -> origin/master
HEAD is now at 3404335 dynamodb-local 2014-04-24
==> Installation successful!
You should run `brew doctor' *before* you install anything.
Now type: brew help
```

```
$ brew doctor
Your system is ready to brew.
```

# brew bundle

```
$ brew bundle Brewfile 
Already up-to-date.
Cloning into '/usr/local/Library/Taps/homebrew/homebrew-binary'...
remote: Reusing existing pack: 137, done.
remote: Total 137 (delta 0), reused 0 (delta 0)
Receiving objects: 100% (137/137), 21.78 KiB | 0 bytes/s, done.
Resolving deltas: 100% (63/63), done.
Checking connectivity... done.
Tapped 13 formula
Cloning into '/usr/local/Library/Taps/homebrew/homebrew-versions'...
remote: Reusing existing pack: 1949, done.
remote: Counting objects: 6, done.
remote: Compressing objects: 100% (6/6), done.
remote: Total 1955 (delta 2), reused 0 (delta 0)
Receiving objects: 100% (1955/1955), 625.20 KiB | 212.00 KiB/s, done.
Resolving deltas: 100% (1064/1064), done.
Checking connectivity... done.
Tapped 137 formula
Cloning into '/usr/local/Library/Taps/phinze/homebrew-cask'...
remote: Reusing existing pack: 28852, done.
remote: Counting objects: 10, done.
remote: Compressing objects: 100% (10/10), done.
remote: Total 28862 (delta 2), reused 0 (delta 0)
Receiving objects: 100% (28862/28862), 10.72 MiB | 1004.00 KiB/s, done.
Resolving deltas: 100% (16633/16633), done.
Checking connectivity... done.
Tapped 1 formula
==> Cloning https://github.com/phinze/homebrew-cask.git
Cloning into '/Library/Caches/Homebrew/brew-cask--git'...
remote: Counting objects: 1680, done.
remote: Compressing objects: 100% (1646/1646), done.
remote: Total 1680 (delta 34), reused 868 (delta 24)
Receiving objects: 100% (1680/1680), 4.93 MiB | 999.00 KiB/s, done.
Resolving deltas: 100% (34/34), done.
Checking connectivity... done.
Note: checking out '1f69c04cd66eefb1dd4268de3a0f22dc60332e3d'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by performing another checkout.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -b with the checkout command again. Example:

  git checkout -b new_branch_name

==> Checking out tag v0.33.0
🍺  /usr/local/Cellar/brew-cask/0.33.0: 1519 files, 6.0M, built in 11 seconds

...
```

# NeoBundle for vim, zsh

```
$ curl https://raw.githubusercontent.com/Shougo/neobundle.vim/master/bin/install.sh | sh
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  1948  100  1948    0     0   5196      0 --:--:-- --:--:-- --:--:--  5208
git is /usr/bin/git
Start fetch NeoBundle...
Cloning into '/Users/fujimoto/.vim/bundle/neobundle.vim'...
remote: Reusing existing pack: 6455, done.
remote: Total 6455 (delta 0), reused 0 (delta 0)
Receiving objects: 100% (6455/6455), 1.54 MiB | 283.00 KiB/s, done.
Resolving deltas: 100% (2684/2684), done.
Checking connectivity... done.
Done.
Please write NeoBundle initial setting to your vimrc path ...


"NeoBundle Scripts-----------------------------
if has('vim_starting')
  set nocompatible               " Be iMproved

  " Required:
  set runtimepath+=/Users/fujimoto/.vim/bundle/neobundle.vim/
endif

" Required:
call neobundle#begin(expand('/Users/fujimoto/.vim/bundle'))

" Let NeoBundle manage NeoBundle
" Required:
NeoBundleFetch 'Shougo/neobundle.vim'

" My Bundles here:
NeoBundle 'Shougo/neosnippet.vim'
NeoBundle 'Shougo/neosnippet-snippets'
NeoBundle 'tpope/vim-fugitive'
NeoBundle 'kien/ctrlp.vim'
NeoBundle 'flazz/vim-colorschemes'

" You can specify revision/branch/tag.
NeoBundle 'Shougo/vimshell', { 'rev' : '3787e5' }

" Required:
call neobundle#end()

" Required:
filetype plugin indent on

" If there are uninstalled bundles found on startup,
" this will conveniently prompt you to install them.
NeoBundleCheck
"End NeoBundle Scripts-------------------------


Done.
Complete setup NeoBundle!
```

# homesick


## vim

```
$ ln -s dotfiles/.vimrc .vimrc
$ vim
Not installed bundles:  ['vimproc', 'vimshell', 'vim-slime', 'VimClojure', 'syntastic', 'neocomplcache', 'unite.vim', 'alpaca_powertabline', 'powerline']
Install bundles now?
(y)es, [N]o: y


[neobundle/install] Update started: (2014/04/28 00:04:59)
[neobundle/install] (1/9): |syntastic| git clone --recursive https://github.com/scrooloose/syntastic.git "/Users/fujimoto/.vim/bundle/syntastic"
[neobundle/install] (2/9): |vimproc| git clone --recursive https://github.com/Shougo/vimproc.git "/Users/fujimoto/.vim/bundle/vimproc"
[neobundle/install] (3/9): |powerline| git clone --recursive https://github.com/Lokaltog/powerline.git "/Users/fujimoto/.vim/bundle/powerline"
[neobundle/install] (4/9): |vimshell| git clone --recursive https://github.com/Shougo/vimshell.git "/Users/fujimoto/.vim/bundle/vimshell"
[neobundle/install] (1/9): |syntastic| Updated
[neobundle/install] |syntastic|  -> 2a770da3a036ec2268d2ef7e7a7b9d0ed7d49340
[neobundle/install] (2/9): |vimproc| Updated
[neobundle/install] |vimproc|  -> 25ad75f51dc0c19ad87b896818080d10e0bf78fc
[neobundle/install] (3/9): |powerline| Updated
[neobundle/install] |powerline|  -> fa502281f3c144f7d0f92da2b17f2479c8ecea55
[neobundle/install] (4/9): |vimshell| Updated
[neobundle/install] |vimshell|  -> 1f90884a10642d53115182e300285064b09c038c
[neobundle/install] (5/9): |alpaca_powertabline| git clone --recursive https://github.com/alpaca-tc/alpaca_powertabline.git "/Users/fujimoto/.vim/bundle/alpaca_powertabline"
[neobundle/install] (6/9): |unite.vim| git clone --recursive https://github.com/Shougo/unite.vim.git "/Users/fujimoto/.vim/bundle/unite.vim"
[neobundle/install] (7/9): |vim-slime| git clone --recursive https://github.com/jpalardy/vim-slime.git "/Users/fujimoto/.vim/bundle/vim-slime"
[neobundle/install] (8/9): |neocomplcache| git clone --recursive https://github.com/Shougo/neocomplcache.git "/Users/fujimoto/.vim/bundle/neocomplcache"
[neobundle/install] (5/9): |alpaca_powertabline| Updated
[neobundle/install] |alpaca_powertabline|  -> c9add3898f29cbbad8f57108ef73baab8fd6e21d
[neobundle/install] (6/9): |unite.vim| Updated
[neobundle/install] |unite.vim|  -> 8ee4ce8f94735592bd79a1771ddedc1c98372b34
[neobundle/install] (7/9): |vim-slime| Updated
[neobundle/install] |vim-slime|  -> dc614e65eb86cadbf49b4f2f04998ceb9d21d890
[neobundle/install] (8/9): |neocomplcache| Updated
[neobundle/install] |neocomplcache|  -> da44ba4a92eef3860bdee2d96d755a7171889a70
[neobundle/install] (9/9): |VimClojure| git clone --recursive https://github.com/vim-scripts/VimClojure.git "/Users/fujimoto/.vim/bundle/VimClojure"
[neobundle/install] (9/9): |VimClojure| Updated
[neobundle/install] |VimClojure|  -> 2a17c249571395a7f45523d38cac6a9326ecf8f1
[neobundle/install] Installed/Updated bundles:
syntastic
vimproc
powerline
vimshell
alpaca_powertabline
unite.vim
vim-slime
neocomplcache
VimClojure
Press ENTER or type command to continue
```

## zsh

change shell

```
$ chsh -s /bin/zsh
Changing shell for fujimoto.
Password for fujimoto: 
$ 
$ echo $SHELL
/bin/bash
```

new terminal

```
% echo $SHELL
/bin/zsh
% ln -s dotfiles/.zshrc .zshrc
```

new terminal

```
 fujimoto  ~  
```

上記のままでは、古いzshを使ってしまう。
homebrewでインストールしたzshを使うためには、次の手順が必要。

```
$ sudo vi /etc/shells
```

`/usr/local/bin/zsh`を追加

```
# List of acceptable shells for chpass(1).
# Ftpd will not allow users to connect who are not using
# one of these shells.

/bin/bash
/bin/csh
/bin/ksh
/bin/sh
/bin/tcsh
/bin/zsh
/usr/local/bin/zsh
```

デフォルトのログインシェルをzshに変更する

```
$ chpass -s /usr/local/bin/zsh
```

新しいターミナルを起動して、$SHELLを確認

```
$ echo $SHELL
/usr/local/bin/zsh
```

## tmux

 pending...


# git

.gitconfig

# iterm2


# ruby/rbenv


# chrome
