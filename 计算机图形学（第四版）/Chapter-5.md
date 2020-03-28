# 图元的属性

属性参数(attribute parameter)

> 任何影响图元显示方法的参数
>
> ​		例如：颜色、大小

状态系统(state system)或状态机(state machine)

> 维护属性和其他参数当前值表的图形系统

状态变量(state variable)或状态参数(state parameter)

> 输出图元的属性和当前帧缓存位置等其他参数

## 5.1 颜色和灰度

RGB颜色分量

颜色表(color map)

> 提供“合理”数量颜色，不要求大容量帧缓存
>
> * 当颜色表中某项值改变时，所有使用该颜色索引的像素都将改成新颜色



灰度(gray scale)

> 相同量的红色、绿色、蓝色，结果为灰色
>
> ​		靠近0：暗灰色
>
> ​		靠近1：亮灰色
>
> 应用：增强黑白照片、产生可视化效果

## 5.2 颜色函数

颜色显示模型(color display mode)

```c
glutInitDisplayMode(GLUT_SINGLE|GLUT_RGB);
```

RGB模式：红色、绿色、蓝色分量

RGBA模式：RGB + $\alpha$系数（颜色调和）



1. 颜色指定：

   ```c
   glColor3f(0.0,1.0,1.0);
   glColor3fv(colorArray);
   glColor3ub(0,255,255);
   ```

2. 颜色索引模式：

   ```c
   glIndex* (colorIndex);
   ```

   

## 5.3 点属性函数

```c
glPointSize(size);
```

## 5.4 线属性

颜色

线宽

```c
glLineWidth(width);
```

线型

```c
glLineStipple(repeatFactor,pattern);
```

## 5.5 反走样函数

走样：低频取样（不充分取样）而造成的信息失真

反走样：校正不充分取样过程

```c
glEnable(primitiveType);//激活反走样子程序,GL_POINT_SMOOTH,GL_LINE_SMOOTH,GL_POLYGON_SMOOTH
glEnable(GL_BLEND);//激活颜色调和
```



## 5.6 附则

P133