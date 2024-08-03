> 本文由 [[简悦 SimpRead](http://ksria.com/simpread/)](http://ksria.com/simpread/) 转码， 原文地址 [[www.cnblogs.com](https://www.cnblogs.com/hanlulu1998/p/12210589.html)](https://www.cnblogs.com/hanlulu1998/p/12210589.html)

> **Anaconda 指的是一个开源的 Python 发行版本，其包含了 conda、Python 等 180 多个科学包及其依赖项。当你尝试 pip install xxx 时出现各种意外和依赖问题，那么 conda 就是一方良药。可以让你轻松的安装各种库并处理各种依赖问题。**

Anaconda 安装

**可以从官网下载，不过服务器在国外，所以很慢。推荐使用国内镜像网站：清华大学开源镜像站：`https://mirrors.tuna.tsinghua.edu.cn/anaconda/archive/`，下载后一直 next 下去安装完成即可，安装位置可以自定义。可以自己勾选`add to path`添加系统环境变量, 或者自己安装完成后手动添加。（没有添加就不能在控制台进行命令操作）**

Anaconda 换源

**由于服务器在国外，所以更新下载很慢，建议换源到国内镜像源，在 cmd 控制台或者 powershell 下输入命令即可**

**清华 anaconda 镜像：**

```
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/# 设置搜索时显示通道地址conda config --set show_channel_urls yes
```

**conda 额外库:**

```
# pytorchconda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/pytorch/# 安装时PyTorch，官网给的安装命令需要去掉最后的-c pytorch，才能使用清华源# conda-forgeconda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge/# msys2conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/msys2/# biocondaconda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/bioconda/# menpoconda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/menpo/# 设置搜索时显示通道地址conda config --set show_channel_urls yes
```

> **额外库都是第三方提供的，非 anaconda 官方的，建议没有特殊需要直接使用稳定的官方库。**

**中科大 anaconda 镜像：**

```
conda config --add channels https://mirrors.ustc.edu.cn/anaconda/pkgs/main/conda config --add channels https://mirrors.ustc.edu.cn/anaconda/pkgs/free/conda config --add channels https://mirrors.ustc.edu.cn/anaconda/cloud/conda-forge/conda config --add channels https://mirrors.ustc.edu.cn/anaconda/cloud/msys2/conda config --add channels https://mirrors.ustc.edu.cn/anaconda/cloud/bioconda/conda config --add channels https://mirrors.ustc.edu.cn/anaconda/cloud/menpo/conda config --set show_channel_urls yes
```

> **国内源也是会挂的，之前清华就挂过，后来又活了，腾讯挂了就直接死了，一旦出现一直连接失败问题就可以换回来了**

```
换回默认源：conda config --remove-key channels
```

Anaconda 更新

1.点击Anaconda Prompt
2.输入命令：
conda update conda ——等待更新完，然后输入以下命令，这个较快
conda create -n py34 python=3.4 anaconda ——等待更新完，然后输入以下命令。（因为要把python3.4的相关包下载下来，所以比较慢，请耐心等待）
activate py34