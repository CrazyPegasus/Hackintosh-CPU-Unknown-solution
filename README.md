# 满足你的虚荣心之黑苹果关于本机显示“未知”解决办法

修改的具体步骤包括以下两个部分：
--------

一、设置处理器型号type修改为 Unknown
   
* 在config引导设置中将处理器型号type设置为 Unknown。（“关于本机”页面处理器已识别为 “未知” 的，可跳过此步骤，直接到第二步）

* 使用 Clover Configurator 软件，加载 Clover（四叶草）的配置文件 config.plist，选择左侧 CPU 页，在 Type 栏填写 Unknown，保存退出（如果无法输入 Unknown，可以输入 0x00） 


二、编辑相应的系统文件
------------------     
* 需要修改的文件名为 AppleSystemInfo.strings，该文件具体的位置在于以下目录中。
/System/Library/PrivateFrameworks/AppleSystemInfo.framework/Versions/A/Resources/zh_CN.lproj/AppleSystemInfo.strings
* 你可以拷贝该目录地址，使用 Finder 的 “前往文件夹” 选项快速到达该目录，需要注意的是，如果你的系统语言不是简体中文，请在上述目录地址中 Resources 文件夹下选择进入相应的语言文件夹。
* 找到 AppleSystemInfo.strings 文件后，将其复制出来，一份用来备份，以防修改错误或想还原，另一份用来修改编辑。使用 TextWrangler或者bbedit 打开该文件后，找到 UnknownCPUKind 项，编辑其下的字符串为你想显示的内容。如Intel Core i7-9900K 是当前 “关于本机” 页面显示的处理器型号，你可以将其修改为任意内容。
* 编辑好后，保存退出，将编辑好的文件替换掉系统中的源文件。如果不顺利，可以先删除系统原文件，在将已修改文件复制进该目录
