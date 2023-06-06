# Week1

解释型语言interpreted languages, e.g. python  
汇编型语言compiled languages, e.g. c++  
中级编译语言intermediate compiled languages, e.g. JAVA

1. 效率efficiency: how fast it runs  
    c++ > JAVA > python
2. 访问控制access control: can I easily control who gets to read and change the source code?  
    c++ > JAVA >= python
3. 易于开发调制ease of development and debugging: is it easy to write and to debug?  
    python > JAVA > c++
4. 多功能性versatility: can it run smoothly on different operation systems?在不同操作系统上顺利运行  
    python > JAVA > c++
5. 安全性security: how likely is it to damage the system on which it runs?  
    python > JAVA > c++  
    Languages that interact more directly with the operation system are more likely to damage the system

What operations can we do with CLI?

使用CLI可以进行的操作

1. 在不同文件夹中跳转：

    * ​`cd folder_path`​：进入到指定路径的文件夹中。
    * ​`cd ..`​：返回上一级文件夹。
    * ​`cd \`​：返回到根目录。
    * ​`cd %userprofile%`​：返回到用户的主文件夹。
2. 创建新的文件夹：

    * ​`mkdir folder_name`​：在当前文件夹中创建一个新的文件夹，命名为 `folder_name`​。
3. 创建文件：

    * ​`echo. > file_name`​：在当前文件夹中创建一个新的空文件，命名为 `file_name`​。
4. 打开文件：

    * 对于文本文件，你可以使用以下命令来打开：

      * ​`notepad file_name`​：使用记事本打开文件。
      * ​`type file_name`​：在终端中显示文件内容。
    * 对于其他类型的文件，可以使用适当的应用程序来打开。例如，`start file_name`​ 可以打开文件所关联的默认程序。
5. 显示文件夹中所有项目：

    * ​`dir`​：显示当前文件夹中的所有文件和子文件夹。
    * ​`dir folder_path`​​：显示指定路径文件夹中的所有项目。
6. 重命名文件：

    * ​`ren old_file_name new_file_name`​：将文件名从 `old_file_name`​ 更改为 `new_file_name`​。
7. 复制文件：

    * ​`copy source_file destination_path`​：将 `source_file`​ 复制到 `destination_path`​。如果 `destination_path`​ 是文件夹路径，复制后的文件将放置在该文件夹中并保留原始文件名。
8. 删除文件：

    * ​`del file_name`​：从当前文件夹中删除指定的文件。
    * ​`del /s folder_name`​：递归删除整个文件夹及其内容。
9. 移动文件

    1. 将文件移动到另一个目录：

        * ​`move source_file destination_path`​：将名为 `source_file`​ 的文件移动到 `destination_path`​ 目录中。如果 `destination_path`​ 是一个文件夹路径，文件将被移动到该文件夹中，并保持原始文件名。
    2. 将文件重命名并移动到另一个目录：

        * ​`move source_file destination_path\new_file_name`​：将名为 `source_file`​ 的文件重命名为 `new_file_name`​，然后将其移动到 `destination_path`​ 目录中。

‍

* `work\tuesday\test1.txt`​

引用当前目录下的 "work" 文件夹中的 "tuesday" 文件夹中一个名为 "test1.txt" 的文件

* `..\test.txt`​

返回上一级目录，该目录下一个名为 "test.txt" 的文件

* `..\documents\hello.txt`​

上一级目录的 "documents" 文件夹中一个名为 "hello.txt" 的文件

* `cd ..`​ 是一个命令，用于在命令行界面中返回到上一级目录

‍

* `copy *.* backup`​

将当前目录下的所有文件复制到名为 "backup" 的目录中。通配符 `*.*`​ 表示匹配当前目录下的所有文件。复制操作将这些文件复制到目标目录 "backup" 中，保持文件名和扩展名不变。

* `copy *.* g:\`​

当前目录下的所有文件复制到 G 驱动器的根目录下

* ​`copy new old`​

将目录new中的所有文件复制到目录old中，前提是这些目录已经存在

* ​`copy work*.* work`​

将以 "work" 开头的所有文件复制到名为 "work" 的目录中。通配符 `*.*`​ 表示匹配以任意字符开头且具有任意文件扩展名的文件。复制操作将这些文件复制到目标目录 "work" 中，并保持文件名和扩展名不变。如果目标目录不存在，则会出现错误。

* `copy work?.* work`​

Copy all files with names beginning with "work" and exactly one more character (work2.doc, work5.txt, but not  work05.txt) to directory work, which must already exist

将所有名称以"work"开头的文件和恰好多一个字符(work2.doc, work5.txt，但不是work05.txt)复制到目录work，该目录必须已经存在

* ​`copy *.xls excel`​

将当前目录下所有扩展名为 ".xls" 的文件复制到名为 "excel" 的目录中。通配符 `*.xls`​ 表示匹配当前目录下所有扩展名为 ".xls" 的文件

* ​`copy *.xls *.oldx`​

将当前目录下所有扩展名为 ".xls" 的文件复制为具有相同文件名但扩展名为 ".oldx" 的文件。通配符 `*.xls`​ 表示匹配当前目录下所有扩展名为 ".xls" 的文件。复制操作将这些文件复制到同一目录下，并将其扩展名更改为 ".oldx"，但文件名保持不变

* `del *.*`​

删除当前目录下的所有文件。通配符 `*.*`​ 表示匹配当前目录下的所有文件。执行该命令会删除当前目录中的所有文件，但不会删除文件夹

* ​`xcopy /s *.*`​*​   ​*​`..\backup`​

使用 `xcopy`​ 命令来复制当前目录下的所有文件和子文件夹（包括空文件夹），并将它们复制到上一级目录的 "backup" 文件夹中。

​`/s`​ 是 `xcopy`​ 命令的一个开关，它指示 `xcopy`​ 在复制文件时包含子目录及其内容。

注意，在执行该命令之前，确保上一级目录中已经存在名为 "backup" 的文件夹，否则会出现错误。

​`dir moose.txt /s`

在当前目录及其子目录中搜索名为 "moose.txt" 的文件，并显示包含该文件的路径和文件信息。

​`dir`​ 是用于显示文件和目录列表的命令。 `moose.txt`​ 是要搜索的文件名。 `/s`​ 是 `dir`​ 命令的一个开关，它指示 `dir`​ 在子目录中递归搜索文件。

执行该命令后，命令行界面将显示所有包含 "moose.txt" 文件的路径以及其他相关信息，例如文件大小、创建日期和最后修改日期等。

* ​`del *.* /s`​

该命令的意思是删除当前目录及其子目录中的所有文件。

​`del`​ 是删除文件的命令。 `*.*`​ 是通配符，表示匹配当前目录下的所有文件。 `/s`​ 是一个开关，它指示 `del`​ 命令在子目录中递归删除文件。

执行该命令后，命令行界面将删除当前目录及其子目录中的所有文件。请注意，这是一个非常危险的命令，因为它会永久删除文件，而不会将其放入回收站。

* 绝对路径
* 相对路径

‍
