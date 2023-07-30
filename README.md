<!--
 *  =======================================================================
 *  ····Y88b···d88P················888b·····d888·d8b·······················
 *  ·····Y88b·d88P·················8888b···d8888·Y8P·······················
 *  ······Y88o88P··················88888b·d88888···························
 *  ·······Y888P··8888b···88888b···888Y88888P888·888·88888b·····d88b·······
 *  ········888······"88b·888·"88b·888·Y888P·888·888·888·"88b·d88P"88b·····
 *  ········888···d888888·888··888·888··Y8P··888·888·888··888·888··888·····
 *  ········888··888··888·888··888·888···"···888·888·888··888·Y88b·888·····
 *  ········888··"Y888888·888··888·888·······888·888·888··888··"Y88888·····
 *  ·······························································888·····
 *  ··························································Y8b·d88P·····
 *  ···························································"Y88P"······
 *  =======================================================================
 * 
 *  -----------------------------------------------------------------------
 * Author       : 焱铭
 * Date         : 2023-07-29 19:56:59 +0800
 * LastEditTime : 2023-07-30 15:09:04 +0800
 * Github       : https://github.com/YanMing-lxb/
 * FilePath     : \YM-VSCode-Configurations-for-LaTeX\README.md
 * Description  : 
 *  -----------------------------------------------------------------------
 -->

# YM VSCode Configurations for LaTeX
---

该项目旨在帮助想要使用LaTeX的老师同学们在VSCode中快速的配置好LaTeX，成功实现LaTeX的编译。

## LaTeX 本地部署
### TeX 基本环境

需要在电脑上安装任意一种 TeX 环境，如[TeXLive](http://mirror.ctan.org/systems/texlive/Images/)、[MacTeX](https://www.tug.org/mactex/mactex-download.html)和[MiKTeX](https://miktex.org/download)（以上环境都自动带有 XeLaTeX 引擎，但是不推荐 CTeX），安装有 SimSun 和 SimHei 字体（其实就是宋体和黑体）以及 Times New Roman 英文字体。在 MacOS 系统下编译会自动识别操作系统，使用 Songti SC 和 STHeiti 字体，但需要启用`--shell-escape`编译选项。

TeX环境安装教程：
1. [MiKTeX安装教程](https://github.com/YanMing-lxb/YM-VSCode-Configurations-for-LaTeX/blob/main/Docs/MiKTeX%E5%AE%89%E8%A3%85%E6%95%99%E7%A8%8B.md);



### Visual Code Studio 编辑器

> ps: 推荐使用 Visual Code Studio（VSCode）编辑器。

配置VSCode编辑器：
1. VSCode 中安装 LaTeX Workshop 插件；
2. [LaTeX Workshop配置说明](https://github.com/YanMing-lxb/YM-VSCode-Configurations-for-LaTeX/blob/main/Docs/LaTeX-Workshop%E9%85%8D%E7%BD%AE%E8%AF%B4%E6%98%8E.md)；

### LaTeXMK配置

> ps: 推荐使用LaTeXMK进行自动编译。

LaTeXMK的相关配置如下：
1. [LaTeXMK配置说明](https://github.com/YanMing-lxb/YM-VSCode-Configurations-for-LaTeX/blob/main/Docs/LaTeXMK%E9%85%8D%E7%BD%AE%E8%AF%B4%E6%98%8E.md)；
2. 如果在 Windows 平台下使用 MiKTeX 还需要安装[Perl 语言解释器](http://strawberryperl.com/)，方可使用 latexmk 进行编译；

### LaTeX 转 Word

> ps: 通过Pandoc实现格式的转换，该命令仅供参考。

LaTeX 转 Word 命令：
1. [LaTeX 转 Word 命令](https://github.com/YanMing-lxb/YM-VSCode-Configurations-for-LaTeX/blob/main/Docs/LaTeX%E8%BD%ACWord%E5%91%BD%E4%BB%A4.md)


### 注意事项
1. 根据[LaTeX Workshop配置说明](https://github.com/YanMing-lxb/YM-VSCode-Configurations-for-LaTeX/blob/main/Docs/LaTeX-Workshop%E9%85%8D%E7%BD%AE%E8%AF%B4%E6%98%8E.md)和[LaTeXMK配置说明](https://github.com/YanMing-lxb/YM-VSCode-Configurations-for-LaTeX/blob/main/Docs/LaTeXMK%E9%85%8D%E7%BD%AE%E8%AF%B4%E6%98%8E.md)中的教程完成配置后，所有的latex项目编译成功后所生成的PDF文件将被将统一放置`Build`文件夹中，编译过程中所产生的辅助文件也将被统一放置在`Build/Temp`文件夹中，并在编译结束后通过自动删除`Build`文件夹中所有子文件夹的方式清除所有辅助文件；

## 工具推荐

### 写作工具

- 画表神器 https://www.tablesgenerator.com/
- $\LaTeX$公式手册 https://www.cnblogs.com/1024th/p/11623258.html
- 识别公式神器 https://mathpix.com/
- $LaTeX$公式编辑器 https://www.latexlive.com/home
- 文献 bib 整理神器 https://dblp.uni-trier.de/
- $\LaTeX$画图画表常用命令 https://en.wikibooks.org/wiki/LaTeX/Floats,_Figures_and_Captions#Tip

### VSCode 插件推荐



