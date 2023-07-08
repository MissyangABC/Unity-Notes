###### 委托的定义和使用
委托是一个类型，可以赋值（存储）一个方法的引用 
修饰符为 ***delegate***
###### 声明委托
``` csharp
delegate void MyDelegate1() or (int x)
delegate void MyDelegate2<T> (T x)
```
###### 引用方法
``` csharp
//在赋值引用方法时，方法名后不加括号
ShowDelegate showDelegate = Show1;
ShowDelegate showDelegate = new ShowDelegate(func);
//两种实现方法
showDelegate.Invoke();  //使用Invoke函数
showDelegate();
```
###### 简易案例
``` csharp
//委托声明及使用示例
public class BaseDelegate : MonoBehaviour  
{  
//Rider忽略委托修饰符代码分析  
[SuppressMessage("ReSharper", "MemberCanBePrivate.Global")]  
public delegate void ShowDelegate();  
  
[SuppressMessage("ReSharper", "MemberCanBePrivate.Global")]  
public delegate void PrintDelegate(string name, int number);  
  
delegate int CalculateDelegate();  
delegate void ShowDelegate2<T>(T num);  
  
  
// Start is called before the first frame update  
void Start()  
{  
ShowDelegate showDelegate = Show1;  
showDelegate.Invoke();  
showDelegate();  
PrintDelegate printDelegate = Print;  
printDelegate.Invoke("Clear-love", 001);  
printDelegate("Uzi", 008);  
CalculateDelegate calculateDelegate = Calculate;  
int a = calculateDelegate.Invoke();  
int b = calculateDelegate();  
Debug.Log(a);  
ShowDelegate2<string> showDelegate2 = Show2;  
showDelegate2("Hello");  
}  
  
// Update is called once per frame  
void Update() { }  
void Show1()  
{  
Debug.Log("执行Show函数！");  
}  
void Print(string name, int number)  
{  
Debug.Log(name + "的编号是" + number);  
}  
int Calculate()  
{  
return 1000;  
}  
void Show2(string str1)  
{  
Debug.Log("VAR: " + str1);  
}  
}
```
***
###### 系统内置Action
- 不能有返回值
- 系统内置Action不需要再重新声明一个委托，系统已经内置写好

**Action 示例**
``` csharp
public class ActionTest : MonoBehaviour  
{  
Action m_Action1;  
Action<int, int> m_Action2;  
  
// Start is called before the first frame update  
void Start()  
{  
m_Action1 = Show1;  
m_Action2 = Show2;  
m_Action1.Invoke();  
m_Action1();  
m_Action2.Invoke(1,2);  
m_Action2(3, 4);  
}  
  
// Update is called once per frame  
void Update() { }  
void Show1()  
{  
Debug.Log("Action1");  
}  
void Show2(int n, int m)  
{  
Debug.Log("Action2:" + "n=" + n + "m=" + m);  
}  
}
```
###### 系统内置Func 
- 有返回值
- 如果调用多个泛型的委托定义，最后的参数的数据类型是函数的返回值类型，需要保持一致，签名的是形参。
```csharp
public class SystemFunc : MonoBehaviour  
{  
Func<string> m_Func1;  
Func<int, string> m_Func2;  
// Start is called before the first frame update  
void Start()  
{  
m_Func1 = Show1;  
m_Func2 = Show2;  
string a = m_Func1.Invoke();  
Debug.Log(a);  
string b = m_Func2.Invoke(10);  
Debug.Log(b);  
}  
  
// Update is called once per frame  
void Update() { }  
string Show1()  
{  
return "Show1";  
}  
string Show2(int num)  
{  
return "数字是" + num.ToString();  
}  
}
```

##### 匿名方法

没有名字的方法为匿名方法

```csharp
public class BoardCast : MonoBehaviour  
{  
Action m_Action;  
  
// Start is called before the first frame update  
void Start()  
{  
//匿名函数，不在外部声明函数名，直接写函数方法  
m_Action = delegate { Debug.Log("匿名函数执行"); };  
}  
  
// Update is called once per frame  
void Update() { }  
}
```


##### event事件

event事件本身就是一种委托  
只允许作为类的成员变量，且仅在类的内部使用才可以。外部不得直接调用。  
作为A类的成员变量event委托只能在声明类中赋值，在其他类中添加订阅只能+=，删除只能-=。  
**_订阅的时候是添加方法。_**

##### 多播委托

指一个委托中注册多个方法，注册方法时使用加号或者减号实现