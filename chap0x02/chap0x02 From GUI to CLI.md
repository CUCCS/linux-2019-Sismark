# chap0x02 From GUI to CLI

----------

## 实验环境
* Ubuntu 16.04 Server 64bit
* asciinema 2.0.1
## 实验过程
### asciinema安装及使用
* 采用asciinema[官方](https://asciinema.org/docs/installation#installing-on-linux)安装教程
	* <pre>sudo apt-add-repository ppa:zanchey/asciinema
		sudo apt-get update
		sudo apt-get install asciinema</pre>
* 账号关联
	* <pre>asciinema auth</pre>
* 操作过程记录
	* <pre>asciinema rec [filename]</pre>
* 操作记录上传
	* <pre>asciinema upload [filename]</pre>
* vim学习过程：[asciinema-private-Sismark](https://asciinema.org/a/rtvM3mIpMLKojbKinQhF0x9GR)
## 自查清单
* 你了解vim有哪几种工作模式？
	* normoal-mode(正常模式)：用于导航和操作文本，通常可以使用`ESC`返回该模式。
	* insert-mode(插入模式)：用于插入新内容。
	* visual-mode(可视化模式)：对文本进行高亮显示及进行其他操作。
* Normal模式下，从当前行开始，一次向下移动光标10行的操作方法？如何快速移动到文件开始行和结束行？如何快速跳转到文件中的第N行？
	* 一次向下移动光标10行：`10j`
	* 快速移动到文件开始行和结束行：`gg`和`G`
	* 快速跳转到文件中的第N行：`[N]`
* Normal模式下，如何删除单个字符、单个单词、从当前光标位置一直删除到行尾、单行、当前行开始向下数N行？
	* 删除单个字符：将光标移动至需要删除的字符，按下`x`和`dl`
	* 删除单个单词：将光标移动至需要删除的单词的首字母处，按下`dw`
	* 删除到行尾：`d$`
	* 删除单行：`dd`
	* 删除当前行开始的下N行：`[N]dd`
* 如何在vim中快速插入N个空行？如何在vim中快速输入80个-？
	* 快速插入N个空行(normal-mode)
		* 光标所在下方插入：`[N]o`后接`ESC`
		* 光标所在上方插入：`[N]O`后接`ESC`
	* 快速输入80个-(normal-mode)：`80i[-]`后接`ESC`
* 如何撤销最近一次编辑操作？如何重做最近一次被撤销的操作？
	* 撤销最近一次编辑操作：`u`
	* 重做最近一次被撤销的操作：`CTRL-R`
* vim中如何实现剪切粘贴单个字符？单个单词？单行？如何实现相似的复制粘贴操作呢？
	* 剪切
		* 单个字符：`dl`
		* 当个单词：`dw`
		* 单行：`dd`
	* 粘贴：`p`
	* 复制
		* 单个字符：`yl`
		* 当个单词：`yw`
		* 单行：`yy`
* 为了编辑一段文本你能想到哪几种操作方式（按键序列）？
	* 在光标所在字符前处插入：`i`
	* 在光标所在字符后处插入：`a`
	* 在光标所在行的行首插入：`I`
	* 在光标所在行的行尾插入：`A`
* 查看当前正在编辑的文件名的方法？查看当前光标所在行的行号的方法？
	* `CTRL-G`
* 在文件中进行关键词搜索你会哪些方法？如何设置忽略大小写的情况下进行匹配搜索？如何将匹配的搜索结果进行高亮显示？如何对匹配到的关键词进行批量替换？
	* 从光标处向下搜索：`/[phrase]`
	* 顺着搜索方向搜索：`n`
	* 逆着搜索方向搜索：`N`
	* 从光标处向上搜索：`?[phrase]`
	* 设置忽略大小写：`:set ignorecase`
	* 搜索结果高亮显示：`:set hlsearch`
	* 对匹配到的关键词进行批量替换
		* 全文全局替换：`:%s/old/new/g `
		* 第#行至第#之间全局替换：`:#,#s/old/new/g`
* 在文件中最近编辑过的位置来回快速跳转的方法？
	* 回到上一次编辑的位置：`CTRL-O`
	* 去往下一个位置：`CTRL-R`
* 如何把光标定位到各种括号的匹配项？例如：找到(, [, or {对应匹配的),], or }
	* 将光标放至任意一个括号所在处，按下`%`
* 在不退出vim的情况下执行一个外部程序的方法？
	* `:![外部程序]`
* 如何使用vim的内置帮助系统来查询一个内置默认快捷键的使用方法？如何在两个不同的分屏窗口中移动光标？
	* 查询一个内置默认快捷键:`:help [快捷键]`
	* 分屏窗口中移动光标：`CTRL-ww`
## 参考资料
* [asciinema-Installation](https://asciinema.org/docs/installation#installing-on-linux)
* [asciinema needs a UTF-8 native locale to run. Check the output of `locale` command](https://github.com/asciinema/asciinema/issues/206)