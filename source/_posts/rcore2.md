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

## 3.1 安装core

## 3.2 配置目标三元组进入 #.cargo/config

## 3.3安装objdump $\in$ biuntils工具集

## 3.4编译生成64位ELF文件

