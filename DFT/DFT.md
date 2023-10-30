# 书籍
<Mathematics of the Discrete Fourier Transform>, 离散傅里叶变换的数学,斯坦福大学,

参考书籍:
1. Complex Variables and Applications, R. V. Churchill, 1960
2. Complex Variables and the Laplace Transform for Engineers, Dover, 1961
3. Mathematics From the Birth of Numbers, J. Gullberg
4. Introduction to digital filter theory, J. O. Smith
5. Theory and Application of Digital Signal Processing, L. R. Rabiner
6. Digital Signal Processing, A. V. Oppenheim

### Complex Variables and Applications
复变量和应用, 这方面的书看了2本。

# 前言
课程, Introduction to Digital Signal Processing and Discrete Fourier Transform (DFT). For entering Music Ph.D students.

需要 a good high-school math background. Calculus exposure is desirable, but not required.

# chap 1 Introduction to the DFT
DFT, Discrete Fourier Transform,

## 1.1 定义
信号 $x$ 的离散傅里叶变化为
$$
X(w_k) \triangleq \sum_{n=0}^{N-1}x(t_n)e^{-jw_kt_n}, k=0,1,2,...,N-1
$$
and its inverse (IDFT) is given by
$$
x(t_n)=\frac{1}{N}\sum_{k=0}^{N-1}X(w_k)e^{jw_ktn}, n=0,1,2,...,N-1
$$

where:
$x(t_n)\triangleq$ input signal amplitude at time $t_n$ (sec)
$t_n \triangleq nT$ nth sampling instant (sec)
$n \triangleq $ sample number (integer), 采样点数量
$T \triangleq$ sampling period (sec), 采样的时间间隔


   







