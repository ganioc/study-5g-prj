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
文中使用Mathematica来解这个问题，这里我会用Scilab来解同样的问题.
polynomial factorization, 分解为 n first-roder monic polynomials, each of which contributes one zero(root) to the product. This factoring business is often used when working with digital filters.

quadratic formula: 二次多项式方程, 
Linear: the unknowns are only multiplied by constants, may not be multiplied by each other or raised to any power other than 1. 线性系统N个防尘个非常好求解与非线性系统相比。这些都是线性代数, linear algebra要处理的东西。

引入了复数之后，所有的多项式方程n阶都有n个解,
给定任意的多项式
$$
p(x) = a_nx^n+a_{n-1}x^{n-1} + a_{n-2}x^{n-2} + ... + a_2x^2 + a_1x+a_0 \\
$$
我们可以把它写为
$$
\begin{aligned}
    p(x)&=a_n(x-z_n)(x-z_{n-1})(x-z_{n-2})\dotsi(x-z_2)(x-z_1) \\
    &=a_n \prod_{i=1}^{n}(x-z_i)
\end{aligned}
$$
the point $z_i$ 是多项式的根，可以是实数或者复数

## 2.5 复数运算
$z=x+jy$
$re\{z\} = x$
$im\{z\} = y$
复数的乘法
$$
\begin{aligned}
   z_1z_2 \triangleq & (x_1 + jy_1)(x_2 + j y_2) \\
    =& x_1 x_2 + jx_1 y_2 + jy_1x_2 + j^2y_1y_2 \\
    =& (x_1x_2 -y_1y_2) + j(x_1y_2 + y_1x_2)
\end{aligned}
$$

复平面, 一个2D的图像,坐标系可以是Cartesian, rectilinear coordinates, 也可以是polar coordinates. $(r, \theta)$
$$
r = \sqrt{x^2 + y^2} \\
\theta = \tan^{-1}(y/x)
$$
同样，逆转换位:
$$
x=r\cos(\theta)\\
y = r\sin(\theta) \\
$$
复数逆可以写为$\overline{z}$
$$
\overline{z} \triangleq x - jy \\
$$
### 2.5.3 基本关系
$$
z\overline{z} = |z|^2 \\
z\overline{z} = (x+jy)(x-jy) \triangleq |z|^2 \\[0.5em]
\frac{z}{\overline{z}} = \frac{r e^{j\theta}}{re^{-j\theta}} = e^{j2\theta}
$$
### 2.5.4 欧拉公式
$$
z=r e^{j\theta}
$$
一个推论, corollary, by setting $\theta=\pi$ to tet
$$
e^{j\pi} + 1 = 0
$$
还有
$$
\cos(\theta) = \frac{e^{j\theta} + e^{-j\theta}}{2} \\
\sin(\theta) = \frac{e^{j\theta} - e^{-j\theta}}{2j}
$$
### 2.5.5 De Moivre's 定理
$$
[\cos(\theta) + j\sin(\theta)]^n = [e^{j\theta}]^n = \cos(n\theta) + j\sin(n\theta) \\
$$

## 2.6 Numerical Tools in Matlab
如何求根呢? Scilab
找到了: poly(vec, vname, "roots|coeff");求解使用roots(p)


# chap 3 Proof of Euler's Identity
**Roots of Unity**
when a=1, we can write
$$
1^{k/M} = e^{j2\pi k/M}, k=0,1,2,3,\dotsi,M-1 \\
$$
$k=1$称为primitive Mth root of unity,
其它的根都是这个根的$k$次方
$$
e^{j2\pi k/M}=(e^{j2\pi/M})^k
$$
这个根式是如此重要以至于它们在信号处理文献里有专门的记号
$$
W_M^k \triangleq e^{j2\pi k/M},k=0,1,2,3,\dotsi,M-1,
$$
我们还会学到the Nth roots of unity are 用了产生DFT所需的所有正弦信号，IDFT. 第kth正弦信号表示为
$$
W_N^{kn} = e^{j2\pi kn/N} \triangleq e^{jw_kt_n} = cos(w_kt_n)+j\sin(w_kt_n), n=0,1,2,...,N-1 
$$
T为采样间隔，seconds
$w_k \triangleq 2\pi k/NT$
$t_n \triangleq nT$

### 3.1.6 Real Exponents
实数部分。计算实数部分。
泰勒技术展开，光滑曲线，处处可微
$$
f(x) = \sum_{n=0}^{\infin}\frac{f^{(n)}(x_0)}{n!}(x-x_0)^n
$$
对于音频信号而言，这个是满足的因为音频信号是在20kHz以内的。
当然对于调制信号来说，也是成立的。

### 3.1.7 虚数部分 Imaginary Exponents
For $f(x) = e^x$
$$
e^x = \sum_{n=0}^{\infin}\frac{x^n}{n!} = 1 + x + \frac{x^2}{2} + \frac{x^3}{3!} + \dotsi
$$
代入 $x=j\theta$, 将实部和虚部分离
$$
re(e^{j\theta}) = 1- \frac{\theta^2}{2} + \frac{\theta^4}{4!}+\dotsi\\[0.5em]
im(e^{j\theta}) = \theta - \frac{\theta^3}{3!} + \frac{\theta^5}{5!} + \dotsi\\
$$

## 3.3 泰勒级数的残余项
The one that falls out naturally here is called "Pade" approximation. 使前n阶导数在$x=0$ 处的值为0.Maximally flat at the point. The slope of the error to be exactly zero at x=0. 
All degrees of freedom in the polynomial coefficients were devoted to minimizing the approximation error and its derivatives at x= 0. 这个近似误差当远离x=0时会恶化。

为了获得一个更均匀的近似，over some interval I in x, other kinds of error criteria may be deployed. economizaiton of series. Nowadays call it polynomial approximation. 

音频信号时无限可求导的。一个信号不能同时是时间有限和频率有限的。理论上，lowpass filtering, 会是audio signal last forever in time. 在实际中，信号有一个开始和结束点，我们必须承认所有的信号都有着无限的带宽，在turn-on , turn-off transients之间。

# chap 4 Logarithms, Decibels, Number Systems
$e^{j\pi}= -1$,so that
$$
ln(-1) = j\pi
$$
因此所有的复数的ln值可以是, $\ln(x) = j\pi + \ln(|x|)$

**DB SPL**
Sound Pressure Level, 声压强, 0 phons, 1000 Hz sinusoid. 就是$20uPa$, Thresh of pain is 120dB, 
sone amplitude scale, in terms of actual loudness perception experiments. 
phon amplitude scale, 

生成信号的一个例子,
- Windows
- zero padding? 这个是什么意思呢?
  - 是一个简单的概念，在时域信号后添加0以增加时间长度, 原因
  - 使得sample样点数量为2的次方, 
  - FFT的频率分辨率,
- spectral interpolation

在具体做频谱分析之前需要做些什么?

做离散傅里叶变换时频率的间隔为$F_s/N$, $N$为输入时间序列的长度。在尝试估计正弦波振幅时，如果频率无法对应到DFT bin, 则可能导致估计不准确。可以通过填零来处理，但是并不能提高频率的分辨率。

**Filter Design Using Scilab**
```cpp
win=window('hm',n) // hamming windows
// Kaiser Window
win=window('kr', n, alpha);
// chebyshev window
win = window('ch',n,par)
// Window based Linear Phase FIR fiter
[wft, wfm,fr] = wfir(ftype, forder, cfreq, wtype, fpar)
// IIR Digital filter

```
 
### 4.2.3 Dynamic Range
动态范围
最大信号，和quantization noise, 量化噪声
Let $q$ be the quantization level, 这样最大的量化误差幅度为$q/2$, 方差为, noise power, $\delta_q^2 = q^2/12$. rms level of the quantization nosie为$\delta_q = q/(2\sqrt{3}) \approx 0.3q$, about $60\%$ of the maximum error.
人类听力的动态接收范围为0~120dB SPL. 磁带 magnetic tape 是55 dB. Dolby A 增加了10dB, that will fit on magnetic tape, 通过方式, DBX adds 30dB at the cost of more transient distortion. 

## 4.3数字音频的线性数字系统
### 4.3.1 PCM
Pulse Code Modulation, 脉冲编码调制,raw binary format, 16-bit, 2's complement PCM data. 
### 4.3.2 Binary Interger Fixed-Point Numbers
大多数计算机语言值提供两种类型的数, floating-number 和 integer fixed-point. 二进制数据. 浮点数和整数.

### 4.3.3 Fractional Binary Fixed-Point Numbers
分数二进制定点数,
DSP chips, 芯片, 也是用了2的补码。

### 数字音频需要多少bit呢?
120dB SPL的范围，如果一个bit代表6dB动态范围的，我们需要20bit。 我们会将量化误差略小于听力底限。1024 FFT, 24 fixed-point bits pretty reasonable to work with.

soudfiles 通常包含16 bit samples. 2 bytes in each audio sample. L denote the least-significant byte, M the most-significant byte. 那么一个16-bit 的字，可以自然地表示为$[M,L]]= M\cdot 256 + L$,

## 4.4 Logarithmic Number Systems for Audio
音频的对数系统,
The $u\text{-} law$ amplitude-encoding format 在小信号幅度的时候是线性的，在大幅度信号时是对数的。
### 4.4.1 Floating-Point Numbers
浮点数, exponent, significand, 有效数, sign-bit, The normalized number between $1/2$ and $1$ is called the significand. It holds all the significant bits of the number.

浮点数的表示方法与科学表示法类似。let $\tilde{x} = x\cdot 2^{-E}$
A single-precision floating point word is 32 bits long, 4 bytes, consisting of 1 sign bit, 8 exponent bit, and 23 significand bits.
$$
S\space EEEEEEEE\space MMMMMMMMMMMMMMMMMMMMMMMMM
$$
A double-precision floating point is 64 bits long, 1 sign bit, 11 exponent bits, 52 significand bits. 

在intel Pentium processor, 有一种extended precision format, 扩展精度格式, 80 bits, 10个字节。1 sign bit, 15 exponent bits, 64 significand bits. 

The MPEG-4 audio compression standard, 支持使用音乐合成器算法的压缩，规定了数值计算，任何的MPEG-4 audio 解码器都要支持32-bit 单精度浮点数。

### 4.4.2 Logarithmic Fixed-point Numbers
对数定点数
编码为log base 2的二进制编码，对信号采样幅度的。
一个16-bit的对数定点数格式包括1个sign bit, 5个characteristic bit(integer part, 整数部分), 10个mantissa 尾数, S CCCCC MMMMMMMMMM,

5bit的特征比特, $6dB * 2^5 = 192dB$

### 4.4.3 Mu-law Companding
A companding operation compresses dynamic range on encode and expands dynamic range on decode. 在数字电话网络和语音modem里面，标准的CODEC chips使用一个简单的8-bit u-law format, 
采样数据转换为8-bit的$u-law$编码格式
$$
\hat{x}_u \triangleq Q_u[log_2(1+ u|x(n)|)]
$$
$Q_u$是一个量化器,生成3-bit characteristic bits, 4-bit mantissa, 使用一个小的表格查询尾数 mantissa.
3kHz带宽的语音，使用标准的编解码芯片的采样速率为8kHz, 

对于宽带语音, wideband audio, 采样速率可以为44.1kHz, 96kHz, 最低的频率为20Hz, bass guitar的最低音符为$E1 = 41.2Hz$, 大钢琴的最低音符为$A0=27.5Hz$

## 4.5 Round-off Error Variance
舍入误差的方差
量化误差的噪声功率为$q^2/12$, 其中$q$为量化步阶。
量化误差为一个均匀分布的随机变量between $-q/2$ 和 $q/2$之间。概率密度方程为
$$
p_e(x) = \begin{cases}
  \frac{1}{q}, |x| \leqslant \frac{q}{2} \\
  0,|x| > \frac{q}{2} \\
\end{cases}
$$
The probability taht a given roundoff errro $e(n)$ lies in the interval $[x1,x2]$ is given by
$$
\int_{x_1}^{x_2}p_e(x) dx = \frac{x_2 -x_1}{q}
$$
随机变量的均值定义为
$$
u_e \triangleq \int_{-\infin}^{\infin}xp_e(x)dx = 0
$$
概率分布经常用它们的moments来表示。The nth moment of the pdf $p(x)$ is defined as
$$
\int_{-\infin}^{\infin}x^np(x)dx
$$
随机变量的方差variance定义为pdf的second central moment.
$$
\delta_e^2\triangleq \large{\epsilon}\{ [e(n) - u_e]^2 \}= \int_{-\infin}^{\infin}(x-u_e)^2 p_e(x)dx
$$
"Central" means the moment is evaluated after subtracting out the *mean*. 
$$
\delta_e^2 = \int_{-q/2}^{q/2}x^2 \frac{1}{q}dx = \frac{1}{q} \frac{1}{3}x^3|_{-q/2}^{q/2} = \frac{q^2}{12}
$$

# chap 5 Sinusoids and Exponentials
正弦函数和指数函数

定义域$-\pi \leqslant \phi \lt \pi, \pi \in [-\pi, \pi)$.

A-440 tuning fork, 音叉, 振动频率, 
$$
x(t) = A\sin{(2\pi 440 t + \phi)}
$$
正弦波是最基本的物理运动方式
正弦波是线性系统的eigenfuncitons, 本征函数， 用于分析滤波器中的reverberator(混响器，反射器), equalizers(平衡器),auditory nerve(听觉神经),  

in-phase, quadrature,
每一个in-phase, 90度差的phase-quadrature component的合成,都可以表示为一个单独的正弦波，该正弦波有一定的相位延迟。

一个正弦波有一个重要特征，就是closed with respect to addition. 将同频率的信号，各种信号，不同的幅度，不同的相位，加在一起的话，还是会得到一个同样频率的信号。

对每一个线性、时不变系统，LTI, copying, scaling, delaying, summing it's input signals 来生成输出信号output signals. 当一个频率的正弦信号输入的话，同样频率的信号会出现在输出。系统只会改变信号的幅度和相位。所以LTI 系统的eigenfunctions就是本征函数， eigenfunctions. 如果系统是非线性，或者时变的话，那么系统输出会产生新的频率。

### 5.1.5 Constructive and Destructive Interference
增强性地，削弱性地干扰。 
混响器在一个房间里生成nodes,和antinodes,对正弦波, 可以用simple comb filter来表示。梳状滤波器的输入是正弦波,对于一个线性和时不变系统而言，输出也是正弦波。

## 5.2 Exponentials
指数函数 $a(t) = A e^{-t/\tau}, t \geqslant 0$
$\tau$为指数函数的时间常数, 指数衰减的重要性。在自然界中, 一个线性先真气，例如乐器的弦，木管孔，在响应暂时的激励时，它的衰减都是表现为指数衰减的形式。在混响室内，当直接的声音停止时，混响的能量在房间内的衰减也是指数衰减的。所有非激励的震荡衰减都是指数形式的。
指数增长发生时，当一个量的增长速度与当前的数量成正比时。指数增长是不稳定的，因为没有什么东西是可以指数成长的，一定会遇到一些实际的限制。

### 5.2.2 Audio Decay Time(T60)
音频信号的衰减时间,$1/e$ 太小了，在结构声学里，更加常用的一个衡量参数是$t_{60}$, or $T60$, 衰减了60dB的时间,也就是$10^{-60/20} = 0.001$
$$
t_{60} = \ln(1000)\tau \approx 6.91\tau 
$$

## 5.3 Complex Sinusoids
复数正弦信号。按照Euler's Identity
$$
e^{j\theta} = \cos(\theta) +j\sin(\theta)
$$
Setting $\theta = \omega t + \phi$, 我们得到复正弦信号的表达式
$$
s(t) \triangleq Ae^{j(\omega t + \phi)}= A\cos(\omega t + \phi) + jA\sin(\omega t + \phi)
$$
恒包络信号
$$
|s(t)| \equiv A
$$
constant modulus, $\equiv$ identically equal to for all $t$
相位为 $\angle s(t) = \omega t + \phi$
The derivative of the phase of the complex sinusoid gives its frequency
$$
\frac{d}{dt}\angle s(t) = \omega = 2\pi f
$$

### 5.3.1 Circular Motion
counter clockwise, clockwise, $e^{j\omega t}$
$\omega > 0$, a positive-frequency sinusoid,
$\omega < 0$, a negative-frequency sinusoid, 

### 5.3.2 Projection of Circular Motion
圆周运动的投影, 在x轴、y轴上的投影。
复信号在正交信号集上的投影,

### 5.3.4 Analytic Signal and Hilbert Transform Fitlers
analytic signal: a signal without negative-frequency component
对于连续时间信号，每一个解析信号$z(t)$都可以表示为
$$
z(t) = \frac{1}{2\pi} \int_{0}^{\infin}Z(w)e^{jwt}dw
$$
其中$Z(w)$为复系数(设置了幅度和相位),
一个解析信号可以表示为一个复信号和它的共轭值之和。在数学上，如果$x(t)$是一个实数信号，它对应的解析信号，表示为$x_a(t)$形式的话，为:
$$
x_a(t) = x(t) +  * HilbertTransform[x(t)]
$$

一个实际的正弦信号，可以转换为一个正频率复正弦信号$Aexp[j(wt+\phi)]$, by simply generating a phase-quadrature component$A\sin(wt+\phi)$
$$
Ae^{j(wt+ \phi)}=A\cos(wt+\phi) + jA\sin{(wt+\phi)}
$$
对于更加复杂的信号，(由多个正弦信号组成),可以构造一个滤波器，对所有的信号$\cos(wt)$延迟1/4周期, 这个被称为Hilbert transform filter. $H_t\{x\}$, 对正频率相移$-\pi/2$, 对负频率相移$\pi/2$.
使用实信号$x(t)$和它的希尔伯特变换$y(t)=H_t\{x\}$组合成一个新的复信号$z(t)=x(t) + j y(t)$, 则$z(t)$就是这个解析信号，不包含负频率的，与$x(t)$对应的。

在这个例子里面
$$
x(t)=2\cos{(w_0t)} = exp(jw_0t) + exp(-jw_0t)
$$
计算$y(t)$
$$
y(t) = exp(jw_0t - j\pi/2) + exp(-jw_0t +j\pi/2) \\
= -jexp(jw_0t) +jexp(-jw_0t) \\
= 2\sin(w_0t)
$$
那么这个解析信号就是
$$
z(t)=2\cos(w_0t) + j2\sin(w_0t) = 2e^{jw_0t}
$$
对信号$A(t)\cos(w_0t)$,则有$z(t)\approx A(t)e^{jw_0t}$

### 5.3.5 Generalized complex sinusoids
复正弦信号,如果允许 exponential amplitude envelope $y(t)\triangleq Ae^{st}$
$A$和$s$时复数, and further defined as
$$
A_o = Ae^{j\phi}\\
s_o = \sigma + jw \\
y(t) = A_oe^{s_0t} \\
= Ae^{\sigma t}[\cos(wt +\phi) + j\sin(wt+\sigma)]\\
=  Ae^{-t/\tau}[\cos(wt +\phi) + j\sin(wt+\sigma)]\\
$$

### 5.3.6 Sampled Sinusoids采样正弦信号
在离散音频信号处理领域，采样频率需要大于40kHz, CD音质, $f_s=44.1kHz$, Sony使用$f_s=44.025kHz$, DAT digital audio tape使用$f_s = 48kHz$

$T\triangleq 1/f_s$为sampling period, replace t by $nT$, $n$为采样序列
$$
\begin{aligned}
  y(nT)&= Ae^{j\phi}e^{(\sigma + jw)nT} \\
    &= A[e^{\sigma T}]^n[\cos(wnT + \phi)+j\sin(wnT+\phi)]
\end{aligned}
$$

我们获得一个离散时间complex sinusoid.
$$
x(n)\triangleq = z_0z_1^n=Ae^{j\phi}e^{jwnT}, n=0,1,2,3,\dotsi
$$
我们称$z_0$为sinusoidal phasor, 相位, $z_1^n$为sinusoidal载波

**为什么称Phasor相位重要?**
LTI线性时不变系统,对信号只做4种操作: copying, scaling, delaying, adding.
Weighted sum. delayed copies of a complex sinusoid:
$$
y(n) = \sum_{i=1}^Ng_ix(n-d_i)
$$
$g_i$是权重值weighting factor, $d_i$是$ith$ delay, $x(n)=e^{jwnT}$
载波项$e^{jwnT}$可以被提取出来
$$
y(n)=e^{jwnT}\sum_{i=1}^{N}g_ie^{-jwd_iT}
$$

对于DFT来说，内积可以写为
$$
\begin{aligned}
  \langle y,x \rangle \triangleq & \sum_{n=0}^{N-1}y(n)\overline{x(n)}\\
  =& \sum_{n=0}^{N-1}y(n)e^{-j2\pi nk/N} \\
  \triangleq & DFT_k(y) = Y(w_k)
\end{aligned}
$$
DTFT, Discrete Time Fourier Transform,离散时间傅里叶变换, 允许无限数量的采样而不是N个采样， 这样的话频率是连续的
$$
\langle y,x \rangle = \sum_{n=0}^{\infin}y(n)e^{-jwnT}\triangleq DTFT_w(y)
$$
这里假设n<0时，信号为零,单边带傅里叶变换
如何设$x(n)=z^n$, then 内积变为
$$
\langle y,x \rangle = \sum_{n=0}^{\infin}y(n)z^{-n}
$$
这就是z变换的定义,这是DTFT的一般形式。DTFT等价于在Z平面的单位元上的变换和计算。那么将计算从单位圆上扩展到整个复平面，有什么好处呢?

* 允许不稳定的指数信号的转换，只要增长的速率小于指数信号
* z transform有一个deeper代数结构 over the 复平面, 例如有限信号的z变换只是z平面上的一个多项式polynomial. 它的特性可以从z平面上的零值获知。指数信号的z变换只是一个点。z变换在那个电商趋于无穷。pole of the transform.Poles and Zeros 在recursive digital filters的分析中被广泛使用. 任何有限阶，线性，时不变，离散时间系统都是由z平面上的零点和极点来确定的
  
在连续时间场景，我们有傅里叶变换，将y映射到连续时间正弦信号$x(t)=e^{jwt}$,内积为
$$
\langle y,x \rangle = \int_{0}^{\infin}y(t)e^{-jwt}dt \triangleq Y(w)
$$

最后z变换的连续时间情况是拉普拉斯变换，将信号映射到指数增长或衰减的正弦信号上
$$
\langle y,x \rangle = \int_{0}^{\infin}y(t)e^{-st}dt \triangleq Y(s)  
$$
在s平面的$jw$ axis上，傅里叶变换与拉普拉斯变换相同。

### 5.3.10 比较模拟和数字复平面
在信号处理领域，习惯于使用$s$作为拉普拉斯变换的变量做连续时间分析， $z$作为离散时间分析的z变换的变量. s平面和z平面都是复平面。

另外还有其它的变化，比如STFT, short-time Fourier Transforms, wavelet transforms, projecting onto windowed complex sinusoids.


# chap 6 Geometric Signal Theory
几何信号理论,










