---
title: vs_latex-workshop插件的设置
date: 2021-04-07 15:37:42
tags:
---

# 第一步 打开setting.json

ctrl + ,        :打开设置界面

点按右上角符号进入文本设置功能

# 第二步 修改

!!!PS:在setting 最大一个大括号中

添加：

```json
"latex-workshop.latex.tools": [
	{
		"name": "xelatex",
		"command": "xelatex",
		"args": [
			"-synctex=1",
			"-interaction=nonstopmode",
			"-file-line-error",
			"%DOCFILE%"
		]
	},
	{
		"name": "pdflatex",
		"command": "pdflatex",
		"args": [
			"-synctex=1",
			"-interaction=nonstopmode",
			"-file-line-error",
			"%DOCFILE%"
		]
	},
	{
		"name": "bibtex",
		"command": "bibtex",
		"args": [
			"%DOCFILE%"
		]
	}
],

"latex-workshop.latex.recipes": [
	{
		"name": "xelatex",
		"tools": [
			"xelatex"
		],
	},
	{
		"name": "pdflatex",
		"tools": [
			"pdflatex"
		]
	},
	{
		"name": "xe->bib->xe->xe",
		"tools": [
			"xelatex",
			"bibtex",
			"xelatex",
			"xelatex"
		]
	},
	{
		"name": "pdf->bib->pdf->pdf",
		"tools": [
			"pdflatex",
			"bibtex",
			"pdflatex",
			"pdflatex"
		]
	}
],

```
以上代码取自[vscode写LaTex教程](https://blog.csdn.net/qq_21567385/article/details/106943325)

# 第三步 多次重启