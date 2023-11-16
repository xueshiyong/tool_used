## HOW TO USE GDB
1. 首先要明确调试的意义，目的是找到程序中存在的语义错误。
GDB实际上是一种利用命令行的方式获得程序每一个断点之前的内容。


2. 相对于编辑器如*vscode*,  *clion*等完备的IDE中存在的图形调试，gdb存在的优点可以在更加复杂的工况下对程序进行调试
----
### gdb命令

<image src="image/gdb_command.png">

----

<p><img src="image\breakpoint_loop.png" align="middle" /></p>

采用gdb调试代码的流程

     编译代码
     gcc -g -o main.c main.exe

     在gdb命令中显示代码行, 命令为l
     l
     在gdb中默认显示十行，直接用回车键输出剩下的文件代码

     设置断点
     b + 行号， 如b 60, b 49 // 这是在一个文件中打断点
     b + "二进制文件名"：行号 如 b "main":60 // 在main二进制文件第60行打断点

     查看设置的断点号
     info break

     启动调试断点
     run或者r，启动到设置断点的地方
     start， 启动到main函数的入口点

     查看断点之前的变量内容，使用p进行输出
     p + 变量内容，如p root->val

     断点之后进行下一步运行，采用next或者n进行运行
     next 或者 n
     这就是一步一步的进行方式

     如果下一步里面的运行代码有函数，可以采用step或者s进入调试的函数中
     step 或者 s

     如果想从函数代码之中跳出来，则采用finish或者fi跳出调试函数中
     finish 或者 fi

     如果想直接跳到某一行直接停止，则采用until或者u跳到某一行中
     until 61 或者 until 61

     删除断点的操作
     首先查看断点的内容 info break
     对某一个断点进行删除， delete num, 其中num表示的意思是断点的序号




-----

vscode debug 示意图

<image src="image/vs_debug.png">

-----
需要关注的的图标是中间的三个箭头:  
<image src="image/vs_debug_next.png">

从当前断点下一步运行

    这个箭头表示的含义的是从当前断点往下运行对应gdb中调试代码是
    next 或者 n
        

## HOW TO MAKE *Makefile*

-----
一个简单的makefile编写

<image src="image/makefile_exp.png">
