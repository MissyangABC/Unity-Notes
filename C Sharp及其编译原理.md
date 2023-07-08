### 一、C shaper

#### 1、C#是一个简单的、现代的、通用的、面向对象的编程语言，他是由微软开发的。
  C#编程基于C和C++编程语言，是专为公共语言基础结构（CLI：Common Language Infrastructure 通用语言框架）设计的。CLI由可执行代码和运行时环境组成，允许在不同的计算机平台和体系结构上使用各种高级语言。

#### 2、C#强大的编译功能：
  布尔条件（Boolean Conditions）,自动垃圾回收（Automatic Garbage Collection），标准库（Standard Library），组件版本（Assembly Versioning），属性（Properties）和事件管理（Events Management）,易于使用的泛型（Generics），索引器（Indexers）,条件编译（Conditional Compilation），简单的多线程（Multithreading），LINQ和Lambda表达式，集成Windows

#### 3、.Net框架是一个创新平台，
  能编写以下应用程序：Windows应用程序，Web应用程序，Web服务等。支持以下语言开发：C#、C++、Visual Basic等等。.Net框架由巨大的代码库组成，含以下框架组件：公共语言运行库、.Net框架类库、公共语言规范、通用类型系统、元数据和组件、Windows窗体、ASP.Net和ASP.Net AJAX、ADO.Net、Windows工作流基础、Windows显示基础、Windows通信基础、LINQ。

### 二、编译原理

#### 1. C#中的几种后缀名含义：

　　.Sln //解决方案文件→.csproj //项目文件→.cs //类文件。他们是层层包含的关系。

#### 2. 命名空间：

　　命名空间是.NET中提供 应用程序代码容器的方式，他是一个容器。这样就可以唯一地标识代码及其内容;

　　在C#中，创建命名空间的关键字是 namespace,在VS中创建控制台应用程序时会自动加入命名空间。命名是以“层”的形式存在，如有多层则以“.”分开。

#### 3. 编写应用程序：

　　.NET Framework 编写应用程序，即使用.NET代码库编写代码；

　　为了执行C#代码，必须把他们转换为目标操作系统能够理解的语言，即本机代码（native code）,这种转换称为 _**编译代码**_，由**编译器**执行。

#### 4. 编译代码：

　　编译代码指将高级语言转换为本机代码:由_**IDE**_里面的**编译器**→把编译代码转换为通用的_**中间语言**_（_**CIL**_即 Common Intermediate Language）→再由**IDE**转换为**本机代码**；

　　如：C#应用程序代码（编写代码）→把代码编译为_**CIL（托管代码）**_，存储在程序集中→本机代码（_**JIT编译器**_）→在托管的_**CLR（公共语言运行库）**_环境下运行本机代码及其他应用程序或进程→EXE文件/DLL库。

#### 5. JIT编译器（Just-In-Time Compiler）：

　　能将CIL编译成各种不同的机器代码，以适应对应的系统平台

#### 6. 托管代码：（microsoft的_**中间语言**_）

　　 托管代码是microsoft的_**中间语言**_，主要作用是在 _**.NET** **Framework**_ 的 CLR 执行代码前去编译源代码。

#### 7. CLR：（公共语言运行库）

　　管理应用程序、方式是管理内存，处理安全性等。

#### 8. 源代码运行时分为两个阶段：

　　（1）源代码（如：VB,C#）编译为托管代码；

　　（2）托管代码编译为microsoft系统的.net平台专用文件（如：类库，可执行文件等）。

#### 9. 程序集：（即程序文件（exe）和库（dll））

　　程序由指令组成，指令则是由标识符、关键字、常量、运算符、分隔符等构成。


　　