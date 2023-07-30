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
 * Date         : 2023-07-30 15:28:59 +0800
 * LastEditTime : 2023-07-30 15:30:56 +0800
 * Github       : https://github.com/YanMing-lxb/
 * FilePath     : \YM-VSCode-Configurations-for-LaTeX\Docs\Words Count CJK配置说明.md
 * Description  : 
 *  -----------------------------------------------------------------------
 -->

# Words Count CJK配置说明
---
可采用VSCode中的Word Count CJK插件进行中英文字符统计。
具体配置内容如下：
```json
//------------------------------Word Count CJK 配置----------------------------------
  "wordcount_cjk.activateLanguages": ["markdown", "plaintext", "latex"],
  "wordcount_cjk.statusBarTextTemplate": "中文：${cjk} 字 + 英文：${en_words} 词",
  "wordcount_cjk.statusBarTooltipTemplate": "中文字数：${cjk} \\n 非 ASCII 字符数：\\t${total - ascii} \\n 英文单词数：${en_words} \\n 非空白字符数：${total - whitespace} \\n 总字符数：${total}",
  "mdtableeditor.commandViews": {
    "toolbar": [
      "MdTableEditor.fillCells",
      "MdTableEditor.changeAlignRight",
      "MdTableEditor.changeAlignCenter",
      "MdTableEditor.changeAlignLeft",
      "MdTableEditor.insertTop",
      "MdTableEditor.insertBottom",
      "MdTableEditor.insertLeft",
      "MdTableEditor.insertRight",
      "MdTableEditor.removeColumn",
      "MdTableEditor.removeRow",
      "MdTableEditor.moveTop",
      "MdTableEditor.moveBottom",
      "MdTableEditor.moveLeft",
      "MdTableEditor.moveRight",
      "MdTableEditor.columnSelectEmpty",
      "MdTableEditor.sortNumberAsc",
      "MdTableEditor.sortNumberDesc",
      "MdTableEditor.sortTextAsc.ignore",
      "MdTableEditor.sortTextDesc.ignore"
    ],
    "context": [
      "MdTableEditor.columnSelectEmpty",
      "MdTableEditor.fillCells",
      "MdTableEditor.insertBottom",
      "MdTableEditor.insertLeft",
      "MdTableEditor.insertRight",
      "MdTableEditor.insertTop",
      "MdTableEditor.removeColumn",
      "MdTableEditor.removeRow",
      "MdTableEditor.sortNumberAsc",
      "MdTableEditor.sortNumberDesc",
      "MdTableEditor.sortTextAsc.ignore",
      "MdTableEditor.sortTextDesc.ignore"
    ]
  },
  ```