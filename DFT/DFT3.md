# chap 9 Applications of the DFT
DFT的应用示例

一些使用Matlab的一些FFT分析的实际的例子。傅里叶变换原理提供了理解谱分析的思想宝库。

## 9.1 Spectrum Analysis of a Sinusoid
正弦函数的谱分析, Windowing, Zero-Padding, FFT

### 9.1.1 FFT of a Simple Sinusoid
$x(n) = \cos(w_xnT)$
这里我们选择:
$w_x = 2\pi(f_s/4)$, 采样频率为$f_s$,
$T=1$, 采样速率为1,
因为我们使用FFT, 信号长度N必须是2的幂次方,
对于单位频率, fs=1,
峰值出现在f=0.25, f=0.75,f=-0.25,
对于N=64, a spectral peak amplitude of 32 = (1/2)64,
因为
$$
\begin{aligned}
    DFT_k(\cos(w_kn))&=\sum_{n=0}^{N-1} \frac{e^{jw_xn}+e^{-jw_xn}}{2}e^{-jw_kn}\\
    &= \sum_{n=0}^{N-1}\frac{e^{j(w_x-w_k)n}+e^{-j(w_x+w_k)n}}{2}\\
\end{aligned}
$$
当$w_x-w_k=0$时,我明白了，第二项加在一起正好为0，第一项为1时，加在一起是$N/2$
k=1/4*N=16时,有一个峰值,
k=-1/4时，也有一个峰值，正好在3/4*N=48,
因为index从1开始，所有峰值在17,65, bin number,
在其他地方的值非常小，不为0.因为沿圆周均匀分布的矢量和，应该为0吧!

### 9.1.2 FFT of a Not-So-Simple Sinusoid
这里产生了spectral leakage, into all the bins at this frequency,
实在是因为采样出来的时域信号，不够完美导致。

### 9.1.3 FFT of a Zero-Padded Sinusoid
增加bin的数目就可以精细化频谱,

### 9.1.6 Hanning-windowed complex sinusoid
汉明窗口,
不像blackman窗口对旁瓣的抑制性这么强, 但是它的主瓣更窄一些, roll off very quickly vs frequency. 

# 附录A
## 矩阵matrices
square matrix, 方矩阵
transpose of a real matrix, 矩阵的转置， $A^T[i,j]=A[j,i]$
complex matrix, 复数矩阵, $A \in C^{M\times N}$
conjugating transpose operation, 共轭转置, Hermitian transpose,
$A^{*}[i,j] = \overline{A[j,i]}$
column vector, 列向量
row vector, 行向量,

**矩阵的乘法**
$A\cdot B \not ={ B\cdot A}$
$(AB)^T=B^TA^T$
identity matrix, 单位矩阵
A times a vector $x$, linear transformation of $x$,
matrix Toeplitz,$A^T[i,j] = A^T[i-j]$, constant along all diagonals

**求解线性方程**
$Ax=b$
$x=A^{-1}b$, 逆矩阵, 
determinant of the matrix A, 
Matlab based on LINPACK,
如何求逆矩阵,

# 附录B,Sampling Theory 采样理论
When sound is sampled, we call it digital audio.
44,100 samples per second.
once every 23 microseconds, 

### B.1.1 Reconstruction from samples, 采样重构
Pictorial Version,
图像版本,
每个样本，采样，可以被认为是一个scaling, location of a sinc function.
加在一起生成原始信号，
Gibb's overshoot, 
$$
sinc(F_st)\triangleq \frac{\sin(\pi F_st)}{\pi F_st}
$$
$F_s$是采样率，samples per second, t 表示了时间 in seconds 秒,

$x(t)$ 必须带限到less than half the sampling rate. 假定信号在频率的$F_s/2$ 以上的能量为零。
Let $X(w)$ denote the Fourier transform of $x(t)$,
$$
X(w) \triangleq \int_{-\infin}^{\infin}x(t)e^{-jwt}dt
$$
可以Uniquely reconstructed from the samples $x(nT_s)$ by summing up shifted, scaled, sinc functions
$$
\hat{x}(t) \triangleq \sum_{n=-\infin}^{\infin}x(nT_s)h_s(t-nT_s)\equiv x(t)
$$
where
$$
h_s(t)\triangleq sinc(F_st)\triangleq \frac{sin(\pi F_st)}{\pi F_st}
$$
sinc function是一个理想的低通滤波器的冲激响应。这意味着它的傅里叶变换在频域上是一个正方形的窗口。这里sinc函数, 对应于理想低通滤波器，截止频率在采样频率的一半。

## B.2 Aliasing of Sampled Signals
采样信号的混淆
定理:
连续时间aliasing theorem, Let $x(t)$表示任意的信号，拥有傅里叶变换形式
$$
X(jw)\triangleq \int_{-\infin}^{\infin}x(t)e^{-jwt}dt
$$
let $x_d(n)=x(nT_s), n=\dotsi,-2,-1,0,1,2,\dotsi,$
表示了按照$T_s$秒间隔的$x(t)$的采样值, 表示离散时间的傅里叶变换(DTFT)为
$$
X_d(e^{j\theta})=\sum_{n=-\infin}^{\infin}x_d(n)e^{-j\theta n}
$$
这样采样信号$x_d$的频谱就与原始的连续时间信号$x$的频谱相关
$$
X_d(e^{j\theta})=\frac{1}{T_s}\sum_{m=-\infin}^{\infin}X[j\big(\frac{\theta}{T_s}+m\frac{2\pi}{T_s})]
$$
上述项中$m\not = 0$的项被称为aliasing terms. 混淆进了base band, $[-\pi/T_s, \pi/T_s]$. 混淆频谱的内容包含了复数值, 因此, aliasing components 可以被移除，只有当幅度和相位都得知的情况下。

证明:
将$x(t)$写为反傅里叶变换的形式
$$
x(t)=\frac{1}{2\pi}\int_{-\infin}^{\infin}X(jw)e^{jwt}dw
$$
将$x_d(n)$写为反DTFT变换的形式
$$
x_d(n)=\frac{1}{2\pi}\int_{-\pi}^{\pi}X_d(e^{j\theta})x(t)e^{j\theta t}d\theta
$$
where $\theta \triangleq 2\pi w_d T_s$表示的是归一化了的离散时间频率变量, discrete-time frequency variable.
反傅里叶变换可以分为一组有限积分之和，每一个积分的长度都是$\Omega_s=2\pi F_s=2\pi/T_s$
$$
\begin{aligned}
x(t) &= \frac{1}{2\pi}\int_{-\infin}^{\infin}X(jw)e^{jwt}dw\\
&=\frac{1}{2\pi}\sum_{m=-\infin}^{\infin}\int_{(2m-1)\pi/T_s}^{(2m+1)\pi/T_s}X(jw)e^{jwt}dw \\
&= w \gets m\Omega_s \\ 
&= \frac{1}{2\pi} \sum_{m=-\infin}^{\infin}\int_{-\Omega_s/2}^{\Omega_s/2}X(jw+jm\Omega_s)e^{jwt}e^{j\Omega_smt}dw \\
&= \frac{1}{2\pi}\int_{-\Omega_s/2}^{\Omega_s/2}e^{jwt}\sum_{m=-\infin}^{\infin}X(jw+jm\Omega_s)e^{j\Omega_smt}dw
\end{aligned}
$$
Now we sample this representation for $x(t)$ at $t=nT_s$ to obtain
$$
\begin{aligned}
x_d(n)&=x(nT_s)\\
&=\frac{1}{2\pi}\int_{-\Omega_s/2}^{\Omega_s/2}e^{jwnT_s}\sum_{m=-\infin}^{\infin}X(jw+jm\Omega_s) e^{j(w\pi/Ts)mnT_s}dw\\
&=\frac{1}{2\pi}\int_{-\Omega_s/2}^{\Omega_s/2}e^{jwnT_s}\sum_{m=-\infin}^{\infin}X(jw+jm\Omega_s)dw\\
\end{aligned}
$$
Since $n$ and $m$ are integers. 归一化频率为$\theta^{'}=wT_s$
$$
x_d(n)=\frac{1}{2\pi}\int_{-\pi}\pi e^{j\theta^{'}n}\frac{1}{T_s}\sum_{m=-\infin}^{\infin}X[j(\frac{\theta^{'}}{T_s}+m\frac{2\pi}{T_s})]d\theta^{'}
$$

## B.3 香农的采样定理
定理: 让$x(t)$作为任何的连续时间信号，具有连续傅里叶变换形式
$$
X(jw)=\int_{-\infin}^{\infin}x(t)e^{-jwt}dt
$$
如果没有频率混淆的话, $X(jw)=0$,对任意的$|w|\geqslant \Omega_s/2$,上述的无限的求和减少为只有一项, $m=0$ term,
$$
X_d(e^{jw_dT_s})=\frac{1}{T_s}X(jw_d), w_d\in [-\pi/T_s, \pi/T_s]
$$
从采样$x(nT_s)$重构$x(t)$, 我们只要对zero-extended DTFT进行反傅里叶变换, 即
$$
\begin{aligned}
x(t)&= IFT_t(X)=\frac{1}{2\pi}\int_{-\infin}^{\infin}X(jw)e^{jwt}dw \\
&= \frac{1}{2\pi}\int_{-\Omega_s/2}^{\Omega_s/2}X(jw)e^{jwt}dw\\
&=\frac{1}{2\pi}\int_{-\Omega_s/2}^{\Omega_s/2}X_d(e^{j\theta})e^{jwt}dw \\
&= IDTFT_t(X_d)\\
\end{aligned}
$$
$$
x(t)=(x*h)(t) \\
h(t-nT_s)=sinc(t-nT_s)\\
$$

## B.4 Another path to Sampling Theory
另一种方式来解释采样理论。
Consider $z_0\in C$, with $|z_0|=1$, we can write $z_0$ in polar form was
$$
z_0 = e^{j\theta_0}=e^{jw_0T_s}
$$
$\theta_0, w_0, T_s$都是实数。
生成一个集合序列,根据$z_0$生成序列
$$
x(t_n)=z_0^{n}=e^{j\theta_0 n}=e^{jw_0t_n}
$$
其中$t_n = nT_s$, 连续的$z_0$的整数幂，形成了具有单位幅度，零相位的采样复正弦函数。定义采样间隔为$T_s$, $w_0$是每秒的$radian frequency$in radians.

### B.4.1 几何序列表示了什么样的频率呢?
在复平面上, 沿着单位圆,$z_0^n$的移动表示为$\theta_0 = w_0T_s$, 既然$e^{j(\theta_0 n + 2\pi)} = e^{j\theta_0 n}$, 角度步进$\theta_0 \gt 2\pi$与步进$\theta_0 - 2\pi$是相同的。因此，我们可以限制angular step $\theta_0$ 的范围在$2\pi$, 为了避免ambiguity.
还记得我们支持正频率，和负频率，为顺时针和逆时针的转动。
$$
\cos(w_0t_n)=\frac{1}{2}e^{jw_0t_n}+\frac{1}{2}e^{-jw_0t_n}\\
\sin(w_0t_n)=-j\frac{1}{2}e^{jw_0t_n}+\frac{j}{2}e^{-jw_0t_n}\\
$$
$2\pi$范围可以写为以0对称，$\theta_0 \in [-\pi, \pi]$
Since $\theta_0 = w_0T_s=2\pi f_0T_s$, 与频率范围相对应
$$
w_0\in [-\pi/T_s, \pi/T_s]\\
f_0 \in [-F_s/2, F_s/2] \\
$$
$+F_s/2$和$F_s/2$对应z-plane上同样的点$z=-1$, 技术上说，这个可以认为是频率的aliasing, 混叠。
我们可以定义一个有效的范围,digital frequencies, 数字频率，
$$
\begin{aligned}
    \theta_0 & \in [-\pi, \pi) \\
    w_0 \in [-\pi/T_s, \pi/T_s) \\
    f_0 \in [-F_s/2, F_s/2) \\
\end{aligned}
$$
我们选择了largest negative frequency, 与2的补码的表示方法相对应。
我么看到均匀分布的采样可以表示频率$f_0$在范围$[-F_s/2, F_s/2)$, 这种形式可以看做输入信号的低通滤波，移除了所有$F_s/2$以及以上的其它频率。这样的滤波器称为anti-aliasing filter. ADC, analog to digitcal converter, within a IC chip, such as CODEC, codec/decodec, or multimedia chip.

### B.4.2 从采样恢复连续信号
对于一个理想的带限信号，如何恢复原来的连续信号波形呢? given $x(t_n), n=0,1,2,\dotsi,N-1$, 如何计算任意的$t$下的$x(t)$呢?
一个合理的对$x(t)$的定义可以依据与$x(n)$的DFT,离散傅里叶变换
$$
X(e^{jwk})=\sum_{n=0}^{N-1}x(t_n)e^{-jw_kt_n},k=0,1,2,\dotsi,N-1
$$
$X(e^{jw_k})$提供了频率$w_k$上的正弦分量的幅度和相位，我们可以使用这些频点上的连续正弦信号的和来重构$x(t)$信号。
$$
x(t)=\sum_{k=0}^{N-1}X(e^{jw_k})e^{jw_kt}
$$
我们知道某个频点的采样复正弦信号，这种方法是有意义的。每一个这种正弦信号$e^{jw_kt}$在$NT_s$秒之后会重复。这个被称为DFT的周期性扩展, 这个源自事实，我们只有N个采样，在开始时, 这种假定在数学中隐含了,periodic extension, 周期性扩展。然而，在实际中, 在有限的采样信号外，假定信号都为零，更加常见。
$$
x(t)=\begin{cases}
    \sum_{k=0}^{N-1} X(e^{jw_k})e^{jw_kt}, & 0\leqslant t \leqslant(N-1)T_s \\
    0, & otherwise
\end{cases}
$$
非零的时间间隔可以选做任意的长度为$NT_s$的间隔。可以是$[-T_s(N-1)/2, T_s(N-1)/2 - 1]$, 这里允许了正时间，和负时间。Zero-phase filtering, 零相位滤波，就是使用这种定义的。
Chopping 这N个DFT sinusoids，在N个采样范围之外为零，工作的很好，如果原始信号从零慢慢升起，然后消失。否则，这种chopping会带来问题，在边缘处。

能够正常工作吗?
有几个前提,
* 重构的信号$x(t)$是带限的， $[-\pi, \pi)$, 傅里叶变换在$|w| \gt \pi/T_s$之外$X(w)$都为零，在truncated case , not quite true
* 重构的信号$x(t)$与$x(t_n)$信号pass through,

带限信号的插值是唯一的吗？如果这是正确的话。我们需要使用sinc函数之和来重新构造信号根据香农的采样理论。additive synthesis, 加法合成法, 一个N DFT正弦信号的和只能生成一个周期信号, 在时间上对这个信号截断，会带来其它的频率的信号。truncated 信号是带限的，因此这个信号是错的，不是原始的信号。

对于傅里叶变换来说，没有函数可以是同时时间有限和频率有限的。因此一个真正的带限插值，必须是一个无限时间的信号，就如sinc函数一样，必须注意到, sincs之和经过了所有采样时间点上的zero extension区域。









