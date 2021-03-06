---
layout: post
title:  "Vim快捷键整理"
date:   2016-10-14 09:00:13
categories: linux
permalink: /articles/linux/20161014
---

> Vim是Mac OS和Linux里内置的一款强大的文本编辑器，能够和Shell无缝交互。同时也是SSH远程登录VPS时编辑文件的唯一选择。因此掌握Vim对于做服务器运维和Web后端开发的重要性不言而喻。
> 本文对Vim的快捷键操作进行了简单整理。


Vim常见有两种模式一种是Insert模式，该模式下可以像其它文本编辑器一样正常输入字符；另一种是Normal模式，该模式下Vim监听用户的按键可以对文本进行快速修改。

想要从Insert模式切换到Normal模式只需按下ESC键即可。

想要从Normal模式切换到Insert模式，有很多方法。
最直接的是按下I键，效果是：在当前光标处插入文本。
如果按下A键，效果是：在下一光标处追加文本。

以下均是在Normal模式下的部分 快捷键说明：

## 光标的快速移动

* h,j,k,l：左，下，上，右
* w：光标移动至下一单词首位
* b：光标移动至当前单词首位，如果光标已经在当前单词首位，就移动到前一单词首位
* e：光标移动至当前单词末位
* gg：光标移动至文本首行
* Shift+g：光标移动至文本尾行
* 27+Shift+g：光标移动至文本第27行

## 光标跳转

* %: 可以匹配{},"",(),[]之间跳转。
* H、M、L：直接跳转到当前屏幕的顶部、中部、底部。
* #H：跳转到当前屏的第#行。
* #L：跳转到当前屏的倒数第#行。
* zt: 当前编辑行置为屏顶。
* zz: 当前编辑行置为屏中。
* zb: 当前编辑行置为屏底。
* G：直接跳转到文件的底部。
* gg: 跳转到文件首。
* ():跳转到当前的行首、行尾。
* {}：向上、向下跳转到最近的空行。
* [{：跳转到目前区块开头。
* ]}：跳转到目前区块结尾。
* 0: 跳转到行首。
* $: 跳转到行尾。
* 2$: 跳转到下一行的行尾。
* #G: 15G,跳转到15行。
* :#：跳转到#行。
* f'n'：跳转到下一个"n"字母后。
* ctrl+b: 向后翻一页。
* ctrl+f：向前翻一页。
* ctrl+u: 向后翻半页。
* ctrl+d: 向前翻半页。
* ctry+e: 下滚一行。

## 选择

* V: 选择一行。
* ^v: 矩形选择。
* v3w: 选择三个字符


## 插入行

* i: 光标前插入。
* I: 在当前行首插入。
* a: 光标后插入。
* A: 当前行尾插入。
* O: 在当前行之前插入新行。
* o: 在当前行之后插入新行。

## 修改

* r: 替换光标所在处的字符。
* R：替换光标所到之处的字符。
* cw: 更改光标所在处的字到字尾处。
* c#w: c3w 修改3个字符。
* C：修改到行尾。
* ci'：修改配对标点符号中的文本内容。
* di'：删除配对标点符号中的文本内容。
* yi'：复制配对标点符号中的文本内容。
* vi'：选中配对标点符号中的文本内容。
* s：替换当前一个光标所处字符。
* #S：删除 # 行，并以新文本代替。

## 删除与还原

* u：还原上一个操作（不限于删除）
* D：删除到行尾。
* X: 每按一次，删除光标所在位置的前面一个字符。
* x: 每按一次，删除光标所在位置的后面一个字符。
* #x: 删除光标所在位置后面6个字符。
* d^: 删至行首。
* d$: 删至行尾。
* dd:(剪切)删除光标所在行。
* de：删除光标后的单词内容，同时被删除内容存于剪贴板上
* dw: 删除一个单词/光标之后的单词剩余部分。
* d4w: 删除4个word。
* #dd: 从光标所在行开始删除#行。
* daB: 删除{}及其内的内容。
* diB: 删除{}中的内容。
* n1,n2 d：将n1,n2行之间的内容删除。

## 剪切、复制与粘贴

* 选定文本块：使用v进入可视模式；移动光标键选定内容
* y：复制选定块
* yy：复制光标所在整行
* d：剪切选定块
* dd：剪切光标所在整行
* p：粘贴文本

## 大小写转换

* gUU: 将当前行的字母改为大写。
* guu: 将当前行的字母改为小写。
* gUw: 将当前光标下的单词改为大写。
* guw: 将当前光标下的单词改为小写。
* ggguG: 整篇大写
* gg: 光标到文件第一个字符。
* gu: 把选择范围全部小写。
* G: 到文件结束。
* gggUG: 整篇小写：

## 查找与替换

* f+o：在当前行的光标之后查找字母o
* F+b：在当前行的光标之前查找字母b
* :/word：全文查找word。 按下:实际上是进入了Vim的命令模式。查找操作支持正则表达式。
* r+p：将光标之后的字符替换为字母p
* :s/word/replace：光标所在行的第一个word替换为replace。
* :%s/from/to/：全文查找from并替换为to。
* :1,50s/from/to/：在第1行和第50行之间（含）进行搜索和替换。
* :45s/from/to/表示仅仅在第45行进行搜索和替换。而1,$行号范围和%是等价的。
* :%s/from/to/g：全文查找from并替换为to,包含选项g的替换范围更广。
* :%s/from/to/gc：全文查找from并替换为to，替换时询问。可以选择y/n/a/q/l/^E/^Y：y表示同意当前替换；n表示不同意当前替换；a表示替换当前和后面的并且不再确认；q表示立即结束替换操作；l表示把当前的替换后结束替换操作；^E向上滚屏^Y向下滚屏，用来帮助查看前后内容以决定进行操作。

## 执行Shell命令

* :!ls就等同于在Shell终端执行ls命令。

-----------------------------------------------------分割线------------------------------------------------

> 原文参考链接：http://www.jianshu.com/p/c23136f68d2f
