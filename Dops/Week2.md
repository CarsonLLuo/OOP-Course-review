# Week2

# Files and File Types

* Developing software requires manipulating a wide range of file types

* The type of a file can be indicated in two ways:

  * By a file extension which appears as part of the name of the file, separated by a Traditionally these are three letters long but they may be more, or less.
  * By a file type indicator within the file which can be read by the computer.

* Windows is the only OS which requires the use of file extensions. Mac OS and Unix do not require them, but many people choose to use them because it is very convenient to be able to immediately see the type of a file.

* Windows by default hides file extensions in File Manager, but they can be turned on as a setting. The command line always displays them.

1. Media Files
2. Text files
3. Exectables(machine code)不可读
4. containers(mutiple file)

hello转换到knoor

```python
text = "hello"
shift = 3
encrypted_text = ""

for char in text:
    if char.isalpha():
        # 获取字符在ASCII码表中的值，加上偏移量并取余，再转换回字符
        encrypted_char = chr((ord(char) - 97 + shift) % 26 + 97)
    else:
        encrypted_char = char
    encrypted_text += encrypted_char

print(encrypted_text)

```

* **Unicode**

  > *Unicode是一种字符编码标准，用于将字符集中的每个字符映射到唯一的数字代码点上。它涵盖了世界上几乎所有的书写系统，包括拉丁字母、希腊字母、西里尔字母、汉字、日语假名、韩文字母等等，总共可以表示超过13万个字符。Unicode旨在成为全球通用的字符编码标准，使得在不同国家和地区使用不同字符集的计算机之间交换文本信息更加容易和可靠。*
  >
  > *Unicode编码使用的是固定长度的编码格式，每个字符的编码都是由一个或多个字节组成的，具体字节数取决于所使用的编码方案。常见的Unicode编码方案包括UTF-8、UTF-16和UTF-32等，其中UTF-8是最常用的一种编码方式。在UTF-8编码中，每个字符的编码长度可以是1到4个字节，其中常用的拉丁字母和标点符号只需要1个字节就可以表示，而汉字等较少使用的字符需要多个字节来表示。*
  >
  > *Unicode的出现和普及，使得计算机可以更好地支持全球化的文本处理和交互，为国际化和多语言应用奠定了基础。*
  >

* LF和CR

  > *LF和CR都是ASCII字符集中的控制字符，用于在计算机中表示文本行的结束符。*
  >
  > *LF（Line Feed）是ASCII码中的字符编号为10的字符，也被称为“换行符”或“行结束符”，表示在文本中换到下一行。LF通常在Unix、Linux、macOS和一些其他操作系统中用于表示文本行的结束符。*
  >
  > *CR（Carriage Return）是ASCII码中的字符编号为13的字符，也被称为“回车符”，表示将光标移动到文本行的开头位置。CR在一些老的操作系统中用于表示文本行的结束符，如Apple II、Commodore 64等，但现在已经很少使用。*
  >
  > *在Windows系统中，文本行的结束符通常由两个字符组成，即CR和LF的组合，表示先将光标移动到文本行的开头位置，再换到下一行。这种组合被称为“CRLF”（Carriage Return + Line Feed），也称为“回车换行符”。*
  >
  > *在不同操作系统和文本编辑器中，可能使用不同的行结束符，这可能会导致在不同平台之间共享文本文件时出现问题。为了解决这个问题，许多文本编辑器和版本控制系统支持自动检测和转换不同平台的行结束符。*
  >

* **Dll**

  > *DLL（Dynamic Link Library）是Windows操作系统中的一种动态链接库，可以在运行时被加载和卸载。它是一种可执行文件格式，包含一些可共享的代码、数据和资源，可以供多个应用程序或进程共享使用，从而减少内存使用和加速应用程序的启动时间。*
  >
  > *DLL文件通常包含一些函数和数据，它们可以被其他应用程序或进程动态链接调用，实现共享和重用代码。应用程序可以通过函数名或序号来调用DLL中的函数，由操作系统在运行时加载并解析DLL文件，为应用程序提供所需的函数和数据。*
  >
  > *使用DLL可以带来很多好处，比如：*
  >
  > *1.减少内存使用：多个应用程序或进程可以共享同一个DLL文件，避免了多份重复的代码和数据在内存中的存储。*
  >
  > *2.加速应用程序启动时间：由于DLL是在运行时加载的，应用程序可以更快地启动并运行。*
  >
  > *3.方便维护和更新：通过更新DLL文件，可以为多个应用程序或进程提供新的功能或修复问题，避免了需要为每个应用程序单独更新的麻烦。*
  >
  > *4.提高代码重用性：将常用的代码封装在DLL中，可以方便地被多个应用程序或进程共享和重用，提高了代码的可重用性。*
  >
  > *在编写Windows应用程序时，使用DLL可以方便地实现模块化设计和代码重用，提高了开发效率和应用程序的性能。同时，使用DLL也需要注意安全性和兼容性问题，避免出现DLL劫持、版本不兼容等问题。*
  >

从可维护性和可靠性角度考虑，更好的做法是将50个库和程序一起放入容器中。

原因如下：

1.可维护性：将所有库文件和程序打包到一个容器中，可以确保在任何机器上都能够正确运行程序，无需考虑外部环境和依赖关系。这使得程序的部署和维护更加方便和简单。

2.可靠性：如果使用第二种方法，即让用户根据列表下载库文件，那么可能会出现版本不匹配、下载失败等问题，导致程序无法正常运行。而将所有库文件打包到一个容器中，则可以确保所有依赖关系都被正确地解决，避免了这些问题。

3.便捷性：将所有库文件和程序一起放入容器中，可以一次性下载和部署程序，避免了多次下载和手动安装库文件的麻烦。这使得程序的部署更加方便和快捷。

总之，将所有库文件和程序打包到一个容器中，可以提高程序的可维护性和可靠性，减少了出错的可能性，并且方便了程序的部署和维护。因此，更建议采用第一种方法。

‍

# 

‍
