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
 * Date         : 2023-07-29 20:34:33 +0800
 * LastEditTime : 2024-03-09 10:31:06 +0800
 * Github       : https://github.com/YanMing-lxb/
 * FilePath     : \YM-VSCode-Configurations-for-LaTeX\Docs\LaTeXMK配置说明.md
 * Description  : 
 *  -----------------------------------------------------------------------
 -->

# latexmk 编译配置

此处部分内容来源于[无聊就去玩一玩](https://blog.csdn.net/weixin_43852511%20"无聊就去玩一玩")的CSDN博客：[Latex 编译和编写方案配置 — latexmk + latexworkshop](https://blog.csdn.net/weixin_43852511/article/details/105007356)

==如果在Windows平台下使用MiKTeX发行版还需要安装[Perl语言解释器](http://strawberryperl.com/)，方可使用latexmk进行编译。==

## latexmk 原理介绍

latexmk 可利用配置文件，自动地进行 pdflatex、xelatex 等 latex 编译器相关的编译（用过 c/c++ 的同学应该知道 make 工具，latexmk 有点这样的味道）

总而言之，就是以前需要执行各种不同具体的编译命令，现在用了 latexmk后，就可以一个命令搞定一切
> 1. 系统 RC 文件 （Windows 路径：C:\latexmk\LatexMk）
> 2. 用户 RC 文件 （$HOME/.latexmkrc， $Home 是用户目录）
> 3. 当前项目工作路径的 RC 文件 (文件名是 latexmkrc 或 .latexmkrc)
> 4. 其他 RC 文件 （需要在命令行中用 -r 选项指定）

> Linux 系统中可以将下文中的系统 RC 文件 重命令为 .latexmkrc 并放在系统盘的 Home 文件夹下。

RC 文件的书写风格有些类似于 Perl ，所以清楚 Perl 的同学应该会更容易看懂 RC 文件，不清楚也没关系，可以直接把下节我的配置文件拷贝过去用即可，里面的注释有一些解释。

笔者采用系统RC文件和工作路径RC文件，其中系统 RC 文件放共同的一些配置，工作路径下 RC 文件放项目单独的配置。

## latexmk RC文件

系统 RC 文件：

```perl
## 系统latexmk配置文件
## 文件名：LatexMK，文件目录: C:\latexmk\

# 加载 Time::HiRes 模块
use Time::HiRes qw(gettimeofday tv_interval);
use POSIX qw(floor);
# 记录开始时间
my $start_time = [gettimeofday];

# 设置 pdflatex,xelatex,bibtex,biber 选项执行的命令
# %O, %S 是占位符;
# %O 代表选项，%S 代表对应命令的源文件
$pdflatex = "pdflatex -shell-escape -file-line-error -halt-on-error -interaction=nonstopmode -synctex=1 %O %S";
$xelatex = "xelatex -shell-escape -file-line-error -halt-on-error -interaction=nonstopmode -no-pdf -synctex=1 %O %S";
$lualatex = "lualatex -shell-escape -file-line-error -halt-on-error -interaction=nonstopmode -synctex=1 %O %S";


$bibtex = "bibtex %O %S";
$biber = "biber %O %S";

$xdvipdfmx = "dvipdfmx -V 1.6 %O %S";

# 编译索引
$makeindex = "makeindex -s gind.ist %O -o %D %S";

# 用glossaries做索引，所需要的额外编译
add_cus_dep('glo', 'gls', 0, 'glo2gls');
sub glo2gls {
    system("makeindex -s gglo.ist -o \"$_[0].gls\" \"$_[0].glo\"");
}
push @generated_exts, "glo", "gls";

# 用nomencl做索引，所需要的额外编译
add_cus_dep('nlo', 'nls', 0, 'nlo2nls');
sub nlo2nls {
    system("makeindex -s nomencl.ist -o \"$_[0].nls\" \"$_[0].nlo\"");
}
push @generated_exts, "nlo", "nls";

# 执行 latexmk -c 或 latexmk -C 时会清空 latex 程序生成的文件（-C 更强，会清空pdf）
# 除此之外, 可以设置额外的文件拓展，以进行清空
$clean_ext = "blg idx ind lof lot out toc acn acr alg glg glo gls ist fls log spl dtx nlo nls ilg glsdefs fdb_latexmk synctex synctex.gz spl";


# ================================================================================
# 编译结束后要执行的命令
# ================================================================================

END {
    use open qw(:std :utf8);
    use strict;
    use warnings;
    use File::Copy 'move';
    use File::Path 'rmtree';

    # 指定目标文件夹名称
    my $folder_name = 'Build';

    # 打印执行信息
    print "================================================================================\n";
    print "XXXXXXXXXXXXXXXXXXXXXXXXXXXX 开始执行编译以外的附加命令！XXXXXXXXXXXXXXXXXXXXXXXXXXXX\n";
    print "================================================================================\n";

    # 使用文件测试符检查目标文件夹是否存在
    if (-d $folder_name) {
        print "$folder_name 文件夹已存在\n";
    } else {
        # 如果不存在，则创建目标文件夹
        mkdir $folder_name or die "无法创建 $folder_name 文件夹: $!\n";
        print "$folder_name 文件夹已创建\n";
    }

    # 移动以.pdf或.gz结尾的文件到目标文件夹
    for my $file (glob "*.{pdf,gz}") {
        move($file, $folder_name) or die "无法移动文件 $file: $!";
        print "移动文件 $file 到 $folder_name 文件夹\n";
    }

    # 删除指定文件夹下的所有子文件夹
    for my $subfolder (glob "$folder_name/*/") {
        rmtree($subfolder) or warn "无法删除文件夹 $subfolder: $!";
        print "文件夹 $subfolder 已成功删除\n";
    }

    # 格式化时间格式
    my $elapsed = tv_interval($start_time);
    my $hours = floor($elapsed / 3600);
    my $minutes = floor(($elapsed % 3600) / 60);
    my $seconds = $elapsed % 60;
    print "================================================================================\n";
    print "编译时长为：" . sprintf("%02d 小时 %02d 分 %02d 秒 ", $hours, $minutes, $seconds) . "总计 $elapsed 秒\n";
}


```

工作路径 RC 文件：

```perl

## 工作路径 latexmk 配置文件
## 文件名：latexmkrc 或 .latexmkrc
## 文件目录：.

# 设置pdf生成模式，有 0 1 2 3 4 5
# 0 代表不生成 pdf
# 1 代表使用 $pdfltex 选项的命令，在系统 RC 文件已经设置
# 2 代表使用 $ps2pdf；
# 3 代表使用 $dvipdf；
# 4 代表使用 $lualatex；
# 5 代表使用 $xelatex，在系统 RC 文件已经设置

$pdf_mode = 5;

# 设置 bibtex 或 biber 的使用规则，有 0 1 1.5 2
# 0: 不使用 bibtex 或 biber； 清空的时候不会清空 .bbl 文件
# 1: 只有 bib 文件存在才使用 bibtex 或 biber；清空的时候不会清空 .bbl 文件
# 1.5: 只有 bib 文件存在才使用 bibtex 或 biber；当 bib 文件存在时会清空 bbl，否则不会清空
# 2: 有必要更新bbl文件时，运行 bibtex 或 biber，无需测试 bib 文件存在与否；清空删除 bbl

$bibtex_use = 1.5;

# 设置 latex 文件输出的目录
# $out_dir = "Build";
# 设置预览模式，相当于 -pv 选项，在编译结束会开启预览

$preview_mode = 0; # 0不开启，1开启，由于使用latex workshop因此选为0

# $view 设置预览的文件格式

$view = "pdf";

# 设置 latexmk 编译的文件，和不需要编译的文件，可以时多个
# @default_files = ("main.tex");
# @default_excluded_files = ();
#$"latexmk -c" # 由于使用latex workshop进行后清理，因此注销该命令

```

