# MA265 - Spherical Coordinates

## Q28 Section 5.3 Spherical Coordinate Jacobian

### 题目

球坐标 $\rho,\phi,\theta$ 满足

$$
x=\rho\sin\phi\cos\theta
$$

$$
y=\rho\sin\phi\sin\theta
$$

$$
z=\rho\cos\phi
$$

求偏导数组成的 $3\times 3$ 矩阵，并证明它的 Jacobian 行列式为

$$
J=\rho^2\sin\phi
$$

因此球坐标中的体积微元为

$$
dV=\rho^2\sin\phi\,d\rho\,d\phi\,d\theta
$$

### 解答

这题的核心是：从变量 $(\rho,\phi,\theta)$ 变到变量 $(x,y,z)$ 时，体积会被一个比例因子放大或缩小，这个比例因子就是 Jacobian 行列式的绝对值。

所以我们要先写：

$$
J=\frac{\partial(x,y,z)}{\partial(\rho,\phi,\theta)}
$$

也就是下面这个矩阵的行列式：

$$
J=
\det
\begin{bmatrix}
\frac{\partial x}{\partial \rho} & \frac{\partial x}{\partial \phi} & \frac{\partial x}{\partial \theta}\\
\frac{\partial y}{\partial \rho} & \frac{\partial y}{\partial \phi} & \frac{\partial y}{\partial \theta}\\
\frac{\partial z}{\partial \rho} & \frac{\partial z}{\partial \phi} & \frac{\partial z}{\partial \theta}
\end{bmatrix}
$$

第一行来自 $x=\rho\sin\phi\cos\theta$。

对 $\rho$ 求偏导时，把 $\phi,\theta$ 当常数：

$$
\frac{\partial x}{\partial \rho}=\sin\phi\cos\theta
$$

对 $\phi$ 求偏导时，把 $\rho,\theta$ 当常数：

$$
\frac{\partial x}{\partial \phi}=\rho\cos\phi\cos\theta
$$

对 $\theta$ 求偏导时，把 $\rho,\phi$ 当常数：

$$
\frac{\partial x}{\partial \theta}=-\rho\sin\phi\sin\theta
$$

第二行来自 $y=\rho\sin\phi\sin\theta$：

$$
\frac{\partial y}{\partial \rho}=\sin\phi\sin\theta
$$

$$
\frac{\partial y}{\partial \phi}=\rho\cos\phi\sin\theta
$$

$$
\frac{\partial y}{\partial \theta}=\rho\sin\phi\cos\theta
$$

第三行来自 $z=\rho\cos\phi$。注意 $z$ 和 $\theta$ 无关，所以对 $\theta$ 的偏导是 $0$：

$$
\frac{\partial z}{\partial \rho}=\cos\phi
$$

$$
\frac{\partial z}{\partial \phi}=-\rho\sin\phi
$$

$$
\frac{\partial z}{\partial \theta}=0
$$

因此 Jacobian 矩阵是

$$
\begin{bmatrix}
\sin\phi\cos\theta & \rho\cos\phi\cos\theta & -\rho\sin\phi\sin\theta\\
\sin\phi\sin\theta & \rho\cos\phi\sin\theta & \rho\sin\phi\cos\theta\\
\cos\phi & -\rho\sin\phi & 0
\end{bmatrix}
$$

接下来算这个行列式。为了看得清楚，令

$$
s=\sin\phi,\quad c=\cos\phi,\quad C=\cos\theta,\quad S=\sin\theta
$$

矩阵变成

$$
\begin{bmatrix}
sC & \rho cC & -\rho sS\\
sS & \rho cS & \rho sC\\
c & -\rho s & 0
\end{bmatrix}
$$

按第一行展开：

$$
J
=
sC
\begin{vmatrix}
\rho cS & \rho sC\\
-\rho s & 0
\end{vmatrix}
-
\rho cC
\begin{vmatrix}
sS & \rho sC\\
c & 0
\end{vmatrix}
+
(-\rho sS)
\begin{vmatrix}
sS & \rho cS\\
c & -\rho s
\end{vmatrix}
$$

先算第一个 $2\times 2$ 行列式：

$$
\begin{vmatrix}
\rho cS & \rho sC\\
-\rho s & 0
\end{vmatrix}
=
(\rho cS)(0)-(\rho sC)(-\rho s)
=\rho^2s^2C
$$

所以第一项是

$$
sC\cdot \rho^2s^2C=\rho^2s^3C^2
$$

第二个 $2\times 2$ 行列式：

$$
\begin{vmatrix}
sS & \rho sC\\
c & 0
\end{vmatrix}
=
(sS)(0)-(\rho sC)c
=-\rho scC
$$

所以第二项是

$$
-\rho cC(-\rho scC)=\rho^2sc^2C^2
$$

第三个 $2\times 2$ 行列式：

$$
\begin{vmatrix}
sS & \rho cS\\
c & -\rho s
\end{vmatrix}
=
(sS)(-\rho s)-(\rho cS)c
=-\rho s^2S-\rho c^2S
$$

提取公因式：

$$
-\rho S(s^2+c^2)
$$

因为

$$
s^2+c^2=1
$$

所以第三个 $2\times 2$ 行列式等于

$$
-\rho S
$$

第三项就是

$$
(-\rho sS)(-\rho S)=\rho^2sS^2
$$

把三项加起来：

$$
J=\rho^2s^3C^2+\rho^2sc^2C^2+\rho^2sS^2
$$

前两项提取 $\rho^2sC^2$：

$$
J=\rho^2sC^2(s^2+c^2)+\rho^2sS^2
$$

因为 $s^2+c^2=1$：

$$
J=\rho^2sC^2+\rho^2sS^2
$$

继续提取 $\rho^2s$：

$$
J=\rho^2s(C^2+S^2)
$$

又因为

$$
C^2+S^2=1
$$

所以

$$
J=\rho^2s
$$

代回 $s=\sin\phi$：

$$
J=\rho^2\sin\phi
$$

因此体积微元为

$$
dV=|J|\,d\rho\,d\phi\,d\theta
$$

在通常球坐标范围 $0\le \phi\le \pi$ 中，$\sin\phi\ge 0$，所以

$$
dV=\rho^2\sin\phi\,d\rho\,d\phi\,d\theta
$$

### 考点

多变量换元时，面积或体积微元要乘 Jacobian 的绝对值。球坐标中三个方向的尺度因子可以理解为 $\rho$ 方向长度是 $d\rho$，$\phi$ 方向弧长是 $\rho\,d\phi$，$\theta$ 方向弧长是 $\rho\sin\phi\,d\theta$，所以体积微元是

$$
dV=d\rho\cdot \rho\,d\phi\cdot \rho\sin\phi\,d\theta
=\rho^2\sin\phi\,d\rho\,d\phi\,d\theta
$$

### 易错点

- 把 $\phi$ 和 $\theta$ 弄反。这里 $\phi$ 是从 $z$ 轴量下来的角，$\theta$ 是 $xy$ 平面里的角。
- 忘记 $z=\rho\cos\phi$ 不含 $\theta$，所以 $\frac{\partial z}{\partial \theta}=0$。
- 忘记最终体积微元要乘 Jacobian 的绝对值。
- 行列式展开时第二项前面有负号，很容易漏掉。
