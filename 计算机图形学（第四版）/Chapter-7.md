# 二维几何变换

几何变换(geometric transformation)

> 应用于对象几何描述并改变它的位置、方向或大小的操作

## 7.1 基本二维几何变换

平移、旋转和缩放

### 7.1.1 二维平移

$$
x^{'}=x+t_x, y^{'}=y+t_y \tag{7.1}
$$

$(t_x,t_y)$为平移向量(translation vector)或位移向量(shift vector)

### 7.1.2 二维旋转

指定一个**旋转轴**(rotation axis)和一个**旋转角度**(rotation angle)，可以进行一次**旋转**(rotation)变换。

旋转角$\theta$

旋转点$(x_r,y_r)$
$$
x^{'}=rcos(\phi + \theta)=r cos\phi cos\theta - r sin\phi sin \theta \\
y^{'}=rsin(\phi + \theta)=r cos\phi sin\theta + r sin\phi cos \theta \tag{7.2}
$$
旋转矩阵：
$$
R=
\begin{bmatrix}
cos \theta & -sin\theta\\\\
sin \theta & cos \theta
\end{bmatrix}
$$

### 7.1.3 二维缩放

改变一个对象的大小，可使用**缩放**(scaling)变换。

简单的二维缩放操作可通过将缩放系数(scaling factor)$s_x$和$s_y$与对象坐标位置$(x,y)$相乘而得：
$$
x^{'}=x \cdot s_x, y^{'}=y \cdot s_y \tag{7.3}
$$
矩阵形式:
$$
\begin{bmatrix}
x_{'}\\\
y_{'}
\end{bmatrix}

=

\begin{bmatrix}
s_x & 0 \\\
0 & s_y
\end{bmatrix}

\cdot

\begin{bmatrix}
x \\\
y
\end{bmatrix}
$$

## 7.2 矩阵表示和齐次坐标

每个基本变换（平移、旋转和缩放）都可以表示为普通矩阵形式
$$
P^{'}=M_1 \cdot P+M_2 \tag{7.4}
$$
坐标位置$P^{'}$和$P$表示为列向量，矩阵$M_1$是一个包含乘法系数的$2X2$矩阵，$M_2$是包含平移项的两元素列矩阵。

可改进：重组$(7.4)$以消除$M_2$中与平移项相关的矩阵加法。

### 7.2.1 齐次坐标

将2x2矩阵扩充为3x3矩阵，可把二维几何变换的乘法和平移项组合成单一矩阵表示。

所有变换公式可表达为矩阵乘法。

二维$(x,y)$扩充到三维$(x_h,y_h,h)$，称为**齐次坐标**(homogeneous coordinate)

**齐次参数**(homogeneous parameter) h 是一个非零值
$$
x=\frac {x_h}{h},y=\frac{y_h}{h} \tag{7.5}
$$
普通二维齐次坐标可表示为$(h \cdot x,h\cdot y,h)$。



### 7.2.2 二维平移矩阵

$$
\begin{bmatrix}
x^{'}\\\
y^{'}\\\
1
\end{bmatrix}
=
\begin{bmatrix}
1&0&t_x\\\
0&1&t_y\\\
0&0&1
\end{bmatrix}

\cdot

\begin{bmatrix}
x\\\
y\\\
1
\end{bmatrix}
\tag{7.6}
$$

简写：
$$
P^{'}=T(t_x,t_y) \cdot P
\tag{7.7}
$$


### 7.2.3 二维旋转矩阵

$$
\begin{bmatrix}
x^{'}\\\
y^{'}\\\
1
\end{bmatrix}
=
\begin{bmatrix}
cos\theta & -sin\theta & 0\\\
sin\theta & cos\theta & 0\\\
0 & 0 & 1
\end{bmatrix}
\cdot
\begin{bmatrix}
x\\\
y\\\
1
\end{bmatrix}

\tag{7.8}
$$

简写：
$$
P^{'}=R(\theta) \cdot P \tag{7.9}
$$

### 7.2.4 二维缩放矩阵

$$
\begin{bmatrix}
x^{'}\\\
y^{'}\\\
1
\end{bmatrix}
=
\begin{bmatrix}
s_x & 0 & 0\\\
0 & s_y & 0\\\
0 & 0 & 1
\end{bmatrix}
\cdot
\begin{bmatrix}
x\\\
y\\\
1
\end{bmatrix}
\tag{7.10}
$$

简写:
$$
P^{'}=S(s_x,s_y)\cdot P \tag{7.11}
$$

## 7.3 逆变换

$$
T^{-1}=
\begin{bmatrix}
1&0& -t_x\\\
0&1& -t_y\\\
0&0&1
\end{bmatrix}
\tag{7.12}
$$

$$
R^{-1}=
\begin{bmatrix}
cos\theta & sin \theta & 0\\\
-sin \theta & cos \theta & 0\\\
0 & 0 & 1
\end{bmatrix}
\tag{7.13}
$$

$$
S^{-1}=
\begin{bmatrix}
\frac{1}{s_x} & 0 & 0 \\\
0 & \frac{1}{s_y} & 0 \\\
0 & 0 & 1
\end{bmatrix}
\tag{7.14}
$$

## 7.4 其他二维变换

### 7.4.1 反射

产生对象镜像的变换称为**反射**(reflection)
$$
\begin{bmatrix}
1&0&0\\\
0&-1& 0\\\
0 & 0 & 1
\end{bmatrix}
$$

### 7.4.2 错切

**错切**(shear)：使对象形状发生变化的变换
$$
\begin{bmatrix}
1& shx & 0\\\
0 & 1 & 0 \\\
0 & 0 & 1
\end{bmatrix}
$$
