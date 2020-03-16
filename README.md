﻿//////////////////////////////////////////////////////////////////////////////////
                                DuiEditor使用说明
//////////////////////////////////////////////////////////////////////////////////

    首先说明的是, 使用DuiEditor编辑界面的前提是, 你要会手写. 比如DuiEditor并不会禁止在Window下面直接插入一个List.

    由于duilib有许多的个人维护版本, 为了更大的兼容, 设计器从duilib.xml载入控件属性. 需要给设计器增加新控件的话, 只需要编辑duilib.xml就可以. 如果一个控件在duilib.xml定义, 但界面库没定义, 设计器依然可以编辑属性, 但无法预览. 

1,  控件的默认属性float=false, 非float控件的pos.left和pos.top总是为0, 不要用鼠标直接拖拽非float控件的位置. 这是duilib的布局特点决定的.

2,  关于pos,width,height属性值的冗余, 实际上duilib代码里面, width和height属性就是冗余的. 实在纠结这个的话, 非float控件不要用鼠标或键盘方向键调准位置大小,直接在属性面板中设置pos的值. 毕竟float控件用的很少.

3,  自定义控件的使用, 插入CustomControl时,修改类名.

4,  DuiEditor附带一个xml编辑页面, 与NodePad++等专业工具比起来, 只有一个小小的优点, 实现了简单的语法提示. 我是经常会把VerticalLayout和HorizontalLayout写错的人. ^_^

5,  建议直接在面板中修改属性, 而不是用鼠标拖动位置,改变大小等等.

6,  软件可能有时候会崩溃, 随时保存文件.

2017-xx-xx
1, 完善绝对定位控件的对齐大小等等的设置
2, 类似于MFC编辑对话框资源, 直接输入文本设置控件的text.


2017-07-06

1, 测试窗体使用新建进程的方式, 设计器输出页面有测试窗体的事件显示. 有助于了解控件的触发事件.
   DuiPreviewer.exe是设计器带的预览程序, 支持命令行. 如: DuiPreviewer.exe "-f c:\skin.xml". 
   另外, 可以设置附加测试程序. 

2, 完善XML编辑页面, 看起来有点像nodepad++了. 
   增加代码折叠、颜色显示、查找替换、文件信息行列位置.
   保存文件时XML解析错误提示,错误提示精确到行.

3, 增加选项设置, 载入文档时控件树展开的层数. 

4, 增加样式表定义.

5, 增加控件视图中TabLayout右键菜单, 可以快速切换页面.

6, 增加自定义控件, 自定义控件有个custombasedfrom属性, 仅仅在设计器中使用.  表示父类名，设计器只创建它的父类。 如果没有这个属性，设计器不创建控件。

7, 增加选项直接插入float控件

8, 增加xml注释解析. 可以在布局文件中写入注释内容了.

9, 其他小修改等等.

2017-06-26

1, 控件属性字段的位置, 强制按照duilib.xml中属性定义的顺序. 

2, 非float控件的pos.left和pos.top设置为0. 

3, 修改了图片编辑页面.

4, 每次修改控件属性, 过滤一次默认属性值, 防止属性冗余. 原先是保存文件时才过滤.


2018-08-24
1, ui界面显示使用子窗口的方式，使设计器更加脱离库
2，优化编辑代码页面。
3, 增加设计界面显示UI效果，比如鼠标悬停点击等。
4，重新核对属性文件duilib.xml

目前已知的问题:
1, undo redo无法完美还原，因为没有保存ItemIndex.
2, default style font 这类定义设计器没有做即时更新，修改后，需要重新打开文件。 另外，如果share=true，设计器关闭之前一直有效，因为这是CPaintManager的静态函数设置的,设计器没有清理这类资源。

2019-02-05
1, 增加界面模板

2019-03-01
1, 新增 按住Ctrl键, 移动控件, 是为复制控件
2, 切换文档时, 更新属性窗口

2020-03-16
1，即时更新Style, 这个修改许要改动CPaintManagerUI::AddStyle(). 要重新打开文件才能刷新显示。
2, 即时更新Default. 要重新打开文件才能刷新显示。
3, 即时更新Font属性，即时显示.





    BUG或者建议可以给我发邮件, 53751257@qq.com, 欢迎赞助. 