# 计算机体系结构基础

这是龙芯团队胡伟武老师等人编写的《计算机体系结构基础》（第三版）的开源版本。本书纸质版本由机械工业出版社发行，可以通过各种常规渠道购买。

## 内容提要

本书由从事微处理器设计的一线科研人员编写而成。作者从微处理器设计的角度出发，充分考虑计算机体系结构的学科完整性，强调体系结构、基础软件、电路和器件的融会贯通。全书共分12章，包括指令系统结构、计算机硬件结构、CPU微结构、并行处理结构、计算机性能分析等主要内容，重点放在作为软硬件界面的指令系统结构，以及包含CPU、GPU、南北桥协同的计算机硬件结构。本书可作为高等学校“计算机体系结构”课程的本科生教材，同时也适合相关专业研究生或计算机技术人员参考阅读。

关于本书内容更多的介绍可以参考[推荐序](https://foxsen.github.io/archbase/%E6%8E%A8%E8%8D%90%E5%BA%8F.html)、[自序](https://foxsen.github.io/archbase/%E8%87%AA%E5%BA%8F.html)、[第三版序](https://foxsen.github.io/archbase/%E7%AC%AC%E4%B8%89%E7%89%88%E5%BA%8F.html)和[前言](https://foxsen.github.io/archbase/%E5%89%8D%E8%A8%80.html)等相关章节。

## 关于本书的开源维护

在第三版的改版过程中，作者们引入了一个创新尝试，试图将本书打造为一本活的教科书。具体来说，我们采用以文本为基础的rmarkdown格式编辑书本内容（采用[bookdown](https://bookdown.org)工具包），用git对其进行版本管理，并在互联网进行开源维护。在相应的网站上，还会提供出版社提供的与纸质版本一致的电子版本，以及相关的参考课件PPT和其他补充资源。我们认为这么做有几个好处：

* 文字、图片和参考课件等素材的开放更方便教学使用。通过开源本书，我们期望能够它得到更广泛的采用，得到更多的批评指正意见，使得它能够更快成熟。
* 方便的版本管理系统有助于及时吸收对本书的勘误和改进。一方面，读者可以通过项目的问题管理系统或者其他渠道反馈问题，被接纳后会立即反映到在线的版本中，不必等待下一次改版印刷周期。另一方面，作者们也可以将之前对由于时间仓促未来得及完善的内容进行补充完善，或者根据产业的发展需求对内容进行适当调整。
* 新的格式能够提供更丰富的表现形式。在rmarkdown文本的基础上，系统可以自动生成HTML、word和PDF等各种格式的发布版本，扩大适用范围。后续还可以利用其中某些格式来实现传统纸质书本无法做到的实时交互等功能。 当然，限于rmarkdown/bookdown目前的表现能力以及作者们对其的应用水平，在线版本生成的发布版本排版细节质量上很可能比不上出版社提供的、与纸质版本一致的原始电子文件，阅读体验上也不能替代纸质版本。有条件的读者仍然可以选择由机械工业出版社出版发行的纸质版本。

由于工具的限制，在线版本和纸质版本的版面效果并非完全一致。目前图表的编号也不一定一一对应，部分纸质书的表可能用图来代替。后续随着一些修订内容的添加，在线版本的文字和纸质版本也会有所差别。

本书内容的开源离不开出版社、龙芯中科技术股份有限公司和作者们的支持，在此表示感谢。出版社提供了精心排版后的电子版本和相应资源文件，并同意开放这些资源。龙芯中科技术股份有限公司提供了在线版本的一份web服务器资源以及部分经费支持。作者们接受了可能的出版收益损失。

本书开源版本也得到了中国科学院大学研究生程轶涵、穆热迪力、王铭剑、徐淮、叶锦鹏（按姓氏拼音顺序）等同学的大力支持，他们协助完成了bookdown格式部分源代码的编辑和校对，在此表示感谢！

## 本书相关信息

本书的官方信息网页参见[本书信息](https://www.loongson.cn/LoongsonLab/OpenAccessLibrary)。

本项目的github actions已经配置为自动生成HTML/PDF/DOCX三种输出格式并部署到github pages。三种格式的链接分别如下：

* [HTML](https://foxsen.github.io/archbase). 在线HTML版本。
* [PDF](https://foxsen.github.io/archbase/bookdown.pdf). PDF版下载链接。
* [DOCX](https://foxsen.github.io/archbase/bookdown.docx). Word版下载链接，其中目录部分需要手工选择下“更新域”才能显示。

机械工业出版社提供的纸质书精排电子版可以从这里获得: [纸质书电子版](https://www.loongson.cn/pdf/computer.pdf)。

## docker环境

虽然github actions已经能够全自动地完成代码编译和部署，不过似乎它的环境不太容易在本地复现。为了方便大家复现我们的工作环境，写了一个简单的Dockerfile(参见docker/Dockerfile)，它安装了能够完整编译本项目代码的相关软件工具。

使用方法：

* 安装docker环境。
* cd docker && sudo docker build -t bookdown .
* docker run -it bookdown /bin/bash，然后在docker环境中可以更新代码，编译代码。例如: cd /opt/archbase; git pull; make

有兴趣的读者可以参考这个环境来编写自己的书籍或者其他文档，然后大家可以切磋具体的使用方法和技巧。 我们也都是bookdown新手，估计有很多用法有改进的空间，期待得到大家的反馈。

## 龙芯体系结构相关参考资源

本书的实例和原理介绍以龙芯体系结构为主。关于龙芯体系结构的信息，可以参考[这里](https://github.com/loongson)。那里的内容包括：

1. 龙芯架构的相关[文档](https://github.com/loongson/LoongArch-Documentation)，如指令集手册、ABI文档、龙芯3A5000处理器手册、龙芯7A1000桥片手册等。
2. 一些龙芯架构的关键基础软件，如[工具链](https://github.com/loongson/build-tools)、[QEMU模拟器](https://github.com/foxsen/qemu-loongarch-runenv)和[内核](https://github.com/loongson/linux/tree/loongarch-next)等。很多软件正在upstream的过程中，相信不久后大部分软件可以直接从社区上游获得。

暂时没有龙芯机器的同学，可以在X86上用交叉编译工具链编译loongarch应用，用qemu模拟运行loongarch程序。后续争取提供一些龙芯云端的开发者账号让大家能在真机上做实验。

## 意见反馈

提供开源版本的一个主要目的是为了更好地收集反馈意见。如果您对本书有任何意见或者建议，欢迎与我们联系。您可以利用github的各种交互功能与我们联系：提交issue、pull request或者私信作者等。

## TODO

后续还有很多需要完善的工作，包括:

* 完善教材内容。例如为正文涉及的一些知识提供更多的参考阅读指引，为部分习题添加必要的上下文交代，修正不够严谨的表述等等。
* 整理和上传相关资料，如纸质版对应的pdf版本、参考课件、习题涉及的一些外部资源和运行环境等。
* 持续完善开源版本的格式和自动生成环境。目前通过github action，对源代码的任何修改推送之后将触发HTML/PDF/DOCX版本的自动编译和部署。我们发现缺省的bookdown环境以及我们用到的一些包还存在一定的不足，导致生成的内容还有些异常，包括部分图表超宽、表格内的换行或者tab键处理不如预期等。其中一些问题已经被整理和集成到部署环境中。其他的遗留问题也会通过修正相关软件包或者更换正文的表达方式来逐步解决。

## License

本书采用[Creative Commons Attribution-NonCommercial 4.0 International Public License](https://creativecommons.org/licenses/by-nc/4.0/legalcode)开源，具体条款可参考LICENSE文件。
