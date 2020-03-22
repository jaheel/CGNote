# 3 计算机图形软件

* 专用软件包

  > 为非程序员设计的，使得他们在某些应用中能用来生成图形、表格而不关心显示所需的图形函数

* 通用编程软件包

  > 可用于高级程序设计语言的图形函数库
  >
  > 通用图形程序设计软件包有：
  >
  > ​		GL(Graphics Library)、OpenGL、VRML(Virtual-Reality Modeling Language,虚拟现实建模语言)、Java2D、Java3D等
  >
  > ​		**计算机图形应用编程接口**(CG API)

## 3.1 坐标表示

建模坐标系(modeling coordinate)

局部坐标系(local coordinate)

主坐标系(master coordinate)

世界坐标系(world coordinate)

观察流水线(viewing pipeline)

规范化坐标系(normalized coordinate)

## 3.2 图形功能

**图形输出图元**(graphics output primitive)：图形的基本构造块

> 包括字符串和几何成分

**属性**(attribute)：输出图元的特性

> 包括颜色设定、线型、文本格式、区域填充图案 等

**几何变换**(geometric transformation)

> 改变场景中一个对象的大小、位置或方向

**建模变换**(modeling transformation)

> 将建模坐标系中给出的对象描述组织成场景

**观察变换**(viewing transformation)

> 指定将要显示的视图、使用的投影类型及在输出显示区域出现的范围

**输入函数**(input function)

> 控制和处理来自交互设备的数据流

## 3.3 软件标准

可移植性

* 第一个标准(1984年)：图形核心系统(Graphical Kernel System, **GKS**)

* 第二个标准：程序员级的分层结构交互图形标准(Programmer's Hierarchical Interactive Graphics Standard, **PHIGS**)

  > :对GKS的扩充
  >
  > 提供层次式对象建模、颜色设定、表面绘制和图形管理等功能
  >
  > PHIGS+ : 提供PHIGS所没有的三维表面明暗处理功能

* OpenGL

  > 专为高效处理三维应用而设计
  >
  > 按z坐标为0的三维特例来处理二维场景描述

## 3.5 OpenGL简介

OpenGL基本函数库用来描述图元、属性、几何变换、观察变换和其他操作

硬件无关

* OpenGL基本库(也称核心库)

  > 函数名以gl为前缀

* OpenGL实用函数(OpenGL Utility, GLU)

  > 函数名以glu开头
  >
  > 可以设置观察和投影矩阵
  >
  > 利用线条和多边形近似法来描述复杂对象
  >
  > 使用线性近似法显示二次曲线和样条曲线，处理表面绘制操作
  >
  > ...

* OpenGL的X窗口系统扩充(OpenGL Extension to the X Window System, GLX)

  > 以glX为前缀的函数
  >
  > Apple系统：Apple GL(AGL)
  >
  > Windows系统：WGL

* OpenGL实用函数工具包(OpenGL Utility Toolkit, GLUT)

  > 库函数以glut为前缀
  >
  > 提供了与任意屏幕窗口系统进行交互的函数库
  >
  > （包含了描述与绘制二次和样条曲线及曲面的方法）



**头文件**：

```c++
#include <windows.h>
#include <GL/gl.h>
#include <GL/glu.h>
//如果使用GLUT处理窗口管理操作，就不需要引入gl.h和glu.h
#include <GL/glut.h>
```



GLUT进行显示窗口管理：

```c
glutInit(&argc,argv);
glutCreateWindow("Test");
glutDisplayFunc(lineSegment);//将图赋给显示窗口
glutMainLoop();//所有已创建的显示窗口连同其中的图形内容将被激活
glutInitWindowPosition(50,100);//窗口离左上角的x,y距离
glutInitWindowSize(400,300);//显示窗口大小
glutInitDisplayMode(GLUT_SINGLE|GLUT_RGB);//设置显示窗口的缓存和颜色模型等选项（单个缓存、RGB模型）

```

