# XML - 可扩展标记语言(EXtensible Markup Language)

## 1.什么是XML

- XML 指*可扩展标记语言*（EXtensible Markup Language），**跨平台**

- XML 是一种*标记语言*，类似 HTML

- XML 被设计用来*描述数据*

- XML 标签没有被预定义。您需要**自行定义标签**。

  用来标记HTML文档的标签是预定义的的HTML文件作者只能使用在HTML标准（如<P>，<H1>等）定义的标签。**XML允许作者来定义他/她自己的标签和他/她自己的文档结构**。

  XML 被设计用来传输和存储数据， 焦点是数据的内容 ；HTML 被设计用来显示数据， 焦点是数据的外观 。

- XML **使用文件类型声明（DTD）或者 XML Schema 来描述数据**。

- 带有 DTD 或者 XML Schema 的 XML 被设计为具有*自我描述性*。

- XML 是一个 W3C 标准

## 2.XML 用途

- XML 把数据从 HTML 分离

  如果您需要在 HTML 文档中显示动态数据，那么每当数据改变时将花费大量的时间来编辑 HTML。

  通过 XML，数据能够存储在独立的 XML 文件中。这样您就可以专注于使用 HTML/CSS 进行显示和布局，并确保修改底层数据不再需要对 HTML 进行任何的改变。

  通过使用几行 JavaScript 代码，您就可以读取一个外部 XML 文件，并更新您的网页的数据内容。

- XML **简化数据共享**

  在真实的世界中，计算机系统和数据使用不兼容的格式来存储数据。

  XML 数据以纯文本格式进行存储，因此提供了一种独立于软件和硬件的数据存储方法。

  这让创建不同应用程序可以共享的数据变得更加容易。

- XML **简化数据传输**

  对开发人员来说，其中一项最费时的挑战一直是在互联网上的不兼容系统之间交换数据。

  由于可以通过各种不兼容的应用程序来读取数据，以 XML 交换数据降低了这种复杂性。

- XML **简化平台变更**

  升级到新的系统（硬件或软件平台），总是非常费时的。必须转换大量的数据，不兼容的数据经常会丢失。

  XML 数据以文本格式存储。这使得 XML 在不损失数据的情况下，更容易扩展或升级到新的操作系统、新的应用程序或新的浏览器。

## 3.XML语法

-  XML 必须**包含根元素**，它是所有其他元素的父元素 

- XML 声明文件的可选部分，如果存在需要放在文档的第一行，如下所示：

  ```xml
  <?xml version="1.0" encoding="utf-8"?>
  ```

- 在 HTML 中，某些元素不必有一个关闭标签，如<p>、<br>等。在 XML 中，省略关闭标签是非法的。所有元素都**必须有关闭标签**。

-  XML 标签对**大小写敏感**。 

-  在 XML 中，所有元素都**必须彼此正确地嵌套** 

- 与 HTML 类似，XML 元素也可拥有属性（名称/值的对）。在 XML 中，**XML 的属性值必须加引号。**

- 在 XML 中，一些字符拥有特殊的意义。

  如果您把字符 "<" 放在 XML 元素中，会发生错误，这是因为解析器会把它当作新元素的开始。这样会产生 XML 错误， 为了避免这个错误，请用**实体引用**来代替 "<" 字符， 在 XML 中，有 5 个预定义的实体引用： 

  | 实体引用描述 | 实际内容 | 意义           |
  | ------------ | -------- | -------------- |
  | &引用符lt;   | <        | less than      |
  | &引用符gt;   | >        | greater than   |
  | &引用符amp;  | &        | ampersand      |
  | &引用符apos; | '        | apostrophe     |
  | &引用符quot; | "        | quotation mark |

- 在 XML 中编写注释的语法与 HTML 的语法很相似。

  ```xml
  <!-- This is a comment -->
  ```

-  HTML 会把多个连续的空格字符裁减（合并）为一个 ; 在 XML 中，**文档中的空格不会被删减。** 

- 在 Windows 应用程序中，换行通常以一对字符来存储：回车符（CR）和换行符（LF）。

  在 Unix 和 Mac OSX 中，使用 LF 来存储新行。

  **XML 以 LF 存储换行**。

## 4.XML元素

- XML 元素指的是从（且包括）开始标签直到（且包括）结束标签的部分。

  一个元素可以包含：

  - 其他元素
  - 文本
  - 属性
  - 或混合以上所有...

- XML 元素必须遵循以下命名规则：

  - 名称可以包含字母、数字以及其他的字符
  - 名称不能以数字或者标点符号开始
  - 名称不能以字母 xml（或者 XML、Xml 等等）开始
  - 名称不能包含空格

  可使用任何名称，没有保留的字词。

- 最佳命名习惯

  - 使名称具有描述性。使用下划线的名称很不错。

  - 名称应简短和简单。

  - 避免减号 "-" 、点"." 、冒号":" 字符。冒号会被转换为命名空间来使用（稍后介绍）。

  - XML 文档经常有一个对应的数据库，其中的字段会对应 XML 文档中的元素。有一个实用的经验，即使用数据库的命名规则来命名 XML 文档中的元素。

-  XML 元素是可扩展而不会被应用程序中断的，以携带更多的信息 

## 5.元素属性

 属性（Attribute）提供有关元素的额外信息。 属性值必须被引号包围，不过单引号和双引号均可使用。比如一个人的性别，person 元素可以这样写：

<person sex="female">

或者这样也可以：

<person sex='female'>

如果属性值本身包含双引号，您可以使用单引号，就像这个实例：

<gangster name='George "Shotgun" Ziegler'>

或者您可以使用字符实体：

<gangster name="George &quot;Shotgun&quot; Ziegler">

> **在 HTML 中，属性用起来很便利，但是在 XML 中，您应该尽量避免使用属性。如果信息感觉起来很像数据，那么请使用元素吧。** 

因使用属性而引起的一些问题：

- 属性不能包含多个值（元素可以）
- 属性不能包含树结构（元素可以）
- 属性不容易扩展（为未来的变化）

属性难以阅读和维护。请尽量使用元素来描述数据。而仅仅使用属性来提供与数据无关的信息。 