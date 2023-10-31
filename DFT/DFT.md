# 书籍
"Mathematics of the Discrete Fourier Transform", 离散傅里叶变换的数学,斯坦福大学,

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

$T \triangleq$ sampling period (sec), 采样的时间长度,

$X(w_k) \triangleq$ Spectrum of $x$, at radian frequency $w_k$

$w_k \triangleq k\Omega$, $kth$ frequency sample (rad/sec)

$\Omega \triangleq \frac{2\pi}{NT}$, radian-frequency sampling interval

$fs \triangleq \frac{1}{T}$, sampling rate,  采样频率

$N$, number of samples in both time and frequency, integer, 整数

## 1.2 Mathematics of the DFT
dft的数学原理，

There are two remaining symbols in the DFT,
$$
j \triangleq \sqrt{-1}\\
e \triangleq \lim\limits_{n \to \infin}(1+ \frac{1}{n})^n = 2.71828\\
$$
一个序列 $s_k(n)\triangleq e^{j2\pi n k/N}$
Euler's Identity, 欧拉恒等式,$e^{j\theta}=\cos{(\theta)} + j\sin{(\theta)}$
欧拉恒等式是理解下述等式的关键:
$$
s_k(t_n)\triangleq  e^{jw_kt_n} = \cos{(w_kt_n)} + j\sin{(w_kt_n)}
$$
这个表达式定义了一个抽样复正弦函数，
内积, inner product of the signals $x$ and $s_k$, 我们将DFT重新用内积的方式表示出来:
$X(k) \triangleq \langle x,s_k \rangle$ where $s_k(n)\triangleq e^{j2\pi n k/N}$ is the sampled complex sinusoid at (normalized) radian frequency $w_k = 2\pi k/N$, and the inner product operation is defined by
$$
\langle x,y \rangle \triangleq  \sum_{n=0}^{N-1}x(n)\overline{y(n)}
$$
We will show that the inner product of $x$ with the $kth$ basis sinusoid $s_k$ is a measure of how much of $s_k$ is present in $x$ and at what phase, since it is a complex number. 物理意义就是$x$ 在 $s_k$ 上的投影是多少，并且相位是多少?

反相傅里叶变换, IDFT, weighted sum of projections of $x$ onto $\{ s_k \}_{k=0}^{N-1}$, i.e.,
$$
x(n) \triangleq \sum_{k=0}^{N-1}\tilde{X_k}s_k(n)
$$
where 
$$
\tilde{X_k} \triangleq \frac{X(k)}{N}
$$
is the actual coefficient of projection of $x$ onto $s_k$. Referring to the whole signal as $x\triangleq x(\cdot)$, the IDFT can be written as
$$
x \triangleq \sum_{k=0}^{N-1}\tilde{X_k}s_k
$$
Projecting signals onto signals via the inner product
The DFT as the coefficient of projection of a signal $x$ onto a sinusoid
The IDFT as a weighted sum of sinusoidal projections

# chap 2 Complex Numbers
## 2.1 多项式的分解
monic, the leading coefficient is $1$,
$$
p(x)=(x-x_1)(x-x_2)
$$
This is the factored form of the monic polynomial $p(x)$




