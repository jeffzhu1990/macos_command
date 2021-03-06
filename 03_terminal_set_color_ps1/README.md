# 修改终端命令提示信息颜色

视频介绍:[点我到优酷看视频](http://v.youku.com/v_show/id_XMjY3NzA0OTQ0MA==.html)

## 下载文件ps1.sh
点击下载:[ps1.sh.zip](https://github.com/zimingwz/macos_command/raw/master/03_terminal_set_color_ps1/ps1.sh.zip)

	ps1.sh脚本的作用是将PS1变量信息写入用户配置文件，来改变终端命令提示信息的颜色。
	可以配合PS1变量生成工具(后文介绍)来生成PS1变量。
	如果你会使用vi编辑器，可不使用这个脚本，而直接修改 '~/.bash_profile' 配置文件(MacOS)即可。 


## PS1变量生成工具
PS1生成工具请访问:[zimingwz.github.io](https://zimingwz.github.io/)

	为了更方便的生成PS1变量，笔者制作了一个WEB应用，可以通过模拟界面实时预览效果，
	添加删除显示内容、改变前景和背景颜色、拖拽排序，来自动生成需要的PS1变量。

![](https://github.com/zimingwz/web_demo/blob/master/99_static/pic/ps1.jpg)

<br>

## PS1变量介绍

PS1是UNIX、MacOS、Linux的系统变量，用来定义终端窗口中命令输入提示符前的显示内容。<br>
PS1变量可以通过命令 `echo $PS1` 来查看。

### PS1内容
MacOS默认的PS1变量为:

	\h:\W \u\$

其中`\h`代表**主机名称**、`\W`代表**当前目录**、 `\u`**代表当前用户**、 `\$`**代表命令提示符** ,还可以使用其他的转义内容，例如:

* `\d` ：日期
* `\H` ：完整主机名
* `\t` ：时间24小时制
* `\T` ：时间12小时制
* `\A` ：时间不含秒
* `\v` ：bash版本
* `\w` ：完整的工作路径
* `\#` ：命令计数

同时可以自定义文本、符号、文字表情等内容在PS1变量中。
自定义内容中不要添加非键盘字符，例如 汉字、表情等。


### PS1颜色
通过在PS1中添加*ANSI*控制码改变命令提示信息文字和背景的颜色和样式。
控制码对照表如下：

|文字色|对应码|背景色|对应码|样式|对应码|
|--:|:--|--:|:--|--:|:--|
|黑色|30|黑色|40|默认|0|
|红色|31|红色|41|加粗|1|
|绿色|32|绿色|42|下划线|4|
|黄色|33|黄色|43|闪烁|5|
|蓝色|34|蓝色|44|反显|7|
|洋红|35|洋红|45|隐藏|8|
|青色|36|青色|46|||
|白色|37|白色|47|||

控制码使用时用 `\[\033[` 和 `m\]` 包裹，多个控制码用分号`;`分隔，举例:
```bash
\[\033[31;43m\]hello\[\033[00m\]      #文字'hello'显示为红色字体、黄色背景
```


















