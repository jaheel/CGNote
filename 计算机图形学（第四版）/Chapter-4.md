# 输出图元

**图元**(primitive)：图形软件包中用来描述各种图形元素的函数（图形输出原语 graphics output primitive）

**几何图元**(geometric primitive)：描述对象几何要素的输出图元

## 1 画点函数

```c
//i(整数)、s(短整数)、f(浮点数)、d(双精度浮点数);v(向量)
glBegin(GL_POINTS);
	glVertex2i(50,100);
	glVertex3f(-45.2,56.2,54.10);
glEnd();

int point1[]={50,100};
glVertex2iv(point1);

wcPt2D pointPos;
pointPos.x=120.75;
pointPos.y=45.30;
glVertex2f(pointPos.x,pointPos.y);
```

## 2 画线函数

```c
gleBegin(GL_LINES);
	glVertex2iv(p1);
	glVertex2iv(p2);
	glVertex2iv(p3);
glEnd();
//GL_LINE_STRIP 折线
//GL_LINE_LOOP封闭折线
```

## 3 曲线函数

1. 核心库：包含 显示Bezier样条的功能，由一组离散点定义的多样式

2. GLU包含：球面和柱面等三维曲面函数及生成有理B样条的函数（包含简化Bezier曲线的样条曲线的总集）
3. GLUT：显示某些三维曲面（如球面、锥面和其他形体）的函数



多次折线也可形成曲线

## 4 多边形填充区

凸(convex)多边形：一个多边形的所有内角均小于180度

凹(concave)多边形：不是凸多边形的多边形

> 将凹多边形分割成一组凸多边形，再实现填充，提高效率

退化多边形(degenerate polygon)：描述共线或重叠坐标位置的顶点集

### 4.1 识别凹多边形

1. 至少有一个内角大于180度
2. 凹多边形某些边的延长线会与其他边相交且有时一对内点之间的连线会与多边形边界相交



识别算法：

1. 每一条边建立一个向量，可使用相邻边的叉积来测试凹凸性

   > 凸多边形的所有向量叉积均同号
   >
   > 若有负值，可确定为凹多边形

2. 观察多边形顶点位置与每条边延长线的关系

   > 如果有些顶点在某一边延长线的一侧而其他一些顶点在另一侧，则该多边形为凹多边形



### 4.2 分割凹多边形

使用边向量和边叉积来完成.

向量方法：

1. 形成边向量，给定相继的向量位置$V_k$和$V_{k+1}$，定义边向量：

$$
E_k=V_{k+1}-V_k
$$

2. 按多边形边界顺序计算连续的边向量的叉积、

   > 一些为正，一些为负，则为凹多边形
   >
   > 否则为凸多边形

### 4.3 多边形表

几何数据表（分为三个表引起坐标信息重复）

1. 顶点表

   > $V_1:x_1,y_1,z_1$

2. 边表

   > $E_1:V_1,V_2$

3. 面片表

   > $S_1:E_1,E_2,E_3$

扩充边表使其包含指向面片表的指针（提高信息的提取速度）

> $E_1:V_1,V_2,S_1$

### 4.4 前向面与后向面

前向面(front face)：可见或朝外的一侧

后向面(back face)：向着对象内部的一侧
$$
Ax+By+Cz+D<0,点(x,y,z)在平面后方
$$

$$
Ax+By+Cz+D>0,点(x,y,z)在平面前方
$$

## 5 多边形填充区函数

```c
int vertex1[]={200,100};
int vertex2[]={50,250};
glRectiv(vertex1,vertex2);
//正方形填充


//GL_POLYGON 单个凸多边形
//GL_TRIANGLES 多个不相连的三角形
//GL_TRIANGLE_STRIP 多个相连的三角形
//GL_TRIANGLE_FAN 多个相连的三角形
glBegin(GL_POLYGON);
	glVertex2iv(p1);
	glVertex2iv(p2);
	glVertex2iv(p3);
	glVertex2iv(p4);
	glVertex2iv(p5);
	glVertex2iv(p6);
glEnd();
```

## 6 像素阵列函数

位图函数：

```c
glBitmap(width,height,x0,y0,xOffset,yOffset,bitShape);
/*	width:列数
	height:行数
	bitShape:每一元素赋值为0或1
	x0,y0:矩形阵列“原点”位置
	xOffset,yOffest:位图显示后更新帧缓存当前光栅位置的坐标位移
	*/
```

像素图函数：

```c
glDrawPixels(width,height,dataFormat,dataType,pixMap);

glDrawPixels(128,128,GL_RGB,GL_UNSIGNED_BYTE,colorShape);
```



## 7 附则

103页，函数及子程序小结