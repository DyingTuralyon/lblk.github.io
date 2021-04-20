---
title: tmux_for_mac_install
date: 2021-04-17 16:58:41
tags:
---

本文将解决：

# brew 换源

## 1

```bash

# 替换brew.git:
$ cd "$(brew --repo)"
# 中国科大:
$ git remote set-url origin https://mirrors.ustc.edu.cn/brew.git
# 清华大学:
$ git remote set-url origin https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/brew.git
#以上二选一
```

## 2
```bash

# 替换homebrew-core.git:
$ cd "$(brew --repo)/Library/Taps/homebrew/homebrew-core"
# 中国科大:
$ git remote set-url origin https://mirrors.ustc.edu.cn/homebrew-core.git
# 清华大学:
$ git remote set-url origin https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/homebrew-core.git
#以上二选一
```
## 3
```bash
brew update
```
## 4
```bash
$echo 'export HOMEBREW_BOTTLE_DOMAIN=https://mirrors.tuna.tsinghua.edu.cn/homebrew-bottles/bottles/' >> ~/.zshrc
$source ~/.zshrc
```
以上要注意我是用的zsh，如果你用的是bash终端，把上面的zshrc替换为bash_profile即可

# tmux安装和学习
第一次见到这种格式的tutorial，将就下吧
```
git clone https://github.com/tmux/tmux.git
cd tmux
nroff -mdoc tmux.1|less
```
# riscv-unknown-elf-gdb的安装
[文件下载](https://rcore-os.github.io/rCore-Tutorial-Book-v3/chapter0/5setup-devel-env.html#gdb)
[安装方法](https://github.com/LoesterFranco/riscv_gcc_prebuilt)

