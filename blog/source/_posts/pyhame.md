---
title: pyhame
slug: storywriter/upgrade_log
grammar_mindmap: true
grammar_code: true
grammar_decorate: true
grammar_mathjax: true
tags: python,小书匠

renderNumberedHeading: true
grammar_cjkRuby: true

---

* [pygame基础学习](#pygame基础学习)
			* [pygame最小开发框架](#pygame最小开发框架)
			* [引用部分](#引用部分)
			* [初始化](#初始化)
			* [处理](#处理)
			* [刷新](#刷新)

--- 

# pygame基础学习

#### pygame最小开发框架
- 引用；初始；处理；刷新   

![最小框架](https://github.com/cfxcheer/cfxcheer.github.io/blob/master/img/%E5%BE%AE%E4%BF%A1%E5%9B%BE%E7%89%87_20200319152305.jpg?raw=true)

* 最小游戏框架代码
```python
#hello wordld game
import pygame,sys

pygame.inint()
screen=pygame.display.set_mode((600,400))
pygame.display.set_caption("pygame游戏")

while True:
	for event in pygame.event.get():
		if event.type==pygame.QUIT:
			sys.exit)(

pyame.display.update()
		
```
---

#### 引用部分

* 引入pygame和sys
`import pygame,sys`

* sys库
sys是python标准库（标准模块）,提供有关python运行环境的变量和函数

* sys模块的常见函数
	* sys.exit([arg]):程序中间的退出，arg=0位正常退出   。
	* sys.getdefaultencoding():获取系统当前编码，一般默认为asscii。   
	* sys.path:获取当前指定模块收索路径的字符串集合，可以将写好的模块放在得到的某个路径下，就可以在程序中import时正确找到。
	* sys.platform:获取当前系统平台。


---

#### 初始化
* 初始化
 `pygame.init()`初始化，其实就是检查，电脑上一需要的硬件调用接口，基础功能是否有问题。如果有，他会在程序运行之前就反馈给你，方便你进行排查和规避。
    
	
 ![初始化](https://github.com/cfxcheer/cfxcheer.github.io/blob/master/img/%E5%BE%AE%E4%BF%A1%E5%9B%BE%E7%89%87_20200319155448.jpg?raw=true)  返回值（6，0），这是什么？   
他的函数原型：init()->(numpass,numfail)。这个函数的返回值是一个元组，第一个数是成功的个数，第二个是失败的个数。
（6，0）说明初始化的时候导入了6个朋友pygame模块，失败为0系统正常。init的时候导入了6个常用的pygame模块。


* [display模块](https://blog.csdn.net/Lingdongtianxia/article/details/86612472)
	1.pygame.display：控制窗口和屏幕的pygame模块
	2.pygame.display.set_mode：初始化窗口或屏幕以进行显示。通常，游戏中需要加载大量的位图，pygame中自带了一些类和函数可以帮助我们轻松的搞位图加载和绘制。screen=pygame.display.set_mode()这个函数会返回一个Suface对象，它是位图的一种。Suface对象有一个名为bit的方法，它可以绘制位图.
	3.pygame.display.set_caption：设置当前窗口标题。

---

####  处理
```python
while True:
	for event in pygame.event.get():
		if event.type==pygame.QUIT:
			sys.exit()
```
这是一个永真的无限循环，知道python运行时退出结束
* pygame.event  用于处理事件与事件队列的 Pygame 模块。
* Pygame 通过事件队列控制所有的事件消息。该模块中的程序帮用户管理事件队列。输入队列很大程度依赖于 pygame 的 display 模块。如果 display 没有被初始化，显示模式没有被设置，那么事件队列就还没有开始真正工作。
* pygame.event.get()函数---—从队列中获取事件，并在队列中删除该事件
*  event type------事件类型。从pygame事件列表中遍历事件，如果触发事件的类型为pygame的预定事件（如：QUIT），那么执行退出操作。
pygame.QUIT 是Pygame中定义的退出事件常量

#### 刷新
`pygame.display.update()`对显示窗口进行更新，默人窗口全部重绘。




   

