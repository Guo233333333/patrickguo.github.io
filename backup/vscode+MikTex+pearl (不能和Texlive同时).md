> 本文由 [[简悦 SimpRead](http://ksria.com/simpread/)](http://ksria.com/simpread/) 转码， 原文地址 [[blog.csdn.net](https://blog.csdn.net/DrGuCoding/article/details/123523407)](https://blog.csdn.net/DrGuCoding/article/details/123523407)

#### 文章目录

- - - [[注意：本文所提内容均安装在 Win10 系统下](https://github.com/Guo233333333/patrickguo.github.io/issues/new#Win10_1)](#Win10_1)
    - [[1. 安装 Latex 程序 MiKTex](https://github.com/Guo233333333/patrickguo.github.io/issues/new#1_LatexMiKTex_2)](#1_LatexMiKTex_2)
    - - [[1.1 下载 MiKTex](https://github.com/Guo233333333/patrickguo.github.io/issues/new#11_MiKTex_4)](#11_MiKTex_4)
      - [[1.2 添加环境变量 Path：将安装的 MiKTex 的 bin 文件夹，添加到环境变量 path 中。](https://github.com/Guo233333333/patrickguo.github.io/issues/new#12_PathMiKTexbinpath_11)](#12_PathMiKTexbinpath_11)
    - [[2. 安装 Perl](https://github.com/Guo233333333/patrickguo.github.io/issues/new#2_Perl_17)](#2_Perl_17)
    - [[3. 安装 VS Code](https://github.com/Guo233333333/patrickguo.github.io/issues/new#3_VS_Code_35)](#3_VS_Code_35)
    - [[4. 在 VS Code 中运行 Tex 文件生成 PDF](https://github.com/Guo233333333/patrickguo.github.io/issues/new#4_VS_CodeTexPDF_46)](#4_VS_CodeTexPDF_46)
    - [[创作日期：2022 年 3 月 16 日](https://github.com/Guo233333333/patrickguo.github.io/issues/new#2022316_47)](#2022316_47)

#### 注意：本文所提内容均安装在 [[Win10 系统](https://so.csdn.net/so/search?q=Win10%E7%B3%BB%E7%BB%9F&spm=1001.2101.3001.7020)](https://so.csdn.net/so/search?q=Win10%E7%B3%BB%E7%BB%9F&spm=1001.2101.3001.7020)下

#### 1. 安装 [[Latex](https://so.csdn.net/so/search?q=Latex&spm=1001.2101.3001.7020)](https://so.csdn.net/so/search?q=Latex&spm=1001.2101.3001.7020) 程序 MiKTex

关于 Windows 下使用 TeXLive 还是 MikTex，可参考[[科学网](https://blog.sciencenet.cn/blog-478347-1215384.html)](https://blog.sciencenet.cn/blog-478347-1215384.html)，“Texlive 包比较全，Miktex 占用空间比较小，遇到需要的包需要在线下载。所以，硬盘空间比较充足的，网络不太方便的电脑，可以选择 Texlive，反之硬盘空间小，一直保持网络链接的可以选择 Miktex。我一直用 MiKtex，相对比较灵活小巧。”

##### 1.1 下载 MiKTex

在 MiKTex 官网下载安装包：[https://miktex.org/download](https://miktex.org/download)  
官网有点慢，提供一个百度网盘链接（Win10 64 位 2022 年 3 月 16 日版本）  
链接：https://pan.baidu.com/s/10MYlJtJ2YQAZaCYgzYFZEA  
提取码：hvqp  
可以自己选择安装目录，为了给 C 盘留一些空间，就安装到了 D 盘。

##### 1.2 添加环境变量 Path：将安装的 MiKTex 的 [[bin 文件](https://so.csdn.net/so/search?q=bin%E6%96%87%E4%BB%B6&spm=1001.2101.3001.7020)](https://so.csdn.net/so/search?q=bin%E6%96%87%E4%BB%B6&spm=1001.2101.3001.7020)夹，添加到环境变量 path 中。

**MiKTex 的 bin 文件夹地址**：安装目录 \ miktex\bin\x64，例如 D:\Program Files\MiKTeX\miktex\bin\x64。或者可以通过开始（win 键）里的 MiKTex Console，点击右键选择 “更多” 里的“打开文件位置”，从而找到原始路径。

**将路径添加到环境变量 Path 中**：右键 “此电脑” → “属性” → “高级系统设置” → “高级” 菜单下的 “环境变量”，选择“系统变量” 下的变量 “Path” 点击 “编辑” → “新建” 并将 MiKTex 的 bin 文件地址（上述路径）粘贴到此处。

#### 2. 安装 Perl

通过官网 [https://www.perl.org/get.html#win32](https://www.perl.org/get.html#win32) 安装：

![](https://i-blog.csdnimg.cn/blog_migrate/d75659888963263b8406db802cd6fb6b.png)  
在 “命令提示符”command 中，粘贴以下文字自动下载安装 perl 到 C 盘。

```
powershell -Command "& $([scriptblock]::Create((New-Object Net.WebClient).DownloadString('https://platform.activestate.com/dl/cli/713293699.1647403381_pdli01/install-latest.ps1'))) -c'state activate --default HGperl/Perl-5.34.0-Windows'"
```

Perl 安装完成可以在 “命令提示符”command 中输入

```
latexmk --version
```

得到如下提示则为安装成功。

```
Latexmk, John Collins, 20 November 2021. Version 4.76
```

#### 3. 安装 VS Code

官网下载：[https://code.visualstudio.com/](https://code.visualstudio.com/)  
百度网盘（Win10 64 位 2022 年 3 月 16 日版本）  
链接：https://pan.baidu.com/s/1xgNLJOV0Ry6XwdBbtasD-A  
提取码：8wpf

[[XeLatex 参考](https://mp.weixin.qq.com/s?__biz=MzI5MDI0ODEyNg==&mid=2247483750&idx=1&sn=f420aa6427e8a97b840fdabc473a6a01&chksm=ec2385b7db540ca16c369e560069eb4fd2070c6c112fcf76b4ad3346b815cf65bd49182eb752&mpshare=1&scene=1&srcid=&sharer_sharetime=1583150851810&sharer_shareid=d4bad27b7c193c89829e4b88500ddaa3&key=319ea6b0e73c8768b8eab405f52cc89f8f210f5bcbaff03642bc42f70d08d3278c27fbb7822a01ad902c59a409697039a914afdb65c8b07578cd0c5b51f07bf13927ac404b15c203771959f00970950e&ascene=1&uin=MTgxNzM5MjIyNA%3D%3D&devicetype=Windows+10&version=62080079&lang=zh_CN&exportkey=AVMUEk2ansz%2B4XY5aceI%2Fas%3D&pass_ticket=FyB7qu%2Bm9yTy8UywTToOau5gRVKwoaGtbJ9qAyEuJdSemZx7ySdqKR2%2BMtt0SQtS)](https://mp.weixin.qq.com/s?__biz=MzI5MDI0ODEyNg==&mid=2247483750&idx=1&sn=f420aa6427e8a97b840fdabc473a6a01&chksm=ec2385b7db540ca16c369e560069eb4fd2070c6c112fcf76b4ad3346b815cf65bd49182eb752&mpshare=1&scene=1&srcid=&sharer_sharetime=1583150851810&sharer_shareid=d4bad27b7c193c89829e4b88500ddaa3&key=319ea6b0e73c8768b8eab405f52cc89f8f210f5bcbaff03642bc42f70d08d3278c27fbb7822a01ad902c59a409697039a914afdb65c8b07578cd0c5b51f07bf13927ac404b15c203771959f00970950e&ascene=1&uin=MTgxNzM5MjIyNA%3D%3D&devicetype=Windows+10&version=62080079&lang=zh_CN&exportkey=AVMUEk2ansz%2B4XY5aceI%2Fas%3D&pass_ticket=FyB7qu%2Bm9yTy8UywTToOau5gRVKwoaGtbJ9qAyEuJdSemZx7ySdqKR2%2BMtt0SQtS)

#### 4. 在 VS Code 中运行 Tex 文件生成 PDF

#### 创作日期：2022 年 3 月 16 日