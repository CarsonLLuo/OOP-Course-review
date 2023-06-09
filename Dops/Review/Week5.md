# Week5

# dir指令

​`dir`​ 是一个常用的命令行指令，用于列出当前目录中的文件和子目录。

在Windows操作系统中，`dir`​ 命令会显示当前目录中的文件和子目录的列表，以及它们的属性（如文件大小、创建日期等）。默认情况下，`dir`​ 命令会列出所有文件和子目录的详细信息。

在许多命令行系统中，可以通过在命令末尾使用 ">" 符号和文件名来将命令的输出保存到文件中，而不是在屏幕上显示。例如，"`dir > filelist.txt`​" 命令将文件列表的输出保存到名为 "filelist.txt" 的文件中。如果文件已经存在，系统的行为取决于具体的操作系统，有些系统会给出错误提示，而另一些系统会覆盖原有的文件内容。如果希望将输出添加到文件而不是覆盖文件内容，可以使用 ">>" 符号，例如 "`dir >> filelist.txt`​"。

另外，通过在命令末尾使用 "<" 符号和文件名，可以将输入从文件中读取而不是从键盘输入。这在需要批处理处理大量输入数据时非常有用。例如，"`command < input.txt`​" 命令将从名为 "input.txt" 的文件中读取输入。

这些功能可以帮助用户将命令行的输出结果保存到文件中，方便后续的处理、分析或记录。同时，通过从文件中读取输入，用户可以轻松地批量处理事先准备好的输入数据。

‍

# 什么是bat语言？

* BAT（Batch）是 Windows 操作系统中的一种批处理语言，用于编写批处理脚本（.bat 文件）。批处理脚本是一系列命令和程序的组合，可以按顺序执行，从而实现自动化操作。

* BAT 脚本通常使用文本编辑器编写，扩展名为 .bat。BAT 语言的语法和命令与 Windows 命令行界面（Command Prompt）中的命令相似，可以使用各种命令和控制结构来实现自动化操作，例如文件操作、网络操作、进程管理、环境变量设置等。

* BAT 语言的语法相对简单，适合用于快速编写一些简单的脚本或小工具。BAT 脚本也常用于批量处理文件、备份数据、自动化部署等任务，可以帮助提高工作效率。

* 尽管 BAT 脚本语言功能比较受限，不如其他编程语言强大和灵活，但在一些简单的场景下，它仍然是非常有用的。

# 命名变量

在 Windows 系统中，可以在命令提示符窗口中使用 `set`​ 命令来定义环境变量。环境变量是一种特殊的变量，可以在当前会话或者系统中被多个程序访问和使用。

定义一个环境变量的格式如下：

```bash
set 变量名=变量值

```

其中，变量名为自定义的名称，变量值可以是任意字符串或数字。需要注意的是，变量名不能包含空格和特殊字符，一般建议使用大写字母来定义环境变量名称。

例如，定义一个名为 `MYVAR`​ 的环境变量，可以在命令提示符窗口中输入以下命令

```bash
set MYVAR=HelloWorld
```

然后可以通过 `%MYVAR%`​ 来引用该变量的值，例如：

```bash
echo %MYVAR%
::输出hello world
```

# 数学运算

如果要对变量进行数学运算，需要在`set`​命令后添加`/a`​开关（用于算术）。例如：

```bash
set /a sum=1+2+3
```

这行代码将计算1+2+3的结果，并将结果存储在变量`sum`​中。

注意：这是标准命令提示符中唯一可以进行数学运算的命令！

# 输入

使用变体的`set`​命令（使用`/p`​开关）可以进行输入操作。例如：

```bash
set /p name=What is your name?
```

请注意，在命令提示符中设置的变量只在当前会话中有效，当会话结束时变量将被重置。设置的变量可以通过使用`%`​符号来引用，例如`echo %name%`​可以显示变量`name`​的值。

# bat语言中的循环语句

在 BAT 脚本中，常用的循环语句有 `for`​ 循环和 `while`​ 循环。

1. ​`for`​ 循环

​`for`​ 循环用于遍历一个序列，并对其中的每个元素执行一次命令。其基本语法如下：

```bash
for %%var in (set) do (
    command1
    command2
    ...
)
```

* 其中，`set`​ 表示需要遍历的序列，可以是一组文件名、一组目录名或者一组字符串等。`%%var`​ 是一个循环变量，可以在循环中使用，每次循环会自动更新其值。在循环体中可以编写需要执行的命令。
* 例如，如果需要遍历当前目录下所有的文件，并对每个文件执行一次 `type`​ 命令，可以使用以下语法：

  ```bash
  for %%i in (*.txt) do (
      type %%i
  )
  ```

* 这段代码会遍历当前目录下所有的 `.txt`​ 文件，并对每个文件执行一次 `type`​ 命令。

2. ​`while`​ 循环

​`while`​ 循环用于在满足某个条件的情况下重复执行一段代码。在 BAT 脚本中，通常使用 `goto`​ 和 `if`​ 语句来实现 `while`​ 循环。其基本语法如下：

```bash
:loop
    command1
    command2
    ...
    if condition goto loop
```

其中，`:loop`​ 表示一个标签，可以用于跳转到循环的起始位置。`condition`​ 是需要判断的条件，如果满足条件，则跳转到 `:loop`​ 标签处重复执行循环体中的命令，否则跳出循环。

例如，如果需要循环读取用户的输入，直到用户输入了一个指定的字符串，可以使用以下语法：

```bash
:loop
    set /p input=Please enter a string:
    if not "%input%"=="exit" goto loop
```

这段代码会不断读取用户的输入，并判断输入的字符串是否等于 `exit`​，如果不是则跳转到 `:loop`​ 标签处继续执行循环体中的命令，否则跳出循环。

‍

```bash
for %%x in (*.docx) do copy %%~x wordfiles
```

* 该代码使用循环语句遍历当前目录中的所有.docx文件。
* 对于每个文件，使用`copy`​命令将文件复制到名为`wordfiles`​的目录中。
* ​`*.docx`​是通配符，用于匹配所有扩展名为.docx的文件。

* 在命令行中使用`for`​循环语句可以对文件进行批量操作。
* 循环控制变量在命令提示符中使用`%%`​前缀。
* ​`%%~`​是对文件名进行处理的特殊符号，用于处理包含空格等特殊字符的现代Windows文件名。

# bat脚本中的条件语句

1. ​`if`​ 语句

​`if`​ 语句用于在满足某个条件的情况下执行一段代码。其基本语法如下：

```bash
if condition (
    command1
    command2
    ...
)
```

其中，`condition`​ 是需要判断的条件，如果满足条件，则执行 `command1`​、`command2`​ 等一系列命令。

2. ​`if-else`​ 语句

​`if-else`​ 语句用于在满足某个条件的情况下执行一段代码，否则执行另一段代码。其基本语法如下：

```bash
if condition (
    command1
    command2
    ...
) else (
    command3
    command4
    ...
)
```

其中，`condition`​ 是需要判断的条件，如果满足条件，则执行 `command1`​、`command2`​ 等一系列命令，否则执行 `command3`​、`command4`​ 等另一系列命令。

‍

# 调用参数

* 在命令行中直接从用户读取输入意味着脚本会在执行时等待用户输入，这会导致脚本无法被其他脚本调用。而通过命令构建脚本是命令行的一个重要优势。
* 相比于从用户读取输入，使用参数（或命令行选项）来传递数据是更受推荐的方式。通过命令行参数，用户可以在执行脚本时直接提供所需的输入，而无需手动输入。这使得脚本更加灵活、可重复使用，并且可以被其他脚本或自动化流程调用。

```bash
#!/bin/bash

# 使用参数传递数据
echo "Hello, $1!"
echo "Your age is $2."

# 示例调用： ./greeting.sh John 25
# 输出： Hello, John!
#       Your age is 25.

```

在这个例子中，脚本通过参数 `$1`​ 和 `$2`​ 来接收用户的输入，而不是直接从命令行读取用户的输入。用户可以在执行脚本时提供姓名和年龄作为参数，脚本会将其打印出来。这种方式使得脚本更具灵活性，可以在不修改脚本代码的情况下多次调用，并且可以方便地集成到其他脚本或工作流程中。

相比之下，如果直接从命令行读取用户输入，脚本可能会变得不够灵活，因为每次执行脚本时都需要手动输入数据，无法通过参数进行自动化或批量处理。使用参数来传递数据可以提高脚本的可用性和易用性。

‍
