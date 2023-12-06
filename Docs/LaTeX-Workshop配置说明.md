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
 * Date         : 2023-07-19 13:15:53 +0800
 * LastEditTime : 2023-12-06 20:40:49 +0800
 * Github       : https://github.com/YanMing-lxb/
 * FilePath     : /YM-VSCode-Configurations-for-LaTeX/Docs/LaTeX-Workshop配置说明.md
 * Description  : 
 *  -----------------------------------------------------------------------
 -->

将下列代码复制到VSCode的settings.json里, 具体操作请百度。

# LaTex Workshop 配置
---
==使用该配置时请将以下几个代码框中的代码粘贴到 settings.json 的{}中。==

`编译工具和命令` 和 `编译链配置` 中的部分命令已注释，可根据需要自行解除注释。
推荐通过`XeLaTeXmk`、`PdfLaTeXmk`、`LuaLaTeXmk`这三个编译链使用LaTeXmk进行编译。

**更多LaTeX Workshop的配置说明请到[LaTeX Workshop 仓库](https://github.com/James-Yu/LaTeX-Workshop)**

## 编译工具和编译链配置
```json
//------------------------------LaTeX 配置----------------------------------

// 编译工具配置
  "latex-workshop.latex.tools": [
    // {
    //   "name": "latexmk",
    //   "command": "latexmk",
    //   "args": [
    //     "-xelatex",
    //     "%DOC%"
    //   ]
    // },
    {
      "name": "xelatexmk",
      "command": "latexmk",
      "args": [
        "-xelatex",
        "%DOC%"
      ]
    },
    {
      "name": "pdflatexmk",
      "command": "latexmk",
      "args": [
        "-pdflatex",
        "%DOC%"
      ]
    },
    {
      "name": "lualatexmk",
      "command": "latexmk",
      "args": [
        "-lualatex",
        "%DOC%"
      ]
    },
    // {
    //   "name": "xelatex",
    //   "command": "xelatex",
    //   "args": [
    //   "-synctex=1",
    //   "-interaction=nonstopmode",
    //   "-file-line-error",
    //   "%DOC%"
    //     ]
    // },          
    // {
    //   "name": "pdflatex",
    //   "command": "pdflatex",
    //   "args": [
    //   "-synctex=1",
    //   "-interaction=nonstopmode",
    //   "-file-line-error",
    //   "%DOC%"
    //   ]
    // },
    // {
    //   "name": "lualatex",
    //   "command": "lualatex",
    //   "args": [
    //   "-lualatex",
    //   "-dvi",
    //   "-synctex=1",
    //   "-interaction=nonstopmode",
    //   "-file-line-error",
    //   "%DOC%"
    //     ]
    // },   
    // {
    //   "name": "makeglossaries",
    //   "command": "makeglossaries",
    //   "args": [
    //   "%DOCFILE%"
    //   ]
    // },
    // {
    //   "name": "makeindex",
    //   "command": "makeindex",
    //   "args": [
    //   "%DOCFILE%.nlo",
    //   "-s",
    //   "nomencl.ist",
    //   "-o",
    //   "%DOCFILE%.nls"
    //   ]
    // },
    // {
    //   "name": "bibtex",
    //   "command": "bibtex",
    //   "args": [
    //   "%DOCFILE%"
    //   ]
    // },
    // {
    //   "name": "biber",
    //   "command": "biber -l zh__pinyin --output-safechars %O %S",
    //   "args": [
    //   "%DOCFILE%"
    //   ]
    // }
  ],

```

## 编译链配置
```json
// 编译链配置 
  "latex-workshop.latex.recipes": [
    // {
    //   "name": "LaTeXmk",
    //   "tools": [
    //   "latexmk"
    //               ]
    // },
    {
      "name": "XeLaTeXmk",
      "tools": [
        "xelatexmk",
      ]
    },
    {
      "name": "PdfLaTeXmk",
      "tools": [
        "pdflatexmk",
      ]
    },
    {
      "name": "LuaLaTeXmk",
      "tools": [
        "lualatexmk",
      ]
    },
    // {
    //   "name": "LaTeXmk-DVIPDFMx",
    //   "tools": [
    //     "LaTeXmk-DVIPDFMx",
    //   ]
    // },
    // {
    //   "name": "upLaTeXmk-DVIPDFMx",
    //   "tools": [
    //     "upLaTeXmk-DVIPDFMx",
    //   ]
    // },

    
    // {
    //   "name": "xelatex",
    //   "tools": [
    //   "xelatex"
    //               ]
    //         },
    // {
    //   "name": "pdflatex",
    //   "tools": [
    //   "pdflatex"
    //               ]
    //         },
    // {
    //   "name": "lualatex",
    //   "tools": [
    //   "lualatex"
    //               ]
    // },
    // {
    //   "name": "bibtex",
    //   "tools": [
    //   "bibtex"
    //               ]
    // },
    // {
    //   "name": "biber",
    //   "tools": [
    //   "biber"
    //               ]
    // },
    // {
    //   "name": "X-bibtex-XX",
    //   "tools": [
    //   "xelatex",
    //   "bibtex",
    //   "xelatex",
    //   "xelatex"
    //               ]
    // },
    // {
    //     "name": "P-bibtex-PP",
    //     "tools": [
    //         "pdflatex",
    //         "bibtex",
    //         "pdflatex",
    //         "pdflatex"
    //     ]
    // },

  ],
```

## 辅助文件清理配置
```json
// 辅助文件清理配置
  // 文件清理。子文件夹中递归删除辅助文件
  "latex-workshop.latex.clean.subfolder.enabled": true,
  //文件清理。此属性必须是字符串数组 "*.bbl",
  "latex-workshop.latex.clean.fileTypes": [
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
    "*.spl",
    "*.dtx",
    "*.nlo",
    "*.nls",
    "*.nlg",
    "*.ilg",
    "*.xdv",
    "*.glsdefs",
    "*.fdb_latexmk",
    "*.fdb_latexmk,",
    "*.synctex(busy)", 
    "*.synctex.gz(busy)",
    "*/*.aux",
    "*.ttt",
    "*.fff",
    "*.nav",
    "*.snm",
    "*.vrb",
  ], 
```

## 编译操作配置
```json
// 编译操作配置
  // 设置是否自动编译
  "latex-workshop.latex.autoBuild.run":"never",
  // 自动编译时间间隔(设置不自动编译时,该命令失效)
  "latex-workshop.latex.autoBuild.interval": 1000,
  // 编译结果输出到特定路径
  "latex-workshop.latex.outDir": "./Build",
  // 编译错误后是否尝试重新编译
  "latex-workshop.latex.autoBuild.cleanAndRetry.enabled": false,
  // 编译完成后关于清除辅助文件的操作设置
  "latex-workshop.latex.autoClean.run": "onBuilt", 
  // 使用上次的recipe编译组合
  "latex-workshop.latex.recipe.default": "lastUsed",
```

## 菜单及通知的配置
```json
// 菜单及通知的配置
  //右键菜单
  "latex-workshop.showContextMenu":false,
  //从使用的包中自动补全命令和环境
  "latex-workshop.intellisense.package.enabled": true,
  //编译出错时设置是否弹出气泡设置
  "latex-workshop.message.error.show": false,
  "latex-workshop.message.warning.show": false,
```

## 编辑器配置
```json
// 编辑器配置
  // 用于反向同步的内部查看器的键绑定。ctrl/cmd +点击(默认)或双击
  "latex-workshop.view.pdf.internal.synctex.keybinding": "double-click",
  // 用于实时预览图片
  "latex-workshop.hover.preview.enabled": true,
  // 实时显示引文信息
  "latex-workshop.hover.citation.enabled": true,
  // 实时显示参考信息
  "latex-workshop.hover.ref.enabled": true,
  // 实时显示命令所属文档
  "latex-workshop.hover.command.enabled": true,

  // 大纲隐藏题注
  // "latex-workshop.view.outline.floats.caption.enabled": false,
  // 大纲中隐藏label
  // "latex-workshop.view.outline.commands": [],
  // 大纲隐藏浮动体数字序号
  // "latex-workshop.view.outline.floats.number.enabled": false,
  // 大纲隐藏浮动体
  // "latex-workshop.view.outline.floats.enabled": false,
```

## 内部查看器配置
```json
// 内部查看器配置
  // 设置VScode内部查看生成的pdf文件 tab browser external
  "latex-workshop.view.pdf.viewer": "tab",
  // 设置VScode内部查看的缩放级别："auto", "page-actual", "page-fit", "page-width"
  "latex-workshop.view.pdf.zoom": "page-width",
  // PDF查看器用于在\ref上的[View on PDF]链接 auto tabOrBrowser external
  "latex-workshop.view.pdf.ref.viewer":"auto",

  // 浅色模式下的前景色
  "latex-workshop.view.pdf.color.light.pageColorsForeground":"",
  // 浅色模式下的背景颜色
  "latex-workshop.view.pdf.color.light.pageColorsBackground":"",
  // 浅色模式下查看器的背景颜色
  "latex-workshop.view.pdf.color.light.backgroundColor":"",
  // 浅色模式下页面边框颜色
  "latex-workshop.view.pdf.color.light.pageBorderColor":"#e60012",
  // 深色模式下的前景色
  "latex-workshop.view.pdf.color.dark.pageColorsForeground":"",
  // 深色模式下的背景颜色
  "latex-workshop.view.pdf.color.dark.pageColorsBackground":"",
  // 深色模式下查看器的背景颜色
  "latex-workshop.view.pdf.color.dark.backgroundColor":"#272822",
  // 深色模式下页面边框颜色
  "latex-workshop.view.pdf.color.dark.pageBorderColor":"#e60012",

  // 启用 CSS 反转过滤器
  "latex-workshop.view.pdf.invertMode.enabled": "auto",
  // 定义 PDF 查看器的 CSS 反转过滤器级别 从0到1的任何浮点数
  "latex-workshop.view.pdf.invert": 0,
  // 定义启用反转模式时 PDF 查看器的 CSS 亮度滤镜级别 从0到2的任何浮点数
  "latex-workshop.view.pdf.invertMode.brightness": 0.85,
  // 定义启用反转模式时 PDF 查看器的 CSS 灰度滤镜级别 从0到1的任何浮点数
  "latex-workshop.view.pdf.invertMode.grayscale": 0,
  // 定义启用反转模式时 PDF 查看器的 CSS 色调旋转滤镜角度。可能的值是从0到360
  "latex-workshop.view.pdf.invertMode.hueRotate": 0,
  // 定义启用反转模式时 PDF 查看器的 CSS 棕褐色滤镜级别。可能的值是从0到1
  "latex-workshop.view.pdf.invertMode.sepia": 0,
```

## 外部查看器(SumatraPDF)配置 (可选)
```json
// 外部查看器(SumatraPDF)配置 (可选)
  // 使用外部查看器时要执行的命令。此功能不受官方支持。
  "latex-workshop.view.pdf.external.viewer.command": "D:/Application/SumatraPDF/SumatraPDF.exe", // 注意修改成自己的SumatraPDF.exe所在路径

  // 使用外部查看器时，latex-workshop.view.pdf.external.view .command的参数。此功能不受官方支持。%PDF%是用于生成PDF文件的绝对路径的占位符。
  "latex-workshop.view.pdf.external.viewer.args": [
    "-forward-search",
    "%TEX%",
    "%LINE%",
    "-reuse-instance",
    "-inverse-search",
    "D:/Application/Microsoft VS Code/Code.exe -r -g \"%f\":%l", // 注意修改成自己的Code.exe所在路径
    "%PDF%"
  ],

  // 将synctex转发到外部查看器时要执行的命令。此功能不受官方支持。
  "latex-workshop.view.pdf.external.synctex.command": "D:/Application/SumatraPDF/SumatraPDF.exe", // 注意修改成自己的SumatraPDF.exe所在路径

  // latex-workshop.view.pdf.external.synctex的参数。当同步到外部查看器时。%LINE%是行号，%PDF%是生成PDF文件的绝对路径的占位符，%TEX%是触发syncTeX的扩展名为.tex的LaTeX文件路径。
  "latex-workshop.view.pdf.external.synctex.args": [
    "-forward-search",
    "%TEX%",
    "%LINE%",
    "-reuse-instance",
    "-inverse-search",
    "\"D:/Application/Microsoft VS Code/Code.exe\" \"D:/Application/Microsoft VS Code/resources/app/out/cli.js\" --ms-enable-electron-run-as-node -r -g \"%f:%l\"", // 注意修改路径
    "%PDF%"
  ],

```


