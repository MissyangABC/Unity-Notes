
# Rider简介
- JetBrains Rider 是一款基于 IntelliJ 平台和 ReSharper 的跨平台 .NET IDE。
- 它主要用于Unity的C#脚本撰写（同时内置了其他相关功能），且近年来对于UE的支持也在不断完善，另外Rider对于Unity的支持度是逐渐增加的，Rider官方也在积极适配Unity。
- 在Rider出现之前，微软几乎垄断了Unity中的C#脚本编写并强推VisualStudio（Unity之前还有过一段时间的Mono编译器，后期被微软收购），自从 2017年JetBrains Rider问世以后，这种被VS垄断的局面正在逐渐被改变，Rider作为一款付费产品却依旧能够从之前垄断市场，且拥有免费社区版本的VS手中抢占一定份额，必然是有它出彩的点。
- 总的来说，Rider是一款适配于游戏开发人员的IDE，当然，也不否认VS的功能强大，本文只是简单介绍Rider，说明Rider也是一款可是使用的Unity IDE。另外由于个人能力尚浅，本文主要用于梳理知识，有误之处劳烦读者指出，不甚感激。
- [JetBrains Rider 官网](https://www.jetbrains.com/zh-cn/lp/dotnet-unity/)

# Rider 的功能

- 集成了 Resharper 的全部功能，同时还包括 dotPeek、dotCover、dotMemory 等辅助功能；
- 集成了 IntelliJ Platform 的绝大多数全部功能；
- 和 VS 相比，占用体积小，安装非常迅速，也不容易出现软件依赖和卸载的难题；
- Rider 天生是跨平台的，同时支持 Windows/Linux/MacOS；
- Rider 天生是 64 位的（事实上只有 64 位）。
- Rider 提供 2200 多种活跃代码检查，数百种来自 ReSharper 的上下文操作和重构，并与 IntelliJ 平台可靠的 IDE 功能相结合。 除了丰富的功能集，Rider 的设计宗旨是轻量级、响应式。
- 在Unity中，得益于集成的双向通信，您可以切换进出 Play 模式，暂停和逐帧执行，而无需离开 Rider！工具栏包含游戏视图按钮 Play、Pause 和 Step，分别对应 Unity 编辑器中的相同按钮，并且与 Unity 编辑器中的按钮控制相同的行为。状态栏上的小 Unity 图标将指示 Unity 编辑器是已经连接、正在刷新还是处于 Play 模式。在 Rider 处于 Edit 模式时应用的任何变更都将立刻提交给 Unity 编辑器。
- [Rider官方完整版功能介绍](https://www.jetbrains.com/zh-cn/rider/features/)

# Rider的安装
![下载界面](https://img-blog.csdnimg.cn/810584b887b84961b35f029796d1a78a.png)
* 拥有三个系统的安装包，根据自己的系统自行选择下载
* 或者选择下方的Toolbox App 一站式管理JetBrains 软件，并且一键更新

#### Rider 需要注册账号并付费使用
![价格](https://img-blog.csdnimg.cn/b7340180b4be40b6b38a41864797dd2b.png)
* Rider的按年结算的用户或者连续购买了12个月的用户，会获得一个永久版本回退许可证，此处转载B站用户的详细介绍：[Rider永久回退许可证](https://www.bilibili.com/read/cv19652710)  作者：iSaika  
# 插件推荐
![Rider](https://img-blog.csdnimg.cn/c43e369b16f943de819c370495c38f12.png)
* 安装完成后，会默认使用英文，但是官方配置了中文包，看个人习惯而定。
#### 两套UI界面
![界面](https://img-blog.csdnimg.cn/b9ac8a2e248b42a0876c9f64cd7bb513.png)
* 经典UI
* 左下角Unity按钮可以同步Unity的Console控制台
* TODO作为一个备注，能够在可能需要修改的位置，或者未完成的位置做标记，以便后期寻找
* 结构面板可以观察该文件的类和方法
* 右方有数据库界面

![在这里插入图片描述](https://img-blog.csdnimg.cn/f1ff8d3b63eb457d955e399b912ff365.png)
* 新版UI
* 左下角Unity按钮可以同步Unity的Console控制台
* TODO作为一个备注，能够在可能需要修改的位置，或者未完成的位置做标记，以便后期寻找
* 结构面板可以观察该文件的类和方法
* 右方有数据库界面
#### 个人插件推荐
![插件](https://img-blog.csdnimg.cn/dee6332d418544eb81a840e52e1fb9d4.png)
* 第一个ignore，可以快捷添加ignore文本，主要用于项目上传云端，忽略相关后缀名文件，比如不上传.unitypackage的文件
* 第三个是中文语言包
* 第四个CodeGlance Pro，是用来快速定位代码片段，可以在编辑器窗格中显示类似于Sublime中的放大概览或最小地图。小地图允许快速滚动，让你直接跳到代码的各个部分。
* 第五个Key Promoter X，用于强化快捷键记忆，当你使用鼠标进行了拥有快捷键的操作行为时，会在右下角提醒你，该操作的快捷键是什么。
* 第六个Translation，是一个软件内部的翻译软件，当你遇到某个类名或者方法的英文不会时，即时翻译。
* [Rider官方插件库](https://plugins.jetbrains.com/)，可以在其中挑选你喜欢的插件，例如常用的主题，关键词搜索Theme，笔者使用主题为Gradianto。![在这里插入图片描述](https://img-blog.csdnimg.cn/bbffb524f7f24c7abd36beb37a8ad96a.png)
# 设置简析
#### 常用快捷键
* 全局搜索，[ Shift + Shift ]，可以得到一个快速搜索界面，可以搜索类，方法，变量，甚至设置面板中的功能![搜索类](https://img-blog.csdnimg.cn/6e9df79dd7164b5bb25013bf29110c19.png)![方法](https://img-blog.csdnimg.cn/2e2754710d33451b9715f796ec671c3e.png)![设置操作](https://img-blog.csdnimg.cn/3c1b6dd01da840699214d7f6abe96920.png)
* 快速修复插入，[ Alt + Enter ]，当遇到报错问题时，可以快速提示修改方案，在没有错误时，也能够补全相关代码，同时对于代码内容可以同义转换，可以选择更加简洁的代码书写，优化自己的编程习惯
![修复](https://img-blog.csdnimg.cn/f21b62b912f848699b7af96f084e8820.png)
![修复](https://img-blog.csdnimg.cn/3564401522e84836bc004a25771d694a.png)
* [ Ctrl+Shift+/ ] 快速注释代码块
* [ Ctrl+Shift+O ] 翻译插件的快捷方式（如果你安装了推荐的插件的话）
* [ Ctrl+Shift+ 方向键上/下 ] 快速整体地移动代码语句，例如，将一个方法整体向上或者向下，还不是只移动当前行
* [ Ctrl+Alt+ Shift+ 方向键左/右 ] 快速整体地改变语句层级，例如，将一个方法快速修改层级。
* [ Ctrl+Alt+L ] 格式化代码，让代码以一定的规则分布，优化代码可读性
* 善用Tab键，Rider默认快捷键中对于Tab的使用度很高。
* 建议初学者前几天多多尝试教程项目，每天过一遍教程，多练习几次，熟悉快捷键之后，可以更快地书写代码，整体编程体验也会提高。初学者主要是圈出的几个项目进行练习。
![教程](https://img-blog.csdnimg.cn/32dc44e235ed475cb9efafd3f37c8928.png)
#### 推荐详细查看的设置
* 检查严重性，这个设置是对你的代码进行实时分析，然后分为提示，建议，警告，错误四个等级，可以自己DIY配置你最喜欢的代码方案。
![检查严重性](https://img-blog.csdnimg.cn/4e0b8278c2d245a487c4e828cecfb4bd.png)
* 代码样式，可以修改你认为合适的变量名设置，一旦没有符合规则的变量名出现，会做出提示，可以对代码进行完整的规范化，增加可读性，例如，私有成员变量名加上前缀(m_)可以快速分辨它的类型，前缀来自成员变量(member variable) 
![代码样式](https://img-blog.csdnimg.cn/cf9ac23f4cd94cadb55f7f4ace1204e8.png)
* 实时模板，可以DIY你自己想要的模板，如果你自己有某个编码习惯，或者感觉有重复代码，或者你有自己喜欢的代码书写方式，都可以设置自己的模板
![实时模板](https://img-blog.csdnimg.cn/780e5b32d55f4ce39710929f410e3d04.png)
* 按键映射，首先可以调整快捷键模板，例如可以直接套用VS快捷键模板，Rider的快捷键操作设置很丰富，可以选择自己常用的行为标注上快捷键，习惯后一定会非常有用。
![快捷键](https://img-blog.csdnimg.cn/b0bd03bb7fea4052a045f5ec1f00ebfe.png)
# 总结
以上就是分享的所有内容，个人选择Rider的第一原因其实是整体UI的颜值，相对于VS会更加顺眼，后面使用的过程中发现更多的优秀的点。同时它相对于VS更加轻量级，个人觉得，VS相当于一所综合性大学，各个能力都涵盖了，且能力均不错，而Rider属于拥有几个优势专业的大学，其他功能一般，但是优势点会做的比较完善。另外，开发者通常两种都会使用，根据具体情况选择。最后，内容中Rider的使用十分浅显，它还有非常多的功能待挖掘使用，个人也在不断学习中！









​

