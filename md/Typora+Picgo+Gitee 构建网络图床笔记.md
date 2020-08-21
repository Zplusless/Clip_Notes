\> 本文由 \[简悦 SimpRead\](http://ksria.com/simpread/) 转码， 原文地址 \[zhuanlan.zhihu.com\](https://zhuanlan.zhihu.com/p/178938338)

**前言**

之前一直在 Typora 上记录自己的笔记，但是发现 markdown 格式的笔记在插入图片时，仅能采用两种方法：1）在线图床，2）本地路径，即图片并不是像 Word 那样集成在文档内的，因此经过一番研究，发现了最新版的 Typora 已经支持在线图床功能，遂写此篇教程帮助后人构建自己的在线图床 markdown 笔记。

**所需软件**
--------

typora

[https://typora.io/](https://link.zhihu.com/?target=https%3A//typora.io/)

picgo

[https://github.com/Molunerfinn/PicGo/releases](https://link.zhihu.com/?target=https%3A//github.com/Molunerfinn/PicGo/releases)

建议选择 2.2.2 正式版本，beta 版本可能会存在不稳定的风险。

![](https://pic4.zhimg.com/v2-be88c425ba401a71e9c91dca74f0d262_b.jpg)![](https://pic4.zhimg.com/v2-be88c425ba401a71e9c91dca74f0d262_r.jpg)

Gitee

由于国内连接 github 时网络偶尔存在不稳定的情况，于是采用了 gitee 作为 github 图床的替代，但整体教程是一样的

[https://gitee.com/](https://link.zhihu.com/?target=https%3A//gitee.com/)

![](https://picb.zhimg.com/v2-daba73811b87533f8f032169d3d11d9a_b.png)![](data:image/svg+xml;utf8,<svg xmlns='http://www.w3.org/2000/svg' width='132' height='46'></svg>)

**具体操作**
--------

主要是分为两部分操作，第一部分是 Typora 的配置，第二部分是 Picgo+Gitee 的在线图床配置

### **Typora 配置**

打开 Typora 后，点击菜单栏 - 文件 - 偏好设置

找到其中的 “图像” 设置，将其设置为如下内容

![](https://pic4.zhimg.com/v2-f374bec8d90d87c2f7683c1133064166_b.jpg)![](https://pic4.zhimg.com/v2-f374bec8d90d87c2f7683c1133064166_r.jpg)

1）**插入图片时...** 下边的选择框内选择**上传图片**

2）勾选上 “**对本地位置的图片应用上述规则**”

3）上传服务选择 **PicGo(app)**

4）将 **PicGo 路径**项设置为本地 PicGo 的安装路径

这样，我们就把 Typora 配置好了，下面我们进行 PicGo+Gitee 的网络图床构建

### **网络图床配置**

首先，安装好 PicGo 之后，我们需要给 PicGo 配置插件以支持 Gitee 图床

**注意**：你必须安装 [Node.js](https://link.zhihu.com/?target=https%3A//nodejs.org/en/) 之后才能安装 PicGo 的插件，因为 PicGo 要使用`npm`来安装插件。

安装好 Nodejs 后，点开左边的**插件设置**一栏，在输入框内输入 “github plus”，如下

![](https://pic2.zhimg.com/v2-270b499aeadae15d014215b32b1204c8_b.jpg)![](https://pic2.zhimg.com/v2-270b499aeadae15d014215b32b1204c8_r.jpg)

点击安装此插件，之后左侧选项栏**图床设置**会多一个 **githubplus**

![](https://picb.zhimg.com/v2-1fd1e0c2ef8c48f1d85a5a04b8566714_b.png)![](data:image/svg+xml;utf8,<svg xmlns='http://www.w3.org/2000/svg' width='160' height='206'></svg>)

接下来我们配置 Gitee 仓库以存储图片

1）进入 [https://gitee.com/](https://link.zhihu.com/?target=https%3A//gitee.com/)，没有账号的话，先注册账号，注册以后登录，新建一个**公开仓库**，名字为 picgo（可以自己起其他名字）

2）点击右上角，进入**设置**，在左侧的**安全设置 - 私人令牌**处生成新令牌。（注意：生成的新令牌只会显示一次，一定要保存好！！！）

我们需要做的如下：

1）回到 picgo，按照如下进行设置

![](https://pic3.zhimg.com/v2-dceba8a3986c7df4dbc3f8cb1e8ca60e_b.jpg)![](https://pic3.zhimg.com/v2-dceba8a3986c7df4dbc3f8cb1e8ca60e_r.jpg)

其中的 repo 为 **UserName / 仓库名称** 格式

branch 填入 master

Token 为刚才在 Gitee 生成的私人令牌，粘贴到这里就行

path 为仓库下用于存储图片的路径，这个可以自行选择

最下边的 origin 部分选择 gitee（默认是 github）

**结束**
------

经过上述操作，我们就把 typora+picgo+gitee 成功配置好了，之后当我们将本地的图片粘贴到 markdown 文档内的时候，typora 会自动将图片上传到刚才我们配置好的 gitee 仓库内，并自动把 markdown 文档内的本地路径转化为 gitee 的图片外链，便于我们以后进行多端访问文档内的图片。

写下你的评论...