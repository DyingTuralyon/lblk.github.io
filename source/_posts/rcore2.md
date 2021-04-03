---
title: rcore第二章知识点
mathjax: true
---
# 1.移除os依赖
## 	1.1移除std
##     1.2接手std工作
### 			1.2.1接手panic
​                            ="abort"
#### 				1.2.1.1panic_handler -> loop{};
#### 				1.2.1.2eh_personality
##### 						1.2.1.2.1堆栈展开
### 			1.2.2接手入口点
#### 				1.2.2.1c入口点
#### 				1.2.2.2原main入口点
## 	1.3用编译命令禁用原c入口点

# 2.目标三元组

## 	2.1 cpu架构

## 	2.2 供应商

## 	2.3 操作系统

## 	2.4 ABI

# 3. 使用给定三元组（riscv64）编译项目为内核镜像
```cmd
$ cargo build --target riscv64imac-unknown-none-elf
```
## 3.1 安装core
```cmd
$ rustup target add riscv64imac-unknown-none-elf
```
## 3.2 配置目标三元组进入 #.cargo/config
```cmd
$ cargo install cargo-binutils
$ rustup component add llvm-tools-preview
```
## 3.3安装「objdump、objcopy」 $\in$ biuntils工具集

## 3.4编译生成64位ELF文件
```cmd
$ cargo build --target riscv64imac-unknown-none-elf
```
## 3.5由ELF文件生成内核镜像
```cmd
$ rust-objcopy target/riscv64imac-unknown-none-elf/debug/os --strip-all -O binary target/riscv64imac-unknown-none-elf/debug/kernel.bin
```

# 4. 使用链接脚本

## 4.1链接脚本的编写

## 4.2链接脚本加入.cargo/config配置

## 4.3跑起来
```
$ cargo build
$ rust-objdump target/riscv64imac-unknown-none-elf/debug/os -h --arch-name=riscv64
$ rust-objdump target/riscv64imac-unknown-none-elf/debug/os -d --arch-name=riscv64
```

# 5.重写程序入口

## 5.1用汇编编写_start

## 5.2用rust_main接管_start

# 6.Qemu降临

## 6.1 qemu_concept_Intro

## 6.2 复杂的qemu-内核加载

# 7.为open_SBI的使用而重构一切

# 8.自己动手写println!()

第一次为他人而非自己提供接口！

