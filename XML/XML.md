# 1、概念

Extersible Markup Language 可扩展标记语言

**可扩展**：标签都是自定义的

**功能**：存储数据，作为配置文件使用，可以在网络中传输

**与HTML的区别**：

1. XML标签是自定义的，HTML标签是预定义的
2. xml的语法严格，HTML语法松散
3. xml是存数据的，HTML是展示数据的

# 2、语法

**后缀名**：.xml

xml第一行必须定义文档声明

```xml
<?xml version="1.0" ?>
```

xml文档中有且仅有一个根标签

属性值必须使用引号

标签必须正确关闭

xml标签区分大小写

## 组成部分

### 文档声明

**格式**

```xml
<?xml 属性列表 ?>
```

**属性列表**

1. version：版本号，必须写
2. encoding：编码方式，默认值ISO-8859-1
3. standalone：是否独立，取值为yes和no

### 指令

结合CSS，可以控制标签样式

```xml
<?xml-stylesheet type="text/css" href="a.css" ?>
```



### 标签

标签名是自定义的

**规则**

1. 数字不能开头
2. 可以包含字母、数字以及其他的字符
3. 名称不能包含空格
4. 不能以xml开头

### 属性

键值对构成，属性值要用引号

id值唯一

### 文本内容

**CDATA区**：在该区域中的内容会被原样展示

```cml
<![CDATA[
	数据
]]>
```

# 3、约束

 规定xml文档书写规则

## 分类

DTD：一种简单的约束技术，有很多问题

Schema：一种复杂的约束技术

## DTD

**内部dtd**：将约束规则定义在xml文档中

**外部dtd**：将约束规则定义在外部的dtd文件中

​	本地：

```xml
<!DOCTYPE 根标签名 SYSTEM "dtd文件的位置">
```



​	网络：

```xml
<!DOCTYPE 根标签名 PUBLIC "dtd文件名" "dtd文件的位置URL">
```

## Schema

后缀为xsd

# 4、解析

**解析**：操作xml文档，将文档中的数据读取到内存中

**写入**：将内存中的数据保存到xml文档中，持久化存储

## 解析xml的方式

### DOM

将标记语言文档一次性加载进内存，在内存中形成DOM树

**优点**：操作方便，可以对文档进行CRUD的所有操作

**缺点**：占内存

### SAX

逐行读取，基于事件驱动，

**优点**：基本不占内存

**缺点**：只能读取

## 常见解析器

### JAXP

sun公司提供的，支持dom和sax

### DOM4J



### Jsoup

本来用于解析HTML

### PULL

安卓内置的解析器，sax方式

## Jsoup简介

**步骤**

1. 导入jar包
2. 获取Document对象
3. 获取对应的标签（Element对象）
4. 获取数据

**Jsoup**：工具类，可以解析html或xml文档，返回Document

​	parse方法

**Document**：文档对象，代表内存中的DOM树

​	获取Element对象

**Elements**：元素Element对象的集合，可以当做ArrayList<Element>来使用

**Element**：元素对象

​	获取子元素对象

​	

​	获取属性值

​		attr方法，根据属性名称获取属性值

​	获取文本内容

​		text()，获取文本内容

​		html()，获取标签体的所有内容(包括子标签的字符串内容)

**Node**：节点对象

​	是Document和Element的父类，

# 5、快捷查询方式

## selector：选择器

使用的方法： Elements  select(String  cssQuery)

​	语法：参考Selector中定义的类

## XPath

​	使用Jsoup的Xpath需要额外jar包