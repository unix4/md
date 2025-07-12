---
title: "VSCode终端字体显示"
description: "This post showcases using the markdown admonition feature in Astro Cactus"
publishDate: "12 Jul 2025"
tags: ["vscode"]
---
## 发现
 在使用VSCode终端的时候发现显示不出来该有的图标，是一个问号方框！
 ![image.png](https://roim-picx-9nr.pages.dev/rest/26mYqVK.png)
 在powershell中打开正常显示应该是这样的
 ![image.png](https://roim-picx-9nr.pages.dev/rest/bHgyqVK.png)
 说实话我都忘了什么时候配置的这个玩意（为什么我之前不解决这个问题。。。)
## 解决
好吧，问了一下ChatGPT它说是字体不匹配导致了，把VSCode终端的字体改为和Powershell终端对应的就行了
1.首先打开终端的json
![image.png](https://roim-picx-9nr.pages.dev/rest/WqozqVK.png)
2.然后检索“Font”
![image.png](https://roim-picx-9nr.pages.dev/rest/ohvzqVK.png)
复制字体名
3.打开VSCode设置，检索“terminal.integrated.fontFamily”
然后打开json
![image.png](https://roim-picx-9nr.pages.dev/rest/2CmARVK.png)
填加上字体名就行了
![image.png](https://roim-picx-9nr.pages.dev/rest/dXeaRVK.png)
ctrl+s保存，就会发现终端已经正常显示图标了！
![image.png](https://roim-picx-9nr.pages.dev/rest/rc7aRVK.png)

