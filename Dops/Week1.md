# Week1

# What is “DevOps”?

## Development

* The part of a company that creates new software.

  公司开发部门

* Carries out requirements analysis, design, software engineering, and programming.

  分析、设计、编程

* Tests the produced software and then hands it over to the customer for installation.

  测试

* Responds to customer requests and bugs with large patches, usually delivered relatively slowly.

## Operations

* The part of a company that manages computers at the backend, eg servers and shared storage.

  公司管理后端计算机的部分，如服务器和共享存储。

* May or may not be the same as customer support which addresses end user queries or IT support which addresses internal user queries and computers.

* Installs server based software and possibly internal user software and keeps it running.

* Maintains computers based on immediate performance and responses. Responds to requests with small fixes delivered ASAP.

* Ideally, proactively monitors and maintains systems to guard against future failure

Progress:

Programmer/

Program

testing

beta staging

remote server (production version)

* Does not have a single definition. Used in a number of contexts by different groups, but the general theme is always similar: **combining aspects from the discipline of operations with those of development**
* This module will look at operations skills and how they are integrated with development. This includes how to use tools to:

  •Make it easier to write code

  •Find and detect bugs

  •Test programs automatically

  •Work with other developers

  •Create different versions of a program

  •Monitor how well a program works

  Make changes rapidly available to users

> *Rollback（回滚）是指在软件开发中撤销或恢复先前所做的更改的操作。当应用程序部署后发生问题或错误时，可以使用回滚操作恢复到之前的状态，以避免可能导致问题的更改继续存在。*

> *CI/CD是一种软件开发流程和实践，代表持续集成和持续交付/部署。CI/CD的目的是通过自动化和持续的反馈，使软件开发、测试和部署变得更加高效和快速。*
>
> *持续集成（Continuous Integration，CI）是指将团队成员的代码集成到共享代码库中，并自动构建和测试应用程序，以便及早发现和解决代码集成问题。每次代码更改后，CI会自动构建、测试和部署应用程序。*
>
> *持续交付/部署（Continuous Delivery/Deployment，CD）是指自动化软件交付流程，包括构建、测试、部署和发布应用程序。持续交付/部署旨在通过减少手动干预，加快软件交付速度，并提高软件质量和可靠性。*

# Version control

Version Control（版本控制）是一种管理文件和代码历史记录的系统，用于跟踪文件或代码的变更。版本控制系统（VCS）可以记录每个文件的更改、何时进行更改、谁进行更改以及更改内容等信息。通过版本控制，用户可以查看文件的历史版本，比较不同版本之间的差异，恢复到之前的版本，并跟踪并协作在同一个代码库中工作的团队成员的更改。

版本控制的优点包括：

1. 安全备份：每个更改都有历史记录，即使发生数据丢失或损坏，也可以轻松地恢复文件或代码。
2. 团队协作：多人可以在同一代码库上工作，轻松共享代码和更改，更容易追踪哪些人对代码库做了什么更改。
3. 版本管理：可以轻松地跟踪文件的版本和更改，查看不同版本之间的差异，并确定谁对文件进行了更改。
4. 分支管理：可以轻松地创建分支（branch），用于并行开发、实验和测试，并合并（merge）分支以进行最终发布。

常见的版本控制系统包括Git、Subversion、Mercurial等，这些工具都是开源的，并且提供了强大的版本控制功能和协作工具，用于简化软件开发和团队协作。

# Compiled and interpreted

编程语言的编译原理是指将源代码转化为可执行的机器代码的过程，通常分为编译和解释两种方式。

编译型语言如C、C++等，需要先将源代码编译为机器码，然后才能运行。编译过程通常包括词法分析、语法分析、语义分析、中间代码生成、代码优化和目标代码生成等步骤。编译型语言的优点是执行速度较快，因为它们的代码已经被翻译成了机器码，可以直接被计算机执行。

解释型语言如Python、Ruby等，不需要编译为机器码，而是在运行时逐行解释执行。解释过程通常包括词法分析、语法分析、解释器解释、中间代码生成等步骤。解释型语言的优点是开发效率较高，因为它们不需要先编译为机器码，而是可以直接在代码修改后执m

What operations can we do with CLI?

1. hop between different folders
2. create a new folder
3. open
4. display all item in folder
5. rename a file
6. copy a file
7. delete
8. \

cd ../Documents

cd c:\users\Clivia\newFilder

interpreted languages, e.g. python  
compiled languages, e.g. c++  
intermediate compiled languages, e.g. JAVA

1. efficiency: how fast it runs  
    c++ > JAVA > python
2. access control: can I easily control who gets to read and change the source code?  
    c++ > JAVA >= python
3. ease of development and debugging: is it easy to write and to debug?  
    python > JAVA > c++
4. versatility: can it run smoothly on different operation systems?  
    python > JAVA > c++  
    5: security: how likely is it to damage the system on which it runs?  
    python > JAVA > c++  
    Languages that interact more directly with the operation system are more likely to damage the system

What operations can we do with CLI?

1. hop between different folders
2. create a new folder
3. create a new file
4. open a file
5. display all the items in a folder
6. rename a file
7. copy a file
8. delete a file

Why do we want to use CLI instead of GUI sometimes?

cd ../Documents  
This is a relative path, which starts from the current directory  
cd C:\users\Clivia\newFolder  
This is an absolute path, which starts from the root directory
