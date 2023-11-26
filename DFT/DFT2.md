# chap 7 Derivation of the Discrete Fourier Transform (DFT)
数字傅里叶变换的推导

### 7.1 几何级数
对于任意一个复数$z_1\in C$, 信号$x(n)\triangleq z_1^n, n=0,1,2,...$定义了一个几何级数，每一项都是前一项乘以一个复数常量。
一个几何级数定义为几何序列的和
$$
S_N(z_1)\triangleq \sum_{n=0}^{N-1}z_1^n=1+z_1+z_1^2+\dotsi+z_1^{N-1}
$$
如果$z_1 \not = 1$, 那么和可以表示为闭形式,closed form
$$
S_N(z_1) = \frac{1-z_1^N}{1-z_1}
$$
### 7.1.2 正弦信号的正交性
不同频率的正弦信号是正交的, 前提是正弦信号的持续时间是无穷的。
对于一个长度为N的采样正弦信号段, DFT使用的，只有采样速率的谐波才能保持正交性。在这些频率点上$f_k = kf_s/N, k=0,1,2,...,N-1$. 
与这些频率点对应的复正弦函数为
$$
s_k(n)\triangleq = e^{jw_knT}, w_k=k\frac{2\pi}{N}f_s, k=0,1,2,3,\dotsi,N-1
$$
复平面上单位值的1/N的根
$$
W_N^{k}\triangleq e^{jw_kT}=e^{jk2\pi(f_s/N)T}=e^{jk2\pi/N}
$$
那么,显然$[W_N^k]^N = e^{jk2\pi}=1$

### 7.1.3 正弦信号的正交性

### 7.1.4 Norm of the DFT正弦信号
$$
\langle s_k,s_k \rangle = \sum_{n=0}^{N-1}e^{j2\pi(k-k)n/N}=N \\
||s_k|| = \sqrt{N}
$$

### 7.1.15 一个正交正弦信号集
Orthonormal sinusoidal set, 
标准正交化,
$$
\tilde{s_k}(n)\triangleq = \frac{s_k(n)}{\sqrt{N}}=\frac{e^{j2\pi kn/N}}{\sqrt{N}}
$$
正规化的DFT sinusoids
### 7.1.16 DFT,离散傅里叶变换
给定一个信号$x(\cdot) \in C^N$,频谱定义为
$$
X(w_k)\triangleq \langle x,s_k \rangle = \sum_{n=0}^{N-1}x(n)\overline{s_k(n)},k=0,1,\dotsi
$$
或者写成
$$
X(w_k)\triangleq \sum_{n=0}^{N-1}x(n)e^{-j\frac{2\pi kn}{N}}
$$
第kth个频谱的值等于信号与第kth个DFT正弦信号$s_k$的内积。这个定义是x在$s_k$上投影的系数的N倍
$$
\frac{\langle x,s_k \rangle}{||s_k||^2}= \frac{X(w_k)}{N}
$$
projection投影本身为:
$$
P_{s_k} = \frac{X(w_k)}{N}s_k
$$
反向离散傅里叶变换，可以写作投影之和
$$
x=\sum_{n=0}^{N-1}P_{s_k}=\sum_{n=0}^{N-1}\frac{X(w_k)}{N}s_k
$$
通常写为:
$$
x(n)=\frac{1}{N}\sum_{n=0}^{N-1}X(w_k)e^{j\frac{2\pi kn}{N}}
$$
### 7.1.7 Frequencis in the Cracks
DFT的点只在这些频点上$w_k=2\pi kf_s/N$,如果我们需要研究的x的频点并不在DFT-sinusoid频率上呢? 
下面我们将一个长度为N的频率为任意$w$的正弦信号投影到第$nth$ DFT 正弦信号上。
$$
x(n) \triangleq e^{jwnT}\\
s_k(n) \triangleq e^{jw_knT}\\
P_{s_k}(x)= \frac{\langle x,s_k \rangle}{\langle s_k,s_k \rangle}s_k \triangleq \frac{X(w_k)}{N}s_k \\
$$
投影系数与成正比
$$
\begin{aligned}
X(w_k)\triangleq& \langle x,s_k \rangle \triangleq \sum_{n=0}^{N-1}x(n)\overline{s_k(n)}\\
=&\sum_{n=0}^{N-1}e^{jwnT}e^{-jw_knT}=\sum_{n=0}^{N-1}e^{j(w-w_k)nT}=\frac{1-e^{j(w-w_k)NT}}{1-e^{j(w-w_k)T}}\\
=&  e^{j(w-w_k)(N-1)T/2}\frac{\sin[(w-w_k)NT/2]}{\sin[(w-w_k)T/2]} 
\end{aligned}
$$
其中用到了一个简单推导
$$
\begin{aligned}
1-e^{j\theta} &= 1-\cos(\theta)-j\sin(\theta)\\
&= 2\sin^2(\frac{\theta}{2})-j2\sin(\frac{\theta}{2})\cos(\frac{\theta}{2})\\
&= 2\sin(\frac{\theta}{2})[\sin(\frac{\theta}{2})-j\cos(\frac{\theta}{2})] \\ 
&= 2\sin(\frac{\theta}{2})(-j)[\cos(\frac{\theta}{2})-j\sin(\frac{\theta}{2})]\\
&=2\sin(\frac{\theta}{2})(-j)e^{-j\frac{\theta}{2}}\\
\end{aligned}
$$
当$w=w_k$时, the sum is N, 当$w=w_l$时，为零。在其他频率点上，sum不等于零。
DFT sinusoids构成了$C^N$上的一个基， basis. 任何长度为N的信号都可以表达为这个基的线性组合。因此，在分析记录的信号的段时，我们必须进行翻译。

我们可以将DFT操作视为一种digital filter, 数字滤波器。频率响应，为刚才计算的值。它的幅值为:
$$
|X(w_k)| = \Bigl| \frac{\sin[(w-w_k)NT/2]}{\sin[(w-w_k)T/2]}  \Big|
$$
The peak is centered on $w_k$. The secondary peaks away from $w_k$ are called sidelobes of the DFT response. 主峰值被称为响应的主瓣, main lobe. 
我们看到$X(w_k)$对dc和采样速率之间的所有频率都很敏感，除了那些DFT-正弦信号频率$w_l$, $l\not =k$. 这被称为spectral leakage, cross talk 在频谱分析里面。频谱泄漏，串话。对于周期性信号，我们可以选择N为一个周期或周期的整数倍。通常，不能满足要求，频谱泄漏会成为一个难以避免的问题。

频谱泄漏可以通过增加N来减小. 在窗口的边界，只有DFT正弦信号没有被截断, 其它的频率都会suffer some truncation distortion, 极速地截断、打开transient会在频谱上作为旁瓣的源头。就DFT而言, 输入信号$x(t)$

frequency bin, or storage bin for energy spectral. $k-1/2$to $k+1/2$, k 被称为bin number, $|X(w_k)|^2$称为total energy in $kth$ bin. 任何连续的带限信号的采样。

### 7.1.8 Normalized DFT
归一化的DFT, 归一化的DFT正弦信号
$$
\tilde{s_k}(n) \triangleq \frac{e^{j2\pi kn/N}}{\sqrt{N}}
$$
In this case, the normalized DFT of $x$ is
$$
\tilde{X}(w_k)\triangleq \langle x,\tilde{s}_k \rangle = \frac{1}{\sqrt{N}}\sum_{n=0}^{N-1}x(n)e^{-j2\pi kn/N}
$$
inverse normalized DFT,
$$
x(n)=\sum_{k=0}^{N-1}X(w_k)\tilde{s}_k(n)=\frac{1}{\sqrt{N}}\sum_{k=0}^{N-1}X(w_k)e^{j2\pi kn/N}
$$
这里DFT, IDFT的唯一区别是指数项的符号,

## 7.2 长度为2的DFT
time domain basis vector
frequency domain basis vector, 只是对时域的basis,旋转了45 degree而已。这个物理解释真的是绝了！

## 7.3 Matrix Formulation of the DFT
DFT的矩阵公式
$$
X(w_k)\triangleq = \langle x,s_k \rangle = \sum_{n=0}^{N-1}x(n)e^{-j2\pi nk/N}
$$
用矩阵形式来表示的话, $X=S_N*x$
$$
\begin{bmatrix}
    X(w_0)\\
    X(w_1)\\
    X(w_2)\\
    \vdots \\
    X(w_{N-1})
\end{bmatrix}=
\begin{bmatrix}
    s_0(0) & s_0(1) & \dotsi & s_0(N-1) \\
    s_1(0) & s_1(1) & \dotsi & s_1(N-1) \\
    s_2(0) & s_2(1) & \dotsi & s_2(N-1) \\
    \vdots &  \vdots & \vdots & \vdots  \\
    s_{N-1}(0)& s_{N-1}(1) & \dotsi & s_{N-1}(N-1) \\
\end{bmatrix}
\begin{bmatrix}
    x(0)\\
    x(1) \\
    x(2) \\
    \vdots \\
    x(N-1) \\
\end{bmatrix}
$$
$S_N$表示为DFT矩阵, $S_N[k,n]\triangleq W_{N}^{-kn}\triangleq e^{-j2\pi kn/N}$
$$
S_N\triangleq
\begin{bmatrix}
    1 & 1 & 1 & \dotsi & 1 \\
    1 & e^{-j2\pi/N} & e^{-j4\pi/N} & \dotsi & e^{-j2\pi(N-1)/N}\\
    1 & e^{-j4\pi/N} & e^{-j8\pi/N} & \dotsi & e^{-j2\pi 2(N-1)/N}\\
    \vdots & \vdots & \vdots & \vdots & \vdots \\
    1 & e^{-j2\pi(N-1)/N} & e^{-j2\pi2(N-1)/N} & \dotsi & e^{-j2\pi(N-1)(N-1)N}
\end{bmatrix}
$$
$kth$ row of the DFT matrix is the $k$ DFT sinusoids
因为这个矩阵是对称的, ${S_N}^T=S_N$, 转置并不包含共轭,第$k$列也就是第$k$行。

The inverse DFT matrix就是$\overline{S_N}/N$, 我们可以将反DFT变换写为
$$
\underline{x}=\frac{1}{N}{S_N}^* X
$$
Since $X=S_Nx$,则${S_N}^*\cdot S_N=N\cdot I$

The normalized DFT matrix is:
$$
\tilde{S}_N \triangleq \frac{1}{\sqrt{N}}S_N
$$
对归一化后的$S_N$, $\tilde{S}_N^*\cdot \tilde{S}_N = I$
$S_N$的列是orthonormal的,规范正交，标准正交的， 这样的矩阵称为, unitray, 单一的,
当一个实矩阵满足$A^TA=I$, $A$称为orthogonal, 是正交矩阵的。Unitary是正交的一般化到复数矩阵。

使用scilab可以很方便地计算FFT,

# chap 8 Fourier Theorems for the DFT
DFT的傅里叶变换原理

## 8.1 The DFT and its Inverse
let $x(n), n=0,1,2,...,N-1$ 表示了一个n个采样的复序列，$x\in C^N$. $x$的频谱是由离散傅里叶变换定义的:
$$
X(k)\triangleq \sum_{n=0}^{N-1}x(n)e^{-j2\pi nk/N}, k=0,1,2,...,N-1
$$
IDFT定义为
$$
x(n)=\frac{1}{N}\sum_{k=0}^{N-1}X(k)e^{j2\pi nk/N},n=0,1,2,...,N-1
$$
一般来说，我们假定采样频率$f_s=1$, 也可以将频率设置为任意值
$$
e^{j2\pi nk/N}=e^{j2\pi k(f_s/N)nT}=e^{jw_kt_n}
$$
这样，我们在这一章使用$f_s=1$的定义，则$w_k\triangleq 2\pi k/N$
a radian 频率$w_k$定义为radians per sample, 每样本弧度. 或者每秒钟弧度，角速度。当采样率为每秒1次的话，这两者是相同的。
normalized frequency, 正规化的频率，归一化的频率。所有的归一化频率的范围在$[-0.5,0.5)$之间。

### 8.1.1 概念和术语, notation and terminology
$X$是$x$的离散傅里叶变换, DFT, 它们形成一组变换对，transform pair, $x \leftrightarrow X$
另一种表示方法为
$$
DFT(x) \triangleq X \\
DFT_k(x) \triangleq X(k) \\
$$
时域信号用小写符号$x$来表示, 频率域信号用大写符号$X$来表示。

### 8.1.2 Modulo Indexing, Periodic Extension
DFT正弦波$s_k(n) \triangleq e^{jw_kn}$是所有的周期性信号能被N整除的。这就是说 $s_k(n+mN) = s_k(n)$, 以N为周期重复的信号。
一个长度为N的信号可以表示为时域的一组DFT正弦信号的线性组合。
$$
x(n) = \frac{1}{N}\sum_{k}X(k)s_k(n)
$$
$s_k(n)$是一组正交的正弦信号。
$x(n)$是周期性重复信号，范围为$[0,N-1)$, $x(n+mN)\triangleq x(n)$
Definition:
对于任意信号$x\in C^N$, 我们定义
$$
x(n+mN) \triangleq x(n)
$$
所有信号和频谱的索引可以被解释为以N为模的重复模式, modulo N, x(n mod N) 来强调这一点。
对周期性信号的采样，按照$NT$秒周期，也就是N个采样的周期。频域上，频谱的范围是$0$ ~ 采样频率$w_k$

另一方面时域上, 信号$x(n)$包含了N个采样信号，后面跟着零。频谱是nonzero 非零的。采样间的频谱可以通过带限插值的方式重构, bandlimited interpolation. 时域上的DFT输入信号的时间有限的表示，

## 8.2 Signal Operators
信号操作符, 

### 8.2.1 Flip operator
翻转运算
$$
FLIP_n(x) \triangleq x(-n)
$$

### 8.2.2 Shift Operator
移位操作, $SHIFT_{\Delta,n}(x)\triangleq x(n-\Delta)$
移位是circular的，
我们用来表示time delay了$\Delta$个采样。我们经常使用移位加填0来避免循环移位带来的问题。

### 8.2.3 Convolution
卷积,$x*y$定义为
$$
(x*y)_n \triangleq \sum_{m=0}^{N-1}x(m)y(n-m)
$$
这是cyclic, circuilar convolution. 
commutative, $x*y=y*x$

Graphical Convolution
$$
y(n)=(x*h)_n=\sum_{m=0}^{N-1}x(m)h(n-m)\\
=\langle x,SHIFT_n(FLIP(h)) \rangle, (h \space real)
$$
where $x,y\in C^N, h\in R^N$,可以在图形上来进行解释。

**Polynomial Multiplication**
多项式乘法, 
let $p(x)$ denote the mth-order polynomial
$$
p(x)=p_0 + p_1x+p_2x^2+p_3x^3 + \dotsi + p_mx^m
$$
let $q(x)$ denote the nth-order polynomial
$$
q(x)=q_0+q_1x+q_2x+\dotsi + q_nx^n
$$
相乘后，查看系数
$$
\begin{aligned}
    p(x)q(y) &= p_0q_0\\
    &= (p_0q_1 +p_1q_0)x \\
    &= (p_1q_2 + p_1q_1 + p_2q_0)x^2 \\
    &= (p_0q_3 + p_1q_2+p_2q_2 +p_3q_0)x^3 + \dotsi \\
    &= (p_0q_{n+m} +p_1q_{n+m-1}+\dotsi + p_{n+m}q_0)x^{n+m}
\end{aligned}
$$
表示为
$$
r(x)\triangleq p(x)q(x)=r_0+r_1x+r_2x^2 + \dotsi + r_{m+n}x^{m+n}
$$
The $ith$ coefficient can be expressed as
$$
r_i = \sum_{j=0}^{i}p_jq_{i-j}=\sum_{j=-\infin}^{\infin}p_jq_{i-j}=(p*q)(i)
$$
**Multiplication of Decimal Numbers**
十进制数的乘法,
十进制数表示为
$$
3819=3\cdot 10^3 + 8\cdot 10^2 + 1\cdot 10^1 + 9\cdot 10^0
$$
将两个十进制数相乘的话，也就是对系数做卷积。只不过这里有carries,进位。

### 8.2.4 Correlation
相关度,
两个信号$x,y \in C^N$的相关性的操作定义为:
$$
(x\circledast y)_n \triangleq \sum_{m=0}^{N-1}\overline{x(m)}y(m+n)
$$
相关性也可以写成$(x\circledast y)_n = \langle SHIFT_{-n}(y),x \rangle$
物理意义的解释, $y$左移$n$个采样值后在$x$上的投影的系数。
$n$是correlation lag, 相关延迟
$\overline{x(m)}y(m+n)$称为lagged product, 延迟积,

### 8.2.5 Stretch Operator
延伸运算符,对一个长度为$N$的信号，扩展为$M\triangleq LN$长度的信号,
stretch by factor $L$
$$
STRETCH_{L,m}(x)\triangleq \begin{cases}
    x(m/L), m/L=integer \\
    0, m/L\not = integer \\
\end{cases}
$$
在each pair of samples中间，插入$L-1$个零。
如$STRETCH_3([4,1,2])=[4,0,0,1,0,0,2,0,0]$
延伸操作用来描述和分析upsampling,增加采样速率, 过采样

### 8.2.6 Zero Padding
填零, 将长度为$N$的信号映射到长度为$M>N$的信号, $M$不要是$N$的整数倍。
$$
ZEROPAD_{M,m}(x)\triangleq \begin{cases}
    x(m), 0\leqslant m \leqslant N-1 \\
    0, N\leqslant m \leqslant M-1 \\
\end{cases}
$$
For spectra, zero padding 的插入,
zero-phase FFT windows,
使用Fourier theorems, 傅里叶原理, 时域上填零会带来频域上的带限插值。同样，在频域上填零会带来时域上的带限插值。实现理想的采样速率转换。
带限插值在数字信号处理上是理想的插值。

### 8.2.7 Repeat Operator
重复操作符, 将长度为$N$的信号映射为长度$M\triangleq LN$的信号
$$
REPEAT_{L,m}(x) \triangleq x(m), m=0,1,2,\dotsi , M-1
$$
重复信号$L$次,

### 8.2.8 Downsampling Operator
欠采样操作,
Downsampling by $L$ 定义为taking every $Lth$ sample, starting with sample 0:
$$
SELECT_{L,m}(x)\triangleq , m=0,1,2,\dotsi,M-1, (N=LM,x\in C^N)
$$
是Stretch的反向操作, 

### 8.2.9 Alias Operator
Aliasing occurs when a signal is undersampled. 
混叠现象,
$$
ALIAS_{L,m}(x)\triangleq \sum_{l=0}^{N-1}x(m+l\frac{N}{L}), \\
m=0,1,2,...,M-1, (N=LM, x\in C^N)
$$
ALIAS操作将一个长度为$N=LM$的信号映射为一个长度为$M$的信号。
time-domain aliasing
frequency-domain aliasing
Aliasing is not invertible, 无法恢复的。无法恢复原来的信号。
与stretch相反,

## 8.3 Even and Odd functions, 偶/奇函数
even, $f(-n)=f(n)$
odd, $f(-n)=-f(n), f(0)=0$
定理:
任何函数$f(n)$都可以被分解为一个偶分量和一个奇分量
$$
f_e(n)\triangleq \frac{f(n)+f(-n)}{2} \\
f_o(n)\triangleq \frac{f(n) -f(-n)}{2} \\
$$
定理:
奇函数$x_o$的所有采样的和为0。这个看起来也是显然的。

对于所有的DFT 正弦信号频率$w_k=2\pi k/N$,
$$
\sum_{n=0}^{N-1}sin(w_kn)cos(w_kn)=0, k=0,1,2,\dotsi,N-1
$$

## 8.4 傅里叶定理, Fourier Theorems
* DFT case,
* DTFT
* Fourier transform
* Fourier series, 

当设计无穷项相加或积分时，傅里叶变换存在的验证条件，可以是非常难以用数学来证明的。数学家们对这些问题颇花了些功夫。

### 8.4.1 Linearity
线性
对于任意的$x,y \in C^N$, 和$\alpha,\beta \in C$, DFT满足
$$
\alpha x + \beta y \leftrightarrow \alpha X + \beta Y
$$

### 8.4.2 Conjugation and Reversal
结合律和翻转率
对于任意的$x\in C^N$
$$
\overline{x} \leftrightarrow FLIP(\overline{X})\\
FLIP(\overline{x}) \leftrightarrow \overline{X}\\
FLIP(x)\leftrightarrow FLIP(X)\\
FLIP(x) \leftrightarrow \overline{X}, \space (x \space real)\\
$$

频域的共轭等于时域上的翻转。频域上相位的求反等于时间上信号的翻转。
当$x\in R^N$时，属于实数信号时, $FLIP(X) = \overline{X}, \space (x \space real)$

### 8.4.3 Symmetry，对称性
任何实信号的频谱是Hermitian的,额米共轭的。
因为这种对称性，我们可以丢弃所有负频率的部分，然后通过正频率的样本恢复原来的$x$信号。采样信号的频谱可以绘制的范围在$0\~ f_s/2$Hz。
意思是负频率=正频率

定理:
如果$x\in R^N$,$re{(X)}$是偶函数, $im{(X)}$是奇函数。

定理:
如果$x\in R^N$, $|X|$是偶函数，$\angle X$是奇函数。

定理:
一个偶信号的傅里叶变换也是偶的。$x\space even \leftrightarrow X\space even$

定理:
一个实偶信号的变换也是实偶信号,$x\space real\space even \leftrightarrow X\space real \space even$

定义:
一个拥有实频谱的信号(例如一个实、偶信号),通常称为一个零相位信号。zero phase signal. 然而，如果频谱变成负值的话，相位通常是$\pi$而不是0. 即使相位在频谱的zero-crossing变换时，相位的变换是0-$\pi$。
在实际中，zero-crossing,过零通常发生在低幅度的时刻，比如FFT windows的DTFT的旁瓣上。

### 8.4.4 Shift Theorem, 移位定理
对于任意的$x \in C^N$, 任意的整数$\Delta$
$$
DFT_k[SHIFT_{\Delta}(x)] = e^{-jw_k\Delta}X(k)
$$
时域上的延迟delay,带来频域上的线性相位部分, linear phase term, 频谱的幅度不发生任何变化。

**Linear Phase Terms**
线性相位项, $e^{-jw_k\Delta}$, $\angle{e^{-jw_k\Delta}}=-\Delta \cdot w_k$
这样，phase vs radian frequency的变化的斜率为$-\Delta$
如果我们表达原来的频谱，用极坐标方式
$$
X(k) = G(k)e^{j\Theta(k)}
$$
$G(k)$是幅度
$\Theta(x)$是相位项
线性相位项，只会改变频谱的$\Theta(x)$,
$$
e^{-jw_k\Delta}X(k)=G(k)e^{j[\Theta(k) - w_k\Delta]}
$$
Where $w_k\triangleq 2\pi k/N$

定义:
一个信号被视为一个linear phase signal,如果它的相位是如下形式
$$
\Theta(w_k) = \plusmn \Delta \cdot w_k \plusmn \pi I(w_k)
$$
$I(w_k)$是一个indicator function, 取值为0或1

**FFT窗口的移位定理的应用**
在实际的频谱分析里, 我们会使用快速傅里叶变换和窗口函数, window function $w(n), n=0,1,2,\dotsi,N-1$,窗口函数是取正值的。关于中点对称，看起来似一个钟函数, bell curve. 
使用窗口函数与$x$信号相乘，形成了一个windowed signal,加窗信号
$$
x_w(n) = w(n)x(n)\\
x_w = w\cdot x \\
$$
加窗信号再用FFT来分析。窗口的作用是将信号慢慢地，优雅地降为0.消除时域信号的突然变化，cutting off , 带来的频谱产物，frequency distortion, 加窗常用于一个较长的信号中取样一部分，形成$x(t)$的场合。

原理:
实对称FFT窗口是线性相位的, linear phase,
A spectrum whose phase is a linear function of frequency, 相位随频率成正比, is a linear phase.

### 8.4.5 Convolution 原理
卷积原理
$$
x*y \leftrightarrow X\cdot Y
$$
由于FFT提供了快速傅里叶变换, 提供了高速卷积, fast convolution.
对FFT实行卷积在长序列时比较高效，比如N>100时。因为直接卷积需要order of $N^2$操作, FFT based 卷积只需要$Nlog(N)$个操作。

使用Matlab来进行快速卷积，使用FFT

### 8.4.6 Dual of the Convolution Theorem
时间上的乘积等于频域上的卷积,
$$
x\cdot y \leftrightarrow \frac{1}{N}X*Y
$$
时域信号的加窗correspond to 频域的平滑过渡。
$w\cdot x$就是$X$使用$W$加窗滤波, $W*X$,这种平滑减少了方形窗口带来的旁瓣。

### 8.4.7 Correlation Theorem
相关性定理
对于所有的$x,y \in C^N$, $x \circledast y \leftrightarrow \overline{X}\cdot Y$
相关的计算也可以转换为卷积的计算
$$
\begin{aligned}
    (x\circledast y)_n \triangleq & \sum_{m=0}^{N-1}\overline{x(m)}y(n+m) \\
    =& \sum_{m=0}^{N-1}\overline{x(-m)}y(n-m), \space (m \gets -m) \\ 
    =& (FLIP(\overline{x})*y)_n \\
    \leftrightarrow & \overline{X}\cdot Y \\
\end{aligned}
$$

### 8.4.8 Power Theorem,
功率定理
对于所有的$x,y \in C^N$
内积等于傅里叶变换的内积的$1/N$
$$
\langle x,y \rangle = \frac{1}{N}\langle X,Y \rangle
$$

### 8.4.9 Rayleigh Energy Theorem(Parseval's Theorem)
瑞利能量定理，帕斯瓦尔定理
对于任意的$x\in C^N$
$$
||x||^2 = \frac{1}{N}||X||^2
$$
$$
\sum_{n=0}^{N-1}|x(n)|^2 = \frac{1}{N}\sum_{k=0}^{N-1}|X(k)|^2
$$

### 8.4.10 Stretch Theorem (Repeat Theorem)
对于所有的$x\in C^N$, $STRETCH_L(x)\leftrightarrow REPEAT_L(X)$
证明:
$$
STRETCH_{L,m} \triangleq \begin{cases}
    x(m/L), & \space m/L=integer \\
    0,   & \space m/L \not ={integer}\\
\end{cases}
$$
let $y\in C^M, M=LN$, 还要顶一个一个新的更密集的频率点, frequency grid, 与长度$M$相关的。$w_k^{'} = 2\pi k/M$, $w_k=2\pi k/N$
则
$$
Y(k)=\sum_{m=0}^{M-1}y(m)e^{-jw_k^{'}m}=\sum_{n=0}^{N-1}x(n)e^{-jw_k^{'}nL}, (n\triangleq m/L)
$$
然而
$$
w_k^{'}L\triangleq \frac{2\pi k}{M}L=\frac{2\pi k}{N}=w_k
$$
得证$Y(k)=X(k)$, by the modulo indexing of X, L copies of X are generated as $k$ goes from 0 to $M-1=LN - 1$

### 8.4.11 Downsampling Theorem (Aliasing Theorem)




