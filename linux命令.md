[TOC]

[TOC]



# linux命令

运行环境MINGW64/bash

显示$并|光标闪缩表示正在命令模式

# 一、文件管理

## cat(Concatenate)

```
$ cat --help
Usage: cat [OPTION]... [FILE]...
Concatenate FILE(s) to standard output.

With no FILE, or when FILE is -, read standard input.

  -A, --show-all           equivalent to -vET
  -b, --number-nonblank    number nonempty output lines, overrides -n
  -e                       equivalent to -vE
  -E, --show-ends          display $ at end of each line
  -n, --number             number all output lines
  -s, --squeeze-blank      suppress repeated empty output lines
  -t                       equivalent to -vT
  -T, --show-tabs          display TAB characters as ^I
  -u                       (ignored)
  -v, --show-nonprinting   use ^ and M- notation, except for LFD and TAB
      --help     display this help and exit
      --version  output version information and exit
```

使用方式可以表示为：cat [-AbeEnstTuv] [--help] [--version] fileName

其中 -AbeEnstTuv指所有选项

注意：文件需要文件名和文件类型，如：a.txt

### 使用echo创建文件

echo是shell的命令不是linux的命令

### 使用cat查看文件内容

假设当前目录a.txt文件内容为

```

```



```
$ cat a.txt
```

* 输入命令回车之后在下一行显示文本内容，内容有多少行，相应的就显示多少行，显示完毕后退出到命令模式
* 需要进入到文件所在的目录才能找到文件

### 查找文件中的内容

```
$ cat a.txt | grep i
```

* "|",称为*管道符号*(piping symbol),可将其视为各命令间传递信息 的管道,用来将某个命令或程序的输出提供给另一个命令或程序
* grep是另一个命令，查找符合要求的字符串，注意文件内容尽量不要使用中文输入的字符包含标点符号
* 命令要求查看a.txt内容，并查找字符串中包含 i 字母的字符串，查找结果将含有 i 字母的字符串（一行内容）显示在命令行，并且多个字符串都是换行显示。

### chattr(change attribute)

```
功能说明：改变文件属性。

语　　法：chattr [-RV][-v<版本编号>][+/-/=<属性>][文件或目录...]

补充说明：这项指令可改变存放在ext2文件系统上的文件或目录属性，这些属性共有以下8种模式： 
　a：让文件或目录仅供附加用途。 
　b：不更新文件或目录的最后存取时间。 
　c：将文件或目录压缩后存放。 
　d：将文件或目录排除在倾倒操作之外。 
　i：不得任意更动文件或目录。 
　s：保密性删除文件或目录。 
　S：即时更新文件或目录。 
　u：预防以外删除。 
 
参　　数：
　-R  递归处理，将指定目录下的所有文件及子目录一并处理。 
　-v<版本编号>  设置文件或目录版本。 
　-V  显示指令执行过程。 
　+<属性>  开启文件或目录的该项属性。 
　-<属性>  关闭文件或目录的该项属性。 
　=<属性>  指定文件或目录的该项属性。 

```



### chgrp(change group)

```
功能说明：变更文件或目录的所属群组。

语　　法：chgrp [-cfhRv][--help][--version][所属群组][文件或目录...] 或 chgrp [-cfhRv][--help][--reference=<参考文件或目录>][--version][文件或目录...] 

补充说明：在UNIX系统家族里，文件或目录权限的掌控以拥有者及所属群组来管理。您可以使用chgrp指令去变更文件与目录的所属群组，设置方式采用群组名称或群组识别码皆可。 

参　　数：
　-c或--changes  效果类似"-v"参数，但仅回报更改的部分。 
　-f或--quiet或--silent 　不显示错误信息。 
　-h或--no-dereference 　只对符号连接的文件作修改，而不更动其他任何相关文件。 
　-R或--recursive 　递归处理，将指定目录下的所有文件及子目录一并处理。 
　-v或--verbose 　显示指令执行过程。 
　--help 　在线帮助。 
　--reference=<参考文件或目录> 　把指定文件或目录的所属群组全部设成和参考文件或目录的所属群组相同。 
　--version 　显示版本信息。
```



### chmod(change mode)

```
功能说明：变更文件或目录的权限。

语　　法：chmod [-cfRv][--help][--version][<权限范围>+/-/=<权限设置...>][文件或目录...] 或 chmod [-cfRv][--help][--version][数字代号][文件或目录...] 或 chmod [-cfRv][--help][--reference=<参考文件或目录>][--version][文件或目录...] 

补充说明：在UNIX系统家族里，文件或目录权限的控制分别以读取，写入，执行3种一般权限来区分，另有3种特殊权限可供运用，再搭配拥有者与所属群组管理权限范围。您可以使用chmod指令去变更文件与目录的权限，设置方式采用文字或数字代号皆可。符号连接的权限无法变更，如果您对符号连接修改权限，其改变会作用在被连接的原始文件。权限范围的表示法如下： 
　u：User，即文件或目录的拥有者。 
　g：Group，即文件或目录的所属群组。 
　o：Other，除了文件或目录拥有者或所属群组之外，其他用户皆属于这个范围。 
　a：All，即全部的用户，包含拥有者，所属群组以及其他用户。 
 
　有关权限代号的部分，列表于下： 
　r：读取权限，数字代号为"4"。 
　w：写入权限，数字代号为"2"。 
　x：执行或切换权限，数字代号为"1"。 
　-：不具任何权限，数字代号为"0"。 
　s：特殊?b>功能说明：变更文件或目录的权限。
 
参　　数：
　-c或--changes 　效果类似"-v"参数，但仅回报更改的部分。 
　-f或--quiet或--silent 　不显示错误信息。 
　-R或--recursive 　递归处理，将指定目录下的所有文件及子目录一并处理。 
　-v或--verbose 　显示指令执行过程。 
　--help 　在线帮助。 
　--reference=<参考文件或目录> 　把指定文件或目录的权限全部设成和参考文件或目录的权限相同 
　--version 　显示版本信息。 
　<权限范围>+<权限设置> 　开启权限范围的文件或目录的该项权限设置。 
　<权限范围>-<权限设置> 　关闭权限范围的文件或目录的该项权限设置。 
　<权限范围>=<权限设置> 　指定权限范围的文件或目录的该项权限设置。 

```



### chown(change owner)

```
功能说明：变更文件或目录的拥有者或所属群组。

语　　法：chown [-cfhRv][--dereference][--help][--version][拥有者.<所属群组>][文件或目录..] 或chown [-chfRv][--dereference][--help][--version][.所属群组][文件或目录... ...] 或chown [-cfhRv][--dereference][--help][--reference=<参考文件或目录>][--version][文件或目录...] 

补充说明：在UNIX系统家族里，文件或目录权限的掌控以拥有者及所属群组来管理。您可以使用chown指令去变更文件与目录的拥有者或所属群组，设置方式采用用户名称或用户识别码皆可，设置群组则用群组名称或群组识别码。 

参　　数：
　-c或--changes 　效果类似"-v"参数，但仅回报更改的部分。 
　-f或--quite或--silent 　不显示错误信息。 
　-h或--no-dereference 　之对符号连接的文件作修改，而不更动其他任何相关文件。 
　-R或--recursive 　递归处理，将指定目录下的所有文件及子目录一并处理。 
　-v或--version 　显示指令执行过程。 
　--dereference 　效果和"-h"参数相同。 
　--help 　在线帮助。 
　--reference=<参考文件或目录> 　把指定文件或目录的拥有者与所属群组全部设成和参考文件或目　录的拥有者与所属群组相同。 
　--version 　显示版本信息。
```



### cksum(check sum)

```
功能说明：检查文件的CRC是否正确。 

语　　法：cksum [--help][--version][文件...]  

补充说明：CRC是一种排错检查方式，该演算法的标准由CCITT所指定，至少可检测到99.998%的已知错误。指定文件交由cksum演算，它会回报计算结果，供用户核对文件是否正确无误。若不指定任何文件名称或是所给予的文件名为"-"，则cksum指令会从标准输入设备读取数据。 

参　　数：
　--help 　在线帮助。 
　--version 　显示版本信息。
```



### cmp

### cp

### cut

### diff

### diffstat

### file

### find

### git

### gitview

### indent

### in 

### locate

### lsattr

### mattrib

### mc

### mcopy

### mdle

### mdir

### mktemp

### mmove

### mread

### mren

### mshowfat

### mtools

### mtoolstest

### mv

### od

### paste

### patch

### rcp

### rhmask

### rm

### slocate

### split

### tee

### tmpwatch

### touch

### umask

### whereis

### which

# 二、文件传输

# 三、文档编辑

# 四、磁盘维护

# 五、网络通信

# 六、系统管理

# 七、系统设置

# 八、备份压缩

# 九、其他

# 十、windows system

# 十一、电子邮件与新闻组