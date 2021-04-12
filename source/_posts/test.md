---
title: 'hexo+github page建站踩坑'
date: 2021-04-02 21:28:45
---
整体上来说同[hexo官方教程](https://hexo.io/zh-cn/docs/github-pages)所述没什么不同
但要注意：github已经将主代码分支名设置为main，所以：.travis.yml文件应该如下所示
```yaml
	sudo: false
	language: node_js
	node_js:
	  - 10 # use nodejs v10 LTS
	cache: npm
	branches:
	  only:
	    - main # build master branch only
	script:
	  - hexo generate # generate static files
	deploy:
	  provider: pages
	  skip-cleanup: true
	  github-token: $GH_TOKEN
	  keep-history: true
	  on:
	    branch: main
	  local-dir: public
```
即把其中的master替换为main