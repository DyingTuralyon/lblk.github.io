---
title: python爬取douban_top250
date: 2021-04-12 09:42:14
tags:
---

本篇为毕业实习番外。

提出idea，初稿作者：张润琳

维护，调试：邓羊驼

```python
import requests
import re

# 得到指定一个URL的网页内容
def GetHTMLText(url):
    try:
        kv = {"User-Agent": "Mozilla/5.0"}            # 模拟浏览器头部信息，向豆瓣服务器发送消息   
        r = requests.get(url, headers=kv, timeout=30)
        r.raise_for_status()                        # 若状态码不是200，抛出HTTPError异常
        r.encoding = r.apparent_encoding              # 用文本中分析的编码替换整体的编码，保证页面编码正确
        return r.text
    except:
        return ""


# 对每一个获得的页面进行解析(通过正则表达式查找指定的字符串)
def parsePage(ilt,html):     # 结果列表类型  相关的HTML页面信息
    try:  
        title0 = re.compile(r'title=\".*?\"(?!/)')
        author0 = re.compile(r'<p class="pl">(.*?)</p>')
        #comment0= re.compile(r'<span class="inq">(.*?)</span>')

        title = title0.findall(html)   
        author = author0.findall(html)
        #comment = comment0.findall(html)
        for i in range(len(title)):
            t = (title[i].split('\"')[1])
            a = author[i].split("/")[0].split(" ")[-2]
            #c = (comment[i].split(':')[1])
            #print(title)
            ilt.append([t,a])     # 输出到相关的列表变量中
    except:
        print("")

        
        
# 输出信息
def printBooksList(ilt):
    tplt = "{:4}\t{:16}\t{:16}\t{:16}"    # 设置表格模板
    ttplt = "{:4}\t{:16}\t{:16}"
    #print(tplt.format("序号","书名","作者","评论")) 
    print(ttplt.format("序号","书名","作者"))      #设置表头
    count = 0      # 序号
    for g in ilt:
        count = count + 1
        print(ttplt.format(count,g[0],g[1]))
        #print(g)


    
# 主函数
def main():
    depth = 10
    start_url = 'https://book.douban.com/top250'
    infoList = []                  # 输出结果变量
    for i in range(depth):         # 调用获取页面信息的函数，10次
        try:
            url = start_url + '?start=' + str(25*i)     # 每一页有25本书
            #https://book.douban.com/top250?start=50
            html = GetHTMLText(url)                 # 调用函数，获得主页
            parsePage(infoList,html)       #调用函数，对每个页面进行解析
            #print(infoList)
        except:
            continue
    printBooksList(infoList)            #调用函数，输出信息
    #print(len(infoList))
main()
```

