
## String常用API
#### 网页链接：https://www.runoob.com/csharp/csharp-string.html
``` csharp
public class StringIO : MonoBehaviour  
{  
const string Str1 = "VIP_SKILL";  
// Start is called before the first frame update  
void Start()  
{  
//分割字符串  
string[] str2 = Str1.Split(new char[]{'P'});  
foreach (string t in str2)  
{  
Debug.Log(t);  
}  
}  
}
```
1. Split分割函数，会返回一个新的字符串数组，不会对之前的原字符串造成影响
## StringBuilder常用API
#### 链接
https://blog.csdn.net/sibaison/article/details/72356393

#### StringBuilder介绍
String 对象是不可改变的。每次使用 System.String 类中的方法之一时，都要在内存中创建一个新的字符串对象，这就需要为该新对象分配新的空间。在需要对字符串执行重复修改的情况下，与创建新的 String 对象相关的系统开销可能会非常昂贵。如果要修改字符串而不创建新的对象，则可以使用 System.Text.StringBuilder 类。例如，当在一个循环中将许多字符串连接在一起时，使用 StringBuilder 类可以提升性能。

通过用一个重载的构造函数方法初始化变量，可以创建 StringBuilder 类的新实例，正如以下示例中所阐释的那样。

StringBuilder MyStringBuilder = new StringBuilder("Hello World!");

***本质还是string引用类型字符串，但是可以节约性能，修改时不会重复开辟内存。

## FileStream
#### 链接
http://c.biancheng.net/view/2928.html 不可使用
## FileStream介绍
一个和资源文件有关的类，能够创建，读取，写入文件。
FileStream类是.NET框架中的一个类，它用于读取、写入和操作文件的数据流。它继承了抽象类Stream，可以用于常规的I/O操作。

FileStream类的一些常用功能包括：

1. 打开和创建文件：可以使用FileStream类打开现有文件或创建新文件。
    
2. 读取文件内容：可以从文件中读取字节数据，并根据需要将其转换为其他数据类型。
    
3. 写入文件内容：可以将字节数据写入文件，可以是覆盖原有内容或追加到文件末尾。
    
4. 移动文件指针位置：可以设置和获取文件指针当前的位置，可以在文件中随意移动位置。
    

常见的API有：

1. 构造函数：
    
    - FileStream(string path, FileMode mode)：根据指定路径和打开模式创建FileStream对象。
    - FileStream(string path, FileMode mode, FileAccess access)：根据指定路径、打开模式和访问模式创建FileStream对象。
    - FileStream(string path, FileMode mode, FileAccess access, FileShare share)：根据指定路径、打开模式、访问模式和共享模式创建FileStream对象。
2. 读取方法：
    
    - Read(byte[] buffer, int offset, int count)：从文件中读取指定字节数的数据，并将其存储在缓冲区数组中。
    - ReadByte()：从文件中读取一个字节的数据，并返回其对应的整数值。
3. 写入方法：
    
    - Write(byte[] buffer, int offset, int count)：将指定字节数组中的数据写入文件中。
    - WriteByte(byte value)：将指定的字节数据写入文件中。
4. 文件指针控制方法：
    
    - Seek(long offset, SeekOrigin origin)：将文件指针移动到指定位置。
    - Position属性：获取或设置文件指针的当前位置。
    - Length属性：获取文件的总字节数。

请注意，FileStream类的实例在使用完毕后需要显式地进行关闭和释放资源操作，以避免资源的泄漏。常见的释放资源方法是调用Close()、Dispose()等方法。
刷新缓存和关闭。
``` csharp
namespace IO_Stream  
{  
public class FileStreamTest : MonoBehaviour  
{  
void Start()  
{  
CreateFile();  
ReadFile();  
}  
void CreateFile()  
{  
string filePath = @"Assets/Resources/student.txt";  
FileStream fileStream = new FileStream(filePath, FileMode.OpenOrCreate, FileAccess.ReadWrite, FileShare.ReadWrite);  
string msg = "4396";  
byte[] bytes = Encoding.UTF8.GetBytes(msg);  
fileStream.Write(bytes, 0, bytes.Length);  
fileStream.Flush();  
fileStream.Close();  
}  
void ReadFile()  
{  
string filePath = @"Assets/Resources/student.txt";  
if (File.Exists(filePath))  
{  
FileStream fileStream = new FileStream(filePath, FileMode.Open, FileAccess.Read);  
byte[] bytes = new byte[fileStream.Length];  
fileStream.Read(bytes, 0, bytes.Length);  
string chars = Encoding.UTF8.GetString(bytes);  
Debug.Log("学生的学号为：" + chars);  
fileStream.Close();  
}  
}  
}  
}
```

## Stream之Streamwriter&StreamReader  
#### 介绍
StreamReader和StreamWriter是C#中用于读取和写入文本文件的两个类，它们都继承自抽象类TextReader和TextWriter。

StreamReader用于从文本文件中读取字符流，它提供了几种不同的构造函数用于不同的输入源。可以通过构造函数传入文件路径、流等参数来创建StreamReader对象。读取文件内容时，可以使用Read()、ReadLine()、ReadToEnd()等方法，它们都会返回读取到的数据。

## Directory和DirectoryInfo操作文件夹
#### 介绍
Directory类是一个静态类，提供一系列静态方法来操作文件夹。它可以用于创建、删除、移动和枚举文件夹，以及获取文件夹的属性。

以下是一些Directory类常用的方法示例：

- CreateDirectory(string path): 创建一个新的文件夹。
- Delete(string path): 删除文件夹。
- Move(string sourceDirName, string destDirName): 将文件夹移到新的位置。
- GetFiles(string path, string searchPattern): 获取指定文件夹中所有符合指定搜索模式的文件的路径。

示例代码：

```csharp
using System.IO;

Directory.CreateDirectory("C:\\NewFolder"); // 创建一个新的文件夹
Directory.Delete("C:\\OldFolder"); // 删除文件夹
Directory.Move("C:\\Temp\\SourceFolder", "C:\\Temp\\DestinationFolder"); // 将文件夹移到新的位置

string[] files = Directory.GetFiles("C:\\Temp", "*.txt"); // 获取指定文件夹中所有扩展名为txt的文件
foreach (string file in files)
{
    Console.WriteLine(file); // 输出文件路径
}
```

DirectoryInfo类是一个实例类，它表示一个文件夹。通过创建DirectoryInfo对象，可以得到文件夹的更多详细信息和操作。它提供了一系列实例方法和属性，用于操作文件夹。

以下是一些DirectoryInfo类常用的属性和方法示例：

- FullName: 获取文件夹的完整路径。
- Exists: 判断文件夹是否存在。
- Create(): 创建一个新的文件夹。
- Delete(): 删除文件夹。
- GetFiles(string searchPattern): 获取文件夹中所有符合指定搜索模式的文件的路径。

示例代码：

```csharp
using System.IO;

DirectoryInfo di = new DirectoryInfo("C:\\Temp");
Console.WriteLine(di.FullName); // 输出文件夹的完整路径
Console.WriteLine(di.Exists); // 判断文件夹是否存在

di.Create(); // 创建一个新的文件夹
di.Delete(); // 删除文件夹

FileInfo[] files = di.GetFiles("*.txt"); // 获取文件夹中所有扩展名为txt的文件
foreach (FileInfo file in files)
{
    Console.WriteLine(file.FullName); // 输出文件的完整路径
}
```

总结来说，Directory类提供了静态方法来操作文件夹，而DirectoryInfo类提供了实例方法和属性来操作文件夹。在实际开发中，可以根据需要选择使用哪个类来管理文件夹。

Directory.Delete只能删除空目录，如果目录不为空，需要使用重载函数（，true）；
自动递归删除子文件夹

#### 关于没有删除meta文件的解决办法，需要手动删除meta文件

- 在Unity中，使用Directory.Delete()删除文件夹时，默认不会删除.meta文件。这是因为.meta文件包含有关资源的元数据，例如资源的GUID和导入设置等等。meta文件的存在是为了确保Unity在源代码控制系统（如Git或SVN）中正确地跟踪和管理资源。

示例代码：

``` csharp
Directory.Delete(path, true);  
File.Delete(path + ".meta");
```
