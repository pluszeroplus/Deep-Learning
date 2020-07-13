# Eigenvalues and Eigenvectors 特征值和特征向量是什么？

在建立数学模型时，我们想要找到输入值$x$ 和目标输出值$y$ 之间的联系。但是有的时候我们的$x$非常复杂，例如有100+个属性作为输入，那么这个时候无论建立什么模型，计算量都会非常的大。

而特征向量的目的，就是用更少的维度来代表这些数据。特征向量和特征值的定义为：
$$
Av = \lambda v
$$
$A$是一个$n\times n$ 的矩阵，$v$是一个$n \times 1$ 的向量，$\lambda$ 是一个常数。低纬度的$v$可以代表高维度的$A$，因此使用特征向量就可以减少了计算同时保留了原数据的特征。

一些应用：

* PCA (Principal component analysis)重要过程就是计算协方差矩阵的特征向量
* 在一些人脸识别技术例如EigenFaces里面也会用到

## 如何计算

对于任意一个方阵 $A$, 存在一个特征值$\lambda$和特征向量$v$，使得下列等式成立：
$$
Av = \lambda v
$$
接下来我们加入一个单位矩阵$I$
$$
Av = \lambda I v
$$
稍微换一下位置
$$
Av - \lambda Iv = 0
$$
如果$v$不等于$0$ 的话，我们可以用下面的式子求出$\lambda$
$$
|A - \lambda I| = 0
$$
我们用个例子来说明如何计算，比如下面这个矩阵
$$
\left [
\begin{matrix}
-6 & 3 \\
4 & 5
\end{matrix}
\right]
$$
的$|A-\lambda I| = 0$
$$
\left|
\left[
\begin{matrix}
-6 & 3\\
4 & 5
\end{matrix}
\right]
- \lambda
\left[
\begin{matrix}
1 & 0 \\
0 & 1
\end{matrix}
\right]
\right|=0
$$

$$
\left| \left[
\begin{matrix}
-6-\lambda& 3\\
4 & 5-\lambda
\end{matrix}
\right] \right |=0
$$

然后计算行列式：
$$
(-6-\lambda)(5-\lambda) - 3 \times 4 = 0
$$

$$
\lambda = -7 \space or \space 6
$$

从这里可以知道，特征值有的时候不止一个

接下来我们来计算特征向量

首先
$$
\left[
\begin{matrix}
-6 & 3\\
4 & 5
\end{matrix}
\right]
\left[
\begin{matrix}
x\\
y
\end{matrix}
\right]
= 6
\left[
\begin{matrix}
x\\
y
\end{matrix}
\right]
$$
相乘之后我们得到两个方程式：
$$
-6x+3y = 6x\\
4+5y = 6y
$$
化简一下：
$$
-12x + 6 y = 0\\
4x - y = 0
$$
两个式子其实都是$y = 4x$ 因此特征向量是
$$
\left[
\begin{matrix}
1\\
4
\end{matrix}
\right]
$$


#### reference 

**What are Eigenvalues and Eigenvectors?**

https://medium.com/fintechexplained/what-are-eigenvalues-and-eigenvectors-a-must-know-concept-for-machine-learning-80d0fd330e47

**Math is fun**

https://www.mathsisfun.com/algebra/eigenvalue.html

