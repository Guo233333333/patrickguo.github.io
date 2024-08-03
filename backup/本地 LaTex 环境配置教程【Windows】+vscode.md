### 安装 LaTex 发行版

LaTex 是基于 TeX 语言拓展的一组宏集（我理解为一个 LaTex 的命令可能集成了多个 TeX 的命令）。  
而不同的人可能会去实现不同的 TeX 宏集，并且都做的十分出色。因此就有不同的 Latex 发行版这一说。  
当前常见的 LaTex 发行版有 [[MiKTeX](https://miktex.org/download)](https://miktex.org/download)、[[TeXLive](https://tug.org/texlive/acquire-netinstall.html)](https://tug.org/texlive/acquire-netinstall.html) 和 [[MacTeX](https://www.tug.org/mactex/mactex-download.html)](https://www.tug.org/mactex/mactex-download.html)，本教程就选择安装 **TeXLive** 作为示例。

#### 下载

- 下载地址 1- [[清华镜像](https://mirrors.tuna.tsinghua.edu.cn/CTAN/systems/texlive/Images/)](https://mirrors.tuna.tsinghua.edu.cn/CTAN/systems/texlive/Images/)
- 下载地址 2 - 阿里云盘

> ![](https://i-blog.csdnimg.cn/blog_migrate/e42766edd1263f913ad61b8fc428e36a.jpeg)

#### 安装

> ![](https://i-blog.csdnimg.cn/blog_migrate/4cc1c78c13845f87d137fae415103bef.png)  
> ![](https://i-blog.csdnimg.cn/blog_migrate/28ecad50f7a3efaa6fdde76dfc319179.png)  
> ![](https://i-blog.csdnimg.cn/blog_migrate/15ffeda8eb5690d0fab13f3a7b4fe761.png)  
> ![](https://i-blog.csdnimg.cn/blog_migrate/b6c266b5255792512dc2000ee8c2e63d.png)

#### 测试

使用命令`latex -v`,`xelatex -v`,`pdflatex -v`验证安装是否成功

> ![](https://i-blog.csdnimg.cn/blog_migrate/151fbc1ec8c95a5cf189c45dcc67548f.png)  
> ![](https://i-blog.csdnimg.cn/blog_migrate/bc89f2f97a9801772c12525f68dd5570.png)

### 安装 Visual Studio Code

Visual Studio Code(VScode) 是微软开源的一款轻量级跨平台编辑器，可以通过安装不同的插件实现高效的代码编辑。

#### 下载

- 下载地址 1- [[官网](https://code.visualstudio.com/#alt-downloads)](https://code.visualstudio.com/#alt-downloads)
- 下载地址 2 - 阿里云盘

> ![](https://i-blog.csdnimg.cn/blog_migrate/652dda9cccd1027bb0ba2bd36e971bbe.png)

#### 安装

> ![](https://i-blog.csdnimg.cn/blog_migrate/6c5614c881008480702ac3f70c8242dd.png)  
> ![](https://i-blog.csdnimg.cn/blog_migrate/45fdd59a65e276f27b1b219348637ba7.png)  
> ![](https://i-blog.csdnimg.cn/blog_migrate/16c277c6782b2e0ca1ad19bd31f93d41.png)

### VScode 中配置 LaTex 编译

VScode 中有一个 LaTex Workshop 插件，可以实现对 LaTex 编辑的支持。

#### 安装 LaTex Workshop 插件

> 未安装插件前的效果:![](https://i-blog.csdnimg.cn/blog_migrate/dc2711087cc90429b2e1bd4dfc504403.png)

##### 在 VScode 的拓展中搜索 LaTex Workshop 插件并安装

> ![](https://i-blog.csdnimg.cn/blog_migrate/6ed61df274014c42f376d24160db9c20.png)  
> ![](https://i-blog.csdnimg.cn/blog_migrate/aff77134ff7ed1511650db1c0e96a790.png)

> 安装后效果：  
> ![](https://i-blog.csdnimg.cn/blog_migrate/dd750bb3c9bbb759d535e281232fc07c.jpeg)  
> 在拓展栏出现了 **TEX** 标志，并且语法出现高亮

#### 配置 LaTex Workshop 插件

为了更好的在 VScode 中使用 LaTex，我们需要对 LaTex Workshop 插件进行一些配置。

##### 在 VScode 中使用快捷键`Ctrl+Shift+P`并在搜索框内输入`Preferences:Open Settings(JSON)`

> ![](https://i-blog.csdnimg.cn/blog_migrate/2a796ec4a99a60c83331d5e2a766e822.jpeg)

##### 添加配置

> ![](https://i-blog.csdnimg.cn/blog_migrate/2a75da1d06d1d447a8df016c965c036f.jpeg)

##### 配置如下

!!! 注意，如果原先的 setting.json 内有配置参数，则需要把下面的配置删除最外层 **{ }** 删除后添加至原先的 **{ }** 内。

```
{
      // Latex workshop

    "latex-workshop.latex.tools": [
      {
        "name": "latexmk",
        "command": "latexmk",
        "args": [
        "-shell-escape",
        "-synctex=1",
        "-interaction=nonstopmode",
        "-file-line-error",
        "-pdf",
        "%DOC%"
        ]
      },
      {
        "name": "xelatex",
        "command": "xelatex",
        "args": [
        "-shell-escape",
        "-synctex=1",
        "-interaction=nonstopmode",
        "-file-line-error",
        "%DOC%"
          ]
      },          
      {
        "name": "pdflatex",
        "command": "pdflatex",
        "args": [
        "-shell-escape",
        "-synctex=1",
        "-interaction=nonstopmode",
        "-file-line-error",
        "%DOC%"
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
        ]
      },
      {
        "name": "pdflatex",
        "tools": [
            "pdflatex"
        ]
      },
      {
        "name": "latexmk",
        "tools": [
        "latexmk"
        ]
      },
      {
        "name": "pdflatex -> bibtex -> pdflatex*2",
        "tools": [
        "pdflatex",
        "bibtex",
        "pdflatex",
        "pdflatex"
        ]
      },
      {
        "name": "xelatex -> bibtex -> xelatex*2",
        "tools": [
        "xelatex",
        "bibtex",
        "xelatex",
        "xelatex"
        ]
      }],
    "latex-workshop.view.pdf.viewer": "tab",  
    "latex-workshop.latex.autoBuild.run": "never",
    "latex-workshop.latex.autoClean.run": "onBuilt",
    "latex-workshop.latex.clean.fileTypes": [
        "chapters/*.aux",
        "misc/*.aux",
        "*.aux",
        "*.bbl",
        "*.blg",
        "*.idx",
        "*.ind",
        "*.lof",
        "*.lot",
        "*.out",
        "*.toc",
        "*.acn",
        "*.acr",
        "*.alg",
        "*.glg",
        "*.glo",
        "*.gls",
        "*.ist",
        "*.fls",
        "*.log",
        "*.fdb_latexmk"
      ],
    "latex-workshop.message.update.show": false,
    "editor.fontSize": 18,
    "files.autoSave": "afterDelay",
    "window.zoomLevel": 1
 }
```

##### 配置属性的一些解释

> 1. `latex-workshop.latex.tools` 在编译过程中需要使用到的编译命令，默认就行，不需要进行修改
> 2. `latex-workshop.latex.recipes` 此串代码是对编译链进行定义，其中 name 是标签，也就是出现在工具栏中的链名称；tools 是 name 标签所对应的编译顺序，其内部编译命令来自上文 latex-workshop.latex.tools 中内容
> 3. `latex-workshop.latex.autoClean.run` 定义在编译过程中是否需要清除过程文件
> 4. `latex-workshop.latex.clean.fileTypes` 配合上一个配置使用，表示需要清除的文件类型

##### 编译链的解释

一般我们在使用 LaTex 写文献的时候，会涉及到论文引用这方面的问题，而一般的方式是使用 **BibTex**  
如果说我们的内容不包含文献，其实只用 **xelatex** 或 **pdflatex** 就足够将文本编译成 pdf 文件了  
但一般我们使用 LaTex 的目的还是写论文，因此肯定逃不开使用 **BibTex**，而使用 **BibTex** 就需要多次编译  
而一般的流程就是 **xelatex → \to → bibtex → \to → xelatex → \to → xelatex** 或者 **pdflatex → \to → bibtex → \to → pdflatex → \to → pdflatex**  
具有的过程在[[这篇文章](https://blog.csdn.net/huitailangyz/article/details/99685683)](https://blog.csdn.net/huitailangyz/article/details/99685683)中有介绍，有兴趣可以看一下。  
`Tip:` **xelatex** 或 **pdflatex** 的区别在于如果内容中有中文，需要引入中文支持的包并只能使用 **xelatex** 编译

#### 使用 LaTex Workshop 插件

进行上述配置以后，我们就可以在 VScode 拓展面板看到我们所配置的结果

> 在 **COMMANDS** 中有五种不同的编译链，对应我们在`latex-workshop.latex.recipes`下的配置  
> SNIPPET VIEW 中提供了 LeTax 的公式编辑帮助，点击其中的符号就可以在 tex 文本中直接添加  
> ![](https://i-blog.csdnimg.cn/blog_migrate/15c349291c0d070c19d7aa778bcda04e.jpeg)

##### 使用定义好的编译链编译. tex 文件

示例的 CVPR 模板可以从我的阿里云下载：下载地址  
首先选中并打开需要编译的. tex 文件

> ![](https://i-blog.csdnimg.cn/blog_migrate/7fa83ad74beca33cd3362477daba0ebc.jpeg)

然后打开 VScode 拓展栏中的 TEX  
在 **COMMANDS** 选择 **xelatex → \to → bibtex → \to → xelatex → \to → xelatex** 或者 **xelatex → \to → bibtex → \to → xelatex → \to → xelatex**  
单击后，tex 文件便会被编译成 pdf

> ![](https://i-blog.csdnimg.cn/blog_migrate/ab483fff91225fc87b54fb1bca4965b5.jpeg)

编译后效果

> ![](https://i-blog.csdnimg.cn/blog_migrate/1abca978aecb17aed34ccf7c51553b7e.jpeg)

### LaTex 基础

#### 文档的基本结构

一般的文本结构如下，标识是以 `\`开头的  
在`\begin{document}`后，在标识与标识之间填写的内容会属于开始的标识  
例如，**Zzbro1** 属于第一节的内容，**Zzbro1~1** 属于第一节的第一子节

```
%文档的类型
\documentclass{article}
%导入需要用的宏包，不限制数量
\usepackage{amsmath}

%内容开始-只有以下内容会出现在最终的pdf文档中
\begin{document}
%节的标识
\section{First}
Zzbro1
%子节的标识
\subsection{One}
Zzbro1~1
\subsection{Two}
Zzbro1~2
\section{Seconde}
Zzbro2
\section{Third}
Zzbro3

\end{document}
%内容结束
```

使用 **xelatex** 或 **pdflatex** 进行编译，结果如下

> ![](https://i-blog.csdnimg.cn/blog_migrate/0ff689056aef6d1604e3c19668f03ff5.jpeg)

#### 向文档中插入图片

这个时候需要导入 **graphicx** 宏包来支持插入图片，使用命令`\usepackage{graphicx}`  
插入图片的基本结构如下

```
%图片的标识
\begin{figure}
    %居中
    \begin{center}
        %插入图片，{}内是图片的名字，！！！路径需要填写以tex文件所在路径的相对位置
        \includegraphics{clock.png}
    \end{center}
    %图片描述信息，一般论文就是图名和描述图的内容
    \caption{
        A clock
    }
    %为这张图打上一个标签，方便在其他地方引用
    \label{fig:overview}
\end{figure}
```

带图片的示例文档

```
%文档的类型
\documentclass{article}
%导入需要用的宏包，不限制数量
\usepackage{amsmath}
\usepackage{graphicx}
%内容开始-只有以下内容会出现在最终的pdf文档中
\begin{document}
%图片的标识
\begin{figure}
    %居中
    \begin{center}
        %插入图片，{}内是图片的名字
        \includegraphics{clock.png}
    \end{center}
    %图片描述信息，一般论文就是图名和描述图的内容
    \caption{
        A clock
    }
    %为这张图打上一个标签，方便在其他地方引用
    \label{fig:overview}
\end{figure}
%节的标识
\section{First}
Zzbro1
%子节的标识
\subsection{One}
Zzbro1~1
\subsection{Two}
Zzbro1~2
\section{Seconde}
Zzbro2
\section{Third}
Zzbro3

\end{document}
%内容结束
```

使用 **xelatex** 或 **pdflatex** 进行编译，结果如下

> ![](https://i-blog.csdnimg.cn/blog_migrate/65bd17668f2ba1a292abb2da971e42f0.jpeg)

#### 向文档中插入表格

表格内容的基本格式，其中`\begin{tabular}`后的`lc`表示第一列内容左对齐，第二列内容居中对齐

```
%表的标识
\begin{table}
    %居中
    \centering
    %表的内容开始标识
    \begin{tabular}{lc}
        Method & Frobnability\\
        Ours v0 & Frumpy \\
        Ours v1 & Frobbly \\
        Ours & Makes one's heart Frob\\
    \end{tabular}
    %表描述信息，一般论文就是表名和描述表的内容
    \caption{
        \textbf{Ablations} -- our decisions are well justified.
    }
    %为这个表打上一个标签，方便在其他地方引用
    \label{tab:ablations}
\end{table}
```

添加至文档 **\begin{document}** 之后使用 **xelatex** 或 **pdflatex** 进行编译，结果如下：

> ![](https://i-blog.csdnimg.cn/blog_migrate/233e9ffe15881999a68d552686ed9d0b.png)

#### 向文档中插入公式

文档中使用公式需要使用`\usepackage{amsmath}`命令添加 **amsmath** 包  
公式嵌入的两种方式基础结构如下

```
% 行内嵌入公式，使用 $ $ 标识公式的开始与结束 
Zzbro1~1$N=2022$
% 行间嵌入公式，使用如下标识
\begin{equation}
    \int_{a}^{b}  \,dx 
\end{equation}
```

使用 **xelatex** 或 **pdflatex** 进行编译，结果如下：

> ![](https://i-blog.csdnimg.cn/blog_migrate/6f54c2573fc1471867988d8fa203c0eb.jpeg)

#### 引用文本内容

我们在图片和表的结构中都添加了`\label{}`标识，那么对于添加了这些标识的内容，我们可以在文档的任意部分进行引用  
但在**单命令**编译链编译过程中，我们需要修改配置文件的`latex-workshop.latex.clean.fileTypes`，将`"*.aux",`使用`//`注释掉  
示例

```
% 使用\ref{}就可以引用被打标签的部分
\section{Seconde}
Zzbro2\ref{fig:overview}
\section{Third}
Zzbro3\ref{tab:ablations}
```

使用 **xelatex** 或 **pdflatex** 进行**两次**编译，结果如下：

> ![](https://i-blog.csdnimg.cn/blog_migrate/c52e5473dcde24e2270d5463164f721a.jpeg)

#### 小结

使用 LaTex 进行写作时，用`\begin{} \end{}` 这样的结构所标识的内容会自动编号，例如 **Figure 1**、**Table 1** 和公式的编号 **(1)**

##### 文档的示例结构如下

```
%文档的类型
\documentclass{article}
%导入需要用的宏包，不限制数量
\usepackage{amsmath}
\usepackage{graphicx}
\usepackage{booktabs}

%内容开始-只有以下内容会出现在最终的pdf文档中
\begin{document}
%图片的标识
\begin{figure}
    %居中
    \begin{center}
        %插入图片，{}内是图片的名字
        \includegraphics{clock.png}
    \end{center}
    %图片描述信息，一般论文就是图名和描述图的内容
    \caption{
        A clock
    }
    %为这张图打上一个标签，方便在其他地方引用
    \label{fig:overview}
\end{figure}
%节的标识
\section{First}
Zzbro1
%子节的标识
\subsection{One}
% 行内嵌入公式，使用 $ $ 标识公式的开始与结束 
Zzbro1~1$N=2022$

% 行间嵌入公式，使用如下标识
\begin{equation}
    \int_{a}^{b}  \,dx 
\end{equation}

\subsection{Two}
Zzbro1~2
%表的标识
\begin{table}
    %居中
    \centering
    %表的内容开始标识
    \begin{tabular}{@{}lc@{}}
        Method & Frobnability\\
        Ours v0 & Frumpy \\
        Ours v1 & Frobbly \\
        Ours & Makes one's heart Frob\\
    \end{tabular}
    %表描述信息，一般论文就是表名和描述表的内容
    \caption{
        \textbf{Ablations} -- our decisions are well justified.
    }
    %为这个表打上一个标签，方便在其他地方引用
    \label{tab:ablations}
\end{table}

\section{Seconde}
%引用\ref{}
Zzbro2 - fig\ref{fig:overview}
\section{Third}
Zzbro3 - tab\ref{tab:ablations}

\end{document}
%内容结束
```

### LaTex 中使用 bib 管理引用文献

可以使用 BibTeX 来管理引用文献我认为是 LaTex 最最方便的功能之一！  
我们需要在 tex 文件的同级目录下新建一个 bib 文件即可，示例中新建的文件为 **test.bib**

> ![](https://i-blog.csdnimg.cn/blog_migrate/4388bf630cb3423efb98b5000ebaceb4.jpeg)

#### 查找文献的 BibTeX

我们以查找《Deep Residual Learning for Image Recognition》这篇论文的 BibTex 为例

##### [[百度学术](https://xueshu.baidu.com/)](https://xueshu.baidu.com/)

> ![](https://i-blog.csdnimg.cn/blog_migrate/40b09c1d025b3b522cf9ac5133c96cca.jpeg)  
> ![](https://i-blog.csdnimg.cn/blog_migrate/4b30c12cd77bac86a536e95c7924476d.jpeg)

##### [[谷歌学术](https://scholar.google.com/schhp?hl=zh-CN&as_sdt=0,5)](https://scholar.google.com/schhp?hl=zh-CN&as_sdt=0,5)

> ![](https://i-blog.csdnimg.cn/blog_migrate/32a51996f53690fd2d8e407bfb88adcd.jpeg)  
> ![](https://i-blog.csdnimg.cn/blog_migrate/de1f5d51d9d3d564417f63666798f558.jpeg)

##### DBLP

> ![](https://i-blog.csdnimg.cn/blog_migrate/5b5ff756a6838a7c102d437e6babc9ef.jpeg)  
> ![](https://i-blog.csdnimg.cn/blog_migrate/1cc566ca29197d0973476399cad0f340.jpeg)

#### 在文档中插入文献引用

我们在不同数据库所查找到的 BibTex 文件可能是不一样的，但都包含了论文的基础信息  
其中，最需要注意的地方就是 BibTex 第一行 **{** 和 **,** 之间的**简称**内容，例如下面的 **2016Deep、He_2016_CVPR、DBLP:conf/cvpr/HeZRS16**  
我们在文档中引用文献时，使用的就只是这里定义的**简称**，类似于标签的形式。

```
%百度学术
@article{2016Deep,
  title={Deep Residual Learning for Image Recognition},
  author={ He, K.  and  Zhang, X.  and  Ren, S.  and  Sun, J. },
  journal={IEEE},
  year={2016},
}
%谷歌学术
@InProceedings{He_2016_CVPR,
author = {He, Kaiming and Zhang, Xiangyu and Ren, Shaoqing and Sun, Jian},
title = {Deep Residual Learning for Image Recognition},
booktitle = {Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition (CVPR)},
month = {June},
year = {2016}
}
%DBLP
@inproceedings{DBLP:conf/cvpr/HeZRS16,
  author    = {Kaiming He and
               Xiangyu Zhang and
               Shaoqing Ren and
               Jian Sun},
  title     = {Deep Residual Learning for Image Recognition},
  booktitle = {2016 {IEEE} Conference on Computer Vision and Pattern Recognition,
               {CVPR} 2016, Las Vegas, NV, USA, June 27-30, 2016},
  pages     = {770--778},
  publisher = {{IEEE} Computer Society},
  year      = {2016},
  url       = {https://doi.org/10.1109/CVPR.2016.90},
  doi       = {10.1109/CVPR.2016.90},
  timestamp = {Wed, 16 Oct 2019 14:14:50 +0200},
  biburl    = {https://dblp.org/rec/conf/cvpr/HeZRS16.bib},
  bibsource = {dblp computer science bibliography, https://dblp.org}
}
```

我们选择上述谷歌学术的 BibTex 填入 **text.bib** 文件中，并在 text.tex 文档中进行引用  
其中需要注意的是，我们引用 BibTex 中的简称需要使用 `\cite{}` 命令，并且需要在文档的尾部设置引用的类型

##### 文档中引用模板的格式

```
% 引用BibTex中的简称需要使用 \cite{} 命令
\documentclass{article}

\begin{document}


\section{First}
Zzbro1

\subsection{One}

Zzbro1~1

Reference here\cite{He_2016_CVPR}

\subsection{Two}
Zzbro1~2

\section{Seconde}
Zzbro2
\section{Third}
Zzbro3


%BibTex 样式
{   
    %设置BibTex所在的文件，我们这里是test.bib 可简写为test
    \bibliography{test.bib}
    %设置BibTexde的样式文件，我们这里是ieee_fullname.bst 可简写为ieee_fullname
    \bibliographystyle{ieee_fullname}
}

\end{document}
```

使用 **pdflatex → \to → bibtex → \to → pdflatex → \to → pdflatex** 编译链编译，结果如下：

> ![](https://i-blog.csdnimg.cn/blog_migrate/a0ffbea49d421fd4c1545e4b22ba5508.jpeg)

### LaTex 使用模板写作样例

在掌握了上述 LaTex 基础后，使用模板写作相信大家就可以手到擒来了，这里以 CVPR 的模板为例，模板来源于 overleaf

#### 模板结构

![](https://i-blog.csdnimg.cn/blog_migrate/c283e6fd7b6d6c23c3c2ec47359a8215.png)

#### 修改步骤

1. 在 main.tex 中去掉不需要的内容
2. 在 main.bib 中将自己需要的参考文献 BibTex 进行添加
3. 使用 **pdflatex → \to → bibtex → \to → pdflatex → \to → pdflatex** 编译链编译

#### 修改示例

##### 在 main.tex 中删除不需要的内容

> ![](https://i-blog.csdnimg.cn/blog_migrate/507e3b525df46d2c961eeae20916d53d.jpeg)

##### 修改不同章节的内容

> ![](https://i-blog.csdnimg.cn/blog_migrate/77b11f1b94e7f150f0d5875cb20633b8.jpeg)

##### 添加参考文献并在正文中引用

> 这里将该条引用的简称改为了 **ResNet**，因此在论文中就需要以 `\cite{ResNet}`来引用  
> ![](https://i-blog.csdnimg.cn/blog_migrate/183f8398500f918ddb1351a86f1111d5.jpeg)  
> ![](https://i-blog.csdnimg.cn/blog_migrate/7be5b87c5df8bc69fdd4c574f4e2a6f3.jpeg)

##### 使用 **pdflatex → \to → bibtex → \to → pdflatex → \to → pdflatex** 编译链编译

> 这里使用 **pdflatex → \to → bibtex → \to → pdflatex → \to → pdflatex** 编译链，因为存在了 bib 文件  
> 至于你可能会问为什么不用 **xelatex → \to → bibtex → \to → xelatex → \to → xelatex**，这里可能会报错，也可能不报错。但，**只要能编译成功就不要再纠结用哪个啦**~  
> 还需要将 main.tex 中的`\usepackage[pagenumbers]{cvpr}` 和`\bibliographystyle{ieee_fullname}` 改一下路径  
> 修改为`\usepackage[pagenumbers]{cvpr22/cvpr}` 和`\bibliographystyle{cvpr22/ieee_fullname}`  
> ![](https://i-blog.csdnimg.cn/blog_migrate/26ecc2470da087aca119945f707a26c8.jpeg)

### 参考

[[TeX 引擎、格式、发行版之介绍](https://www.latexstudio.net/archives/51537.html)](https://www.latexstudio.net/archives/51537.html)  
[[Visual Studio Code (vscode) 配置 LaTeX](https://zhuanlan.zhihu.com/p/166523064)](https://zhuanlan.zhihu.com/p/166523064)