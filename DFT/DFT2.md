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


