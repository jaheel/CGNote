# 三维几何变换

在二维方法的基础上扩充了z坐标而得

## 9.1 三维平移

$$
\begin{bmatrix}
x^{'}\\\
y^{'}\\\
z^{'}\\\
1
\end{bmatrix}
=
\begin{bmatrix}
1&0&0&t_x\\\
0&1&0&t_y\\\
0&0&0&t_z\\\
0&0&0&1
\end{bmatrix}
\cdot
\begin{bmatrix}
x\\\
y\\\
z\\\
1
\end{bmatrix}
$$

## 9.2 三维旋转

$$
\begin{bmatrix}
x^{'}\\\
y^{'}\\\
z^{'}\\\
1
\end{bmatrix}
=
\begin{bmatrix}
cos\theta&-sin\theta&0&0\\\
sin\theta&cos\theta&0&0\\\
0&0&1&0\\\
0&0&0&1
\end{bmatrix}
\cdot
\begin{bmatrix}
x\\\
y\\\
z\\\
1
\end{bmatrix}
$$

## 9.3 三维缩放

$$
\begin{bmatrix}
x^{'}\\\
y^{'}\\\
z^{'}\\\
1
\end{bmatrix}
=
\begin{bmatrix}
s_x&0&0&0\\\
0&s_y&0&0\\\
0&0&s_z&0\\\
0&0&0&1
\end{bmatrix}
\cdot
\begin{bmatrix}
x\\\
y\\\
z\\\
1
\end{bmatrix}
$$

# 三维观察

