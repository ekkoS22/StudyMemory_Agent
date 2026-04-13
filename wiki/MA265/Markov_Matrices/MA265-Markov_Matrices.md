# MA265 - Markov Matrices

## Section 2.1 Problem 29

### 题目

从向量 $u_0=(1,0)$ 开始，反复乘同一个 Markov matrix：

$$
A=
\begin{bmatrix}
.8 & .3\\
.2 & .7
\end{bmatrix}
$$

已知：

$$
u_1=Au_0=
\begin{bmatrix}
.8\\
.2
\end{bmatrix}
$$

求接下来的三个向量 $u_1,u_2,u_3$。

### 解答

已经给出：

$$
u_1=
\begin{bmatrix}
.8\\
.2
\end{bmatrix}
$$

继续计算：

$$
u_2=Au_1=
\begin{bmatrix}
.8 & .3\\
.2 & .7
\end{bmatrix}
\begin{bmatrix}
.8\\
.2
\end{bmatrix}
$$

第一项：

$$
.8(.8)+.3(.2)=.64+.06=.70
$$

第二项：

$$
.2(.8)+.7(.2)=.16+.14=.30
$$

所以：

$$
u_2=
\begin{bmatrix}
.70\\
.30
\end{bmatrix}
$$

再算：

$$
u_3=Au_2=
\begin{bmatrix}
.8 & .3\\
.2 & .7
\end{bmatrix}
\begin{bmatrix}
.70\\
.30
\end{bmatrix}
$$

第一项：

$$
.8(.70)+.3(.30)=.56+.09=.65
$$

第二项：

$$
.2(.70)+.7(.30)=.14+.21=.35
$$

所以：

$$
u_3=
\begin{bmatrix}
.65\\
.35
\end{bmatrix}
$$

最终答案：

$$
u_1=
\begin{bmatrix}
.8\\
.2
\end{bmatrix},
\quad
u_2=
\begin{bmatrix}
.70\\
.30
\end{bmatrix},
\quad
u_3=
\begin{bmatrix}
.65\\
.35
\end{bmatrix}
$$

### 考点

Markov matrix 的每一列加起来等于 $1$，所以如果初始向量的分量和为 $1$，后续向量的分量和也会保持为 $1$。

### 易错点

- 把 $u_2$ 写成 $u_1A$，但这里应该是 $u_2=Au_1$。
- 矩阵乘法时第一行乘列向量得到第一项，第二行乘列向量得到第二项。
- 忘记检查每个向量的分量和仍然是 $1$。
