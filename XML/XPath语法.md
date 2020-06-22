# 1、选取节点

## 1.1、nodename:

​		选取此节点中所有子节点
​		eg：bookstore   选取bookstores下的所有子节点

## **1.2、/**

如果在最前面，代表从根目录选取，否则选择某节点下的子节点
		eg:/bookstore   选取根元素下所有的bookstore节点

## 1.3、//

从全局节点中选择节点，随便在哪个位置
		eg://book   从全局节点中找到所有book节点

## 1.4、@

选取某个节点的属性
		eg：//book[@price]   选取所有拥有price属性的book节点

# 2、谓语

中括号中的东西即谓语   

**注意**：索引从1开始

## 2.1、/bookstore/book[1]     

选取bookstore下的第一个子元素

## 2.2、/bookstore/book[last()]    

选取bookstore下的倒数第一个子元素

## 2.3、bookstore/book[position()<3]   

选取bookstore下前面两个子元素

## 2.4、//book[@price]    

选取拥有price属性的book元素

## 2.5、//book[@price=10]   

选取所有price属性等于10的book元素

## 2.6、模糊匹配：contains方法

​		eg：//div[contains@class,'fl')]
​			选取class属性中带有fl的div

# 3、通配符

## 3.1、*

匹配任意节点

**eg**：/bookstore/*      选取bookstore下的所有子元素

## 3.2、@*

匹配节点中的任意属性

eg：//book[@*]   选取所有带属性的book元素

# 4、选取多个路径

使用 | 

# 5、运算符

在位置中和xpath语法中可用     放在后面的是常用操作

|  :计算两个节点集
	+ ：加法
	- ：减法
	* ：乘法
	div ：除法
		= ：等于
		！=  ：不等于
		< ：小于
		<= :小于等于
		or : 或
		and ：与
	mod ：计算除法的余数