> 本文由 [[简悦 SimpRead](http://ksria.com/simpread/)](http://ksria.com/simpread/) 转码， 原文地址 [[blog.csdn.net](https://blog.csdn.net/Ray_yep/article/details/140066059)](https://blog.csdn.net/Ray_yep/article/details/140066059)

介绍

[[overleaf](https://so.csdn.net/so/search?q=overleaf&spm=1001.2101.3001.7020)](https://so.csdn.net/so/search?q=overleaf&spm=1001.2101.3001.7020) 已经成了大家编写 LaTeX 的利器，但也有一部分朋友习惯用 vscode 编写 LaTeX，因为 vscode 里面的 copilot 真的非常好用，那有没有办法把二者结合起来？[vscode](https://so.csdn.net/so/search?q=vscode&spm=1001.2101.3001.7020) 里面的插件 **Overleaf Workshop** 就非常好用。

![](https://img-blog.csdnimg.cn/direct/5d94bde62a124ada88287b0fdcd59d54.png)

配置流程

如何创建 overleaf 和在 [vscode](https://so.csdn.net/so/search?q=vscode&spm=1001.2101.3001.7020) 里面配置 LaTeX 这里就不说了，只说怎么把二者联动起来。

### 安装插件 Overleaf Workshop

1. 打开扩展：商店，如 **1**
  
2. 在扩展：商店 中搜索 Overleaf Workshop，然后下载，如 **2**
  
3. 下载完成后会有 overleaf 的表示出现，如 **3**
  

![](https://img-blog.csdnimg.cn/direct/6b4ed490f6064e4394b7820a7cd61105.png)

### 配置

1. 打开 overleaf 图标，如 **1**
  
2. 点击左上角 **+** 号，进行配置，如 **2**
  
3. 输入 overleaf 的网址 https://www.overleaf.com/ 如 **3** ，然后 回车
  

![](https://img-blog.csdnimg.cn/direct/868c44399051478daf4426374433f278.png)

4. 出现 overleaf 的网址后点击右上角登入，如 **4**
  
5. 点击 "**Login with Cookies**"，如 **5**
  

 ![](https://img-blog.csdnimg.cn/direct/e80a0f4e5cee4a7e8b9d9e2285bd080a.png)

6. 在输入框中输入 Cookies 即可，获取 Cookies 的方式见下节。完成后就能联动成功了！

![](https://img-blog.csdnimg.cn/direct/ac0eacae248845d0bd08225be128bca3.png)

### Cookies 获取

 1. 登入 overleaf 后进入首页

![](https://img-blog.csdnimg.cn/direct/ffe2296376e1410e8901d2297cafe5f5.png)

2. 在 overleaf 首页中进入**开发人员工具**，例如 Edge 浏览器中为 **右上角 ··· → 更多工具 → 开发人员工具**

 ![](https://img-blog.csdnimg.cn/direct/b4836a96ca7b4c878d42a195cea7eacb.png)

3. 进入后 点击 **网络 ,** 一两秒后进行刷新（**Ctrl + R**）

![](https://img-blog.csdnimg.cn/direct/9cf9e0b841454fc292a270e2207152f8.png)

4. 左上角查询 **project** ，然后点击 project

![](https://img-blog.csdnimg.cn/direct/5b8ded8c45d343248523dfc271c8f0e4.png)

5. 找到 **Cookie**，并且 **仅复制 over_session2 开头的一段，**这就是我们需要的 Cookie