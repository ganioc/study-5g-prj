# 通信之道
从第9章，基本通信链路，开始，

基本的无线通信链路，声音信号转换为电信号，这个电信号被调制到一个载波频率$f_c=\frac{w_c}{2\pi}$上，通过发射天线发射出去。接收放的天线接收到这个信号后，再通过解调器把它转换成电信号，驱动喇叭发出声音。

发射方有两个核心部件，modulator, Tx antenna;接收方也有两个核心部件Rx antenna和Demodulator.
无线通信是以电磁波为载体的，天线的作用是发射和接收电磁波。

法拉第，赫兹，麦克斯韦

## 调制-频谱搬移
假定$s(t)$是一个余弦信号
$$
s(t) = \cos{wt}
$$
调制就是乘上一个角频率为$w_c = 2\pi f_c$的余弦信号，得到要发射的射频信号
$$
s_{RF}(t) = s(t) \cos{w_ct}= \cos{wt}\cos{w_ct} \\[0.5em]
= \frac{\cos{（w_c- w)t} + \cos{(w_c +w)t}}{2}
$$

### 9.3 相干解调
在解调器当中，用一个载波信号$\cos{w_ct}$乘以接收到的信号，得到
$$
\cos{wt}\cos^2{w_ct} = \cos{wt}(\cos{(2w_ct +1)}/2) \\
= s(t)/2 + \cos{wt} \cos{2w_ct}/2
$$
解调后的信号包括了一个低频信号$s(t)$和一个高频信号$\cos{wt}\cos{2w_ct}$,用一个低频滤波器把高频信号成分滤掉，就得到了要传递的基带信号$s(t)$

对于一个一般性的基带信号$s(t)$, 假设其频谱为
$$
\textcolor{blue}{基带信号}  \\
S(w) = F{\lbrace s(t) \rbrace}
$$
载波的频谱为
$$
F\lbrace \cos{(w_ct)} \rbrace = \pi \delta(w - w_c) + \pi \delta(w + w_c)
$$
则已调信号的频谱为
$$
\begin{aligned}
    S_RF(w) &= F\{ s(t) \cos{w_ct} \} \\
    &= \frac{1}{2\pi}S(w) * [ \pi\delta(w - w_c) + \pi\delta(w + w_c)] \\
    &= \frac{1}{2}[S(w-w_c) + S(w+w_c)]
\end{aligned}
$$
这个过程叫相干解调。

## 9.4 非相干解调
也称为包络检测技术，但是使用这一技术要求基带信号为非负，这可以通过在原基带信号当中叠加一个直流信号实现
例如，非负基带信号$s(t)=2 + \cos{(wt)}$
经过调制后的信号为$S_RF(t) = s(t)\cos{(w_ct)}$
因为基带信号是非负的，所以已调信号的包络就是基带信号

## 9.5 载波恢复
载波恢复就是从接收到的信号当中恢复出载波信号。知道了载波的周期和相位，也就恢复了载波信号。

载波信号恢复时存在$\pi$的相位模糊，也就是说，把载波移动相位$\pi$,或者加一个负号也是可以的。

推导公式要有方向，这个方向来自于直觉，来自于对问题的宏观把握。

## 9.6 锁相环
锁相环是相干解调当中用到的关键部位，包括了3个关键部件，鉴相器，环路滤波器和压控振荡器。

假设VCO的输出信号是一个余弦函数:
$$
c(t) = \cos{[\theta(t)]}
$$
其中香味函数表示为
$$
\theta{(t)} = 2\pi f_0t + \hat\phi(t)=2\pi f_0 t + K\int_{-\infin}^{t}u_c(\tau)d\tau
$$
$\theta(t)$对$t$的导数就是瞬时角频率
$$
w(t) = \frac{d}{dt}\theta(t)=2\pi f_0 + Kv
$$
这样就实现了用输入电压来控制频率
如果输入电压$u_c(t)$是一个设么形状的波形，由于积分的作用，$\theta(t)$总是一个连续函数，不会出现跳变。所以$c(t)$的波形也总是连续的。

关于锁相环的系统特性、数字锁相环等，可以参考更加专业的书籍

## 9.7 平方环
由于$s^{2}(t)$是非负信号，而且对于载波$f_c$来说是一个慢变信号，它的作用可以合并到VCO的控制灵敏度里面。VCO通过稍稍改变锁定后的相差就可以跟随驱动信号幅度的变化，因此数据信息对锁相环的影响不大。

## 9.8 Costas环

## 9.9 双边带信号
## 9.10 单边带信号
## 9.11 Hilbert变换
做一个定义
$$
\hat{s(t)} = s(t)*\frac{1}{\pi t} = \frac{1}{\pi}\int_{-\infin}^{\infin}\frac{s(\tau)}{t-\tau}d\tau
$$
信号$\hat{s(t)}$可以认为是信号$s(t)$经过一个系统后的响应，这个系统的冲激响应为
$$
h(t) = \frac{1}{\pi t}
$$
这个系统被称为希尔伯特变换，这是一个非因果系统,
希尔伯特变换的频域特性为
$$
H(w) = \begin{cases}
    -j, \space w>0 \\
    0, \space w=0 \\
    j , \space w<0 \\
\end{cases}
$$
从如下公式可以直接计算希尔伯特变换的频率特性
$$
H(w) = \int_{-\infin}^{\infin}h(t)e^{-jwt}dt = \int_{-\infin}^{\infin}\frac{1}{t} e^{-jwt}dt
$$
从频域特性来看，除直流外，希尔伯特变换的幅值恒定为1，而对正频率移相$-\frac{\pi}{2}$,对负频率移相$\frac{\pi}{2}$

从一个双边信号$s(t)$,通过如下的方式就可以得到一个单边带信号
$$
s_+(t) = s(t) + j\hat{s}(t)
$$
从而节省一半的带宽
我们发现，单边带信号是一个复数，如何产生一个复数信号呢?

## 9.12 单边带信号的发送和接收
单边带信号, $s_+(t) = s(t) + j\hat{s}(t)$
其中$\hat{s}(t)$是$s(t)$的希尔伯特变换

我们来回忆一下复数的概念，一个复数$x+jy$和一个实数对$(x,y)$相对应，也就是说，一个实数对就可以表达一个复数，只不过还需进一步满足四则运算的要求。

射频的单边带信号
$$
s_{RF+}(t) = [s(t) + j\hat{s}(t)]\cos{(w_ct)}
$$
但是它的虚部和实部多事双边带信号。只要载波信号是实数，我们就无法看出如何表示和发射这个信号。

我们采用复数的载波信号。只要载波信号的傅里叶变换具有冲激函数的性质，就可以保持基带信号的单边带特征。这个合适的复数载波信号就是复指数函数
$$
e^{jw_ct} = \cos{(w_ct)} + j\sin{(w_ct)}
$$
其傅里叶变换为
$$
F[e^{jw_ct}] = \delta{(w_c)}
$$
我们用复指数信号为载波，得到一个单边带的已调信号。为了符号的简便，我们还是采用符号$s_{RF+}(t)$来表示，
$$
\begin{aligned}
s_{RF+}(t) &= [s(t) + j\hat{s}(t)]e^{jw_ct} \\
&= [s(t) + j\hat{s}(t)][\cos{(w_ct)} + j\sin{(w_ct)}] \\
&= s(t)\cos{(w_ct)} - \hat{s}(t)\sin{(w_ct)} + j[\hat{s}(t)\cos{(w_ct)} + s(t) \sin{(w_ct)}]
\end{aligned}
$$
看它的实部的频谱
$$
F\{ \Reals [s_{RF+}(t)] \} = F[s(t)\cos{(w_ct)} - \hat{s}(t)\sin{(w_ct)}] \\
= S(w)*\frac{\delta(w_c) + \delta(-w_c)}{2} - S(w)H(w)*\frac{\delta(w_c) -\delta(-w_c)}{2j} \\
= \frac{1}{2}S(w)[1+jH(w)]*\delta(w_c) + \frac{1}{2}S(w)[1-jH(w)]*\delta(-w_c) \\
$$
设$S_{+}(w)=S(w)[1+jH(w)], s_{-}(w)[1-jH(w)]$, 分别是 $S(w)$的上边带和下边带，可以看出实部的频谱是单边带的。

$$
F\{ \Reals [s_{RF+}(t)] \} = \frac{S_{+}(w)}{2}*\delta(w_c) + \frac{S_{-}(w)}{2}*\delta(-w_c) \\
= \frac{S_{+}(w + w_c) + S_{-}(w-w_c)}{2}
$$

同样的道理，虚部的频谱也是单边带的
$$
F\{ \Im[s_{RF+}(t)] \} = \frac{S_+(w+w_c) - S_{-}(w-w_c)}{2j}
$$
虚部频谱的模与实部是相同的

这样的话，我们就找到了单边带信号的发射方案，只要发射实部或者虚部就可以了。习惯上，我们一般采用实部。

解调的方法还是乘以$\cos{(w_ct)}$

## 9.13 思考一下
提出问题的时候，问题差不多已经解决了。提出问题和解决问题是一个并行的过程，对所有的结论保持一个合理的怀疑。研究的过程就是探究竟，起怀疑，如果怀疑错了就继续研究。直到有一天，运气好，你的怀疑对了，也就创新了。怎样知道怀疑对了呢？因为你已经把问题解决了。

单边带信号$s(t)\cos{(w_ct)} - \hat{s}(t)\sin{(w_ct)}$,同时利用了载波的幅度和相位，而双边带信号只利用了载波的幅度。双边带信号只利用了余弦分量，而单边带信号同时利用了正弦和余弦两个正交分量。单边带信号利用了多一倍的信息，所以只需要一半的频谱资源。

但是如果我们独立地设置正弦和余弦分量，虽然带宽仍然和双边带信号相同，但是传递的信息也增加了一倍，频谱效率和单边带信号是相同的，而且省掉了希尔伯特变换这个环节。这个方法就是目前普遍采用了的IQ调制技术。

$x(t)\cos{(w_ct)} - y(t)\sin{(w_ct)}$

接收端乘以$\cos{(w_ct)}$，得到
$$
x(t)\cos^{2}(w_ct) - y(t)\sin{(w_ct)}\cos{(w_ct)}=x(t)\frac{1+\cos{(2w_ct)}}{2} - y(t)\frac{\sin{(2wct)}}{2}
$$
接收端乘以$-\sin{(w_ct)}$,得到
$$
-x(t)\sin{(w_ct)}\cos{(w_ct)} + y(t)\sin^2(w_ct)=-x(t)\frac{\sin{(2w_ct)}}{2 } + y(t)\frac{1-\cos{(2w_ct)}}{2}
$$
滤掉倍频成分后，分别得到了$x(t)$和$y(t)$

## 9.15 IQ信号的复数表达
已知关系
$$
[x(t)+jy(t)]e^{jw_ct} = x(t)\cos{(w_ct)} - y(t)\sin{(w_ct)} \\ 
+ j[y(t)\cos{(w_ct)} + x(t)\sin{(w_ct)}]
$$
IQ调制信号的发射，实际上就是这个复信号的实部。实部和虚部是一一对应的。我们可以把IQ信号看成是复数信号。

复数信号是等价的数学表达，实数信号是实际的发射和接收过程。

任意一个实信号$s_{RF}(t)$都可以写成以下形式
$$
s_{RF}(t) = \Reals{[s(t)e^{jw_ct}]}
$$
其中$s(t)=x(t) + jy(t)$,是一个复数信号。
假设这个关系成立，找出这个$s(t)$该是什么样的信号? 取实部的话，对于复数来说等于$1/2$复数+复数共轭
$$
s_{RF}(t) = \frac{1}{2}[s(t)e^{jw_ct} + s^{*}(t)e^{-jw_ct}]
$$
做傅里叶变换，得到
$$
S_{RF}(w) = \frac{1}{2}[S(w-w_c) + S^{*}(-w - w_c)]
$$
其中$S(w)=F[s(t)]$
因为$s_{RF}(t)$是实信号，所以其频谱有对称性
$$
S^{*}_{RF}(-w) = S_{RF}(w)
$$
注意到这样的对称性，$S(w)$就是这样一种形式:
$$
S(w-w_c)=\begin{cases}
    0, \space w<0 \\
    S_{RF}(w), \space w=0 \\
    2S_{RF}(w), \space w > 0 \\
\end{cases}
$$

$$
S(w) = \begin{cases}
    0, \space w<-w_c \\
    S_{RF}(w), \space w= -w_c \\
    2S_{RF}(w), \space w > -w_c \\
\end{cases}
$$

在无线通信中，我们把基带信号调制到一个载波上，就形成了一个带通信号。接收机收到的是带通信号和信道的冲激响应的卷积
$$
r_{RF}(t) = s_{RF}(t) * h_{RF}(t)
$$
在频域上
$$
R_{RF}(w) = S_{RF}(w)H_{RF}(w)
$$
表达为形式


# 第10章 概率论与随机过程
## 10.2 联合事件和联合概率
设$S_A$是随机试验$E_A$的样本空间，$A\sube S_A$,$S_B$是随机试验$E_B$的样本空间, $B \sube S_B$

称$(A,B)$是一个联合事件。

## 10.3 条件概率
对联合事件$(A,B)$，条件概率定义为
$$
P(A|B) = \frac{P(A,B)}{P(B)}
$$
条件概率可以反映出两个事件之间的关系
如果$P(A|B) > P(A)$,则A事件和B事件之间存在某种因果关系。A可能是B事件发生的原因之一，或者是B事件产生的结果。

如果$P(A|B) < P(A)$, B事件是阻止A事件发生的因素。

如果$P(A|B)= P(A)$,说明A事件和B事件之间没有关系，这种情况说明A和B独立。即$P(A,B)=P(A)P(B)$

贝叶斯准则，在信号检测中起了非常大的作用
$$
P(A|B) = \frac{P(A,B)}{P(B)} = \frac{P(B|A)P(A)}{P(B)}
$$


# 15 信息论
## 15.6 凸函数和Jensen不等式
一个定义在区间$(a,b)$上的函数$f(x)$,如果对于任意的$x_1,x_2 \in (a,b)$和$0 \leqslant \lambda \leqslant 1$满足
$$
f(\lambda x_1 + (1-\lambda)x_2) \leqslant \lambda f(x_1) + (1-\lambda)f(x_2)
$$
那么称函数$f(x)$在区间$(a,b)$上是凹(Convex)的。如果只有在$\lambda=0$或者$\lambda=1$时才能够取到等号，则称$f(x)$在区间$(a,b)$上是严格凹的(strictly convex)

凸函数(concave)。如果$f(x)$是凹函数，那么$-f(x)$就是凸函数。

**[定理]**
如果函数$f(x)$具有非负二阶导数，那么f(x)是凹的
证明:
把$f(x)$在$x_0$点展开为泰勒级数
$$
f(x)=f(x_0) + f^{'}(x_0)(x-x_0) + \frac{f^{''}(x^{*})}{2}(x-x_0)^2
$$
其中，$x^*$是$x_0$和$x$之间的一个点
根据条件, $f^{''}(x^*) \geqslant 0$， 让$x_0 = \lambda x_1 + (1-\lambda)x_2$,并且取$x=x_1$, 得到
$$
\begin{alignat}{2}
   f(x_1) = f(x_0) + f^{'}(x_0)(x_1 - x_0) +  \Delta \\
x_1 - x_0 = (1-\lambda)x_1-(1 - \lambda) x_2 = (1-\lambda)(x_1-x_2)\\
f(x_1) \geqslant f(x_0) + f^{'}(x_0)[(1-\lambda)(x_1 - x_2)]
\end{alignat}
$$
取$x=x_2$则
$$
\begin{align}
    f(x_2) = f(x_0) + f^{'}(x_0)(x_2 - x_0) +  \Delta \\
x_2 - x_0 = x_2 - \lambda x_1 - (1-\lambda)x_2 = \lambda(x_2 -x_1)\\
f(x_2) \geqslant f(x_0) + f^{'}(x_0)(\lambda(x_2 - x_1)) \\
\end{align}
$$
将$式(3)*\lambda + 式(6)*(1-\lambda)$, 得到
$$
\lambda f(x_1) + (1-\lambda)f(x_2) \geqslant f(x_0)+ f^{'}(x_0)(x_1-x_2)[\lambda(1-\lambda) - \lambda(1-\lambda)] \\
= f(x_0)\\
\lambda f(x_1) + (1-\lambda)f(x_2) \geqslant f(\lambda x_1 + (1-\lambda)x_2)
$$
其实这里就把上面需要证明的给证了

**Jensen不等式**
如果$f$是一个凹函数，$X$是一个随机变量，那么
$$
Ef(x) \geqslant f(EX)
$$
证明:
我们用归纳法来证明这个定理，首先从二元分布开始，假设随机变量$X$有两个取值$x_1$和$x_2$,概率分别为$p_1$和$p_2$,那么不等式为
$$
p_1f(x_1) + p_2f(x_2) \geqslant f(p_1x_1 + p_2x_2)
$$
由于$p_2 = 1 - p_1$,有凹函数的性质可以直接得到这个结论。
?应该怎样来理解呢?凹函数有哪些性质呢?

因为在上一个证明里, $\lambda + (1- \lambda) = 1$, 这里$p_1 + p_2 = 1$, 对照即可得证。 OK

假设在$X$有$k-1$个离散取值的情况下,不等式成立,那么在$X$有$k$个离散取值的情况下:
$$
\begin{aligned}
\sum_{i=1}^{k}p_if(x_i) &= \sum_{i=1}^{k-1}p_if(x_i) + p_kf(x_k) \\
&= (1-p_k)\sum_{i=1}^{k-1}\frac{p_i}{1-p_k}f(x_i) + p_kf(x_k) \\
&\geqslant (1-p_k)f(\sum_{i=1}^{k-1}\frac{p_i}{1-p_k}x_i) + p_kf(x_k) \\
&\geqslant  f(\sum_{i=1}^{k-1}p_ix_i + p_kx_k) \\
&= f(\sum_{i=1}^{k} p_ix_i)
\end{aligned}
$$
命题得证

借助Jensen不等式，可以证明互信息的非负性，也就是
$$
I(X;Y) \geqslant 0
$$
证明:
$$
\begin{aligned}
I(X;Y) &= \sum_{x,y}p(x,y)\log{\frac{p(x,y)}{p(x)p(y)}} \\ 
&= -\sum_{x,y}p(x,y)\log{\frac{p(x)p(y)}{p(x,y)}} \\
&\geqslant -log[\sum_{x,y}p(x)p(y)] \\
&=-\log{1} \\
&= 0 \\
\end{aligned}
$$
这里用到了前面的Jesnsen不等式, $-\log{t}$是一个凹函数。所以得证

因为$I(X;Y) = H(X) - H(X|Y) \geqslant 0$
所以$H(X|Y) \leqslant H(X)$

也就是说，观察到的信号$Y$总是使信源的不确定度减少，最差就是相等，而不会使信源的不确定性增大。那么观测信号$Y$使得我们对信源的不确定度降低的部分，就是互信息$I(X,Y)$

## 15.7 连续随机变量的微熵
假如离散随机变量$X$有两个取值，概率分布为$(\frac{1}{2},\frac{1}{2})$, 那么它的熵可以计算为
$$
H(X) = -\frac{1}{2}\log_2\frac{1}{2}-\frac{1}{2}\log_2\frac{1}{2} =1 \space bit
$$
也就是逼到每一个符号需要1 bit的信息，如果$X$有$4$个取值，概率分布为$(\frac{1}{4},\frac{1}{4},\frac{1}{4},\frac{1}{4})$,那么可以依定义计算它的熵为2 bits, 依次类推，如果有8个取值，则熵为3 bits
$$
-\frac{1}{4}\log_2{\frac{1}{4}}=\frac{1}{2} \\[0.5em]
4 \times \frac{1}{2 } = 2 \\
$$

如果一个连续随机变量$X$, 它的累积分布函数$F(x)=Pr(X \leqslant x)$是连续的，其概率密度函数为$p(x)$, 并且有$\int_{-\infin}^{x}p(t)dt = F(x)$。连续随机变量$X$有无穷多个取值，每个取值的概率趋向于零，那么它的熵根据计算是无穷大的，无法定义。

所以对于连续随机变量$X$, 无法定义它的熵，但是可以定义它的微熵
$$
h(X) = -\int_{-\infin}^{\infin}p(x)\log{p(x)}dx
$$
微熵在形式上与熵类似 ，但是微熵不是熵。

对于两个连续随机变量$X$和$Y$, 联合概率密度函数为$p(x,y)$, 条件概率密度函数为$p(x|y)$,也可以定义联合微熵和条件微熵
$$
h(X,Y)= -\int{p(x,y)\log p(x,y)}dxdy \\
h(X|Y) = - \int p(x,y) \log{p(x|y)}dxdy \\
$$
并且可以证明有这样的关系
$$
h(X,Y) = h(X) + h(Y|X)
$$

## 15.8 高斯分布的微熵
如果随机变量服从高斯分布，则概率密度函数为
$$
p(x) = \frac{1}{\sqrt{2\pi}\sigma}e^{-\frac{x^2}{2\sigma^2}}
$$
计算高斯分布的随机变量的微熵
$$
\begin{aligned}
h(X) &= -\int p(x) \log{p(x)}dx \\
&= - \int p(x) \log{\frac{1}{\sqrt{2\pi}\sigma}e^{-\frac{x^2}{2\sigma^2}}}dx \\
&= \int p(x) \log{\sqrt{2\pi}\sigma}dx - \int p(x) \log{e^{-\frac{x^2}{2\sigma^2}}}dx \\
&= \frac{1}{2} \log{2\pi \sigma^2} + \frac{1}{2}\log{e} \\
&= \frac{1}{2} 2\pi e \sigma^2 \\
\end{aligned}
$$
可以证明，在相同方差的情况下，高斯分布的微熵最大

高斯分布的重要性还体现在大数定律, 即多个独立同分布的和趋向于高斯分布。一个二元分布的不确定还是比较小的，但是两个二元分布加起来就会出现4个值，从而不确定增加了。如果继续加下去，即不确定性是持续增加的，而最终趋向于高斯分布，不确定性达到最大。这个可以作为高斯分布微熵最大的一个解释。

如果有$n$个随机变量$X_1, X_2,\dotsi,X_n$服从$n$维的高斯分布，则联合概率密度函数为
$$
p(x) = \frac{1}{(\sqrt{2\pi})^n \sqrt{\det M}}e^{-(x-m_{x})^{T} M^{-1}(x-m_x)/2}
$$
其中
$$
x=[x_1, x_2,\dotsi, x_n]^T \\
m_x = [E(X_1), E(X_2), \dotsi, E(X_n)]^T
$$
为均值向量，$M$为协方差矩阵
则可以计算联合微熵为
$$
h(X_1, X_2, \dotsi, X_n) = \frac{1}{2}\log{(2\pi e)^n} \det{M}
$$

## 15.9 连续随机变量的互信息
两个离散的随机变量可以定义互信息，那么连续随机变量支架可以定义互信息吗?

假设连续随机变量$X,Y$的联合分布为$p(x,y)$, 因为已经定义了离散变量的互信息，所以对连续变量互信息的定义也可以以此为起点。把连续随机变量$X,Y$量化为离散随机变量$X^{\Delta}, Y^{Delta}$,其互信息为
$$
I(X^{\Delta};Y^{\Delta})= H(X^{\Delta})-H(X^{\Delta}|Y^{\Delta})
$$
让量化区间长度$\Delta$趋向于零，则等式右边为
$$
\begin{aligned}
H(X^{\Delta})-H(X^{\Delta}|Y^{\Delta}) &\to h(X) - \log{\Delta} - h(X|Y) + \log{\Delta}  \\
&= h(X) - h(X|Y) 
\end{aligned}
$$
把它定义为连续随机变量的互信息，也就是
$$
I(X;Y) = h(X) - h(X|Y)
$$
把这个公式展开:
$$
\begin{aligned}
I(X;Y) &= h(X) - h(X|Y) \\
&= -\int p(x) \log{p(x)}dx + \int p(x,y) \log{p(x|y)}dxdy \\
&= -\int p(x,y) \log{p(x)}dxdy + \int p(x,y) \log{\frac{p(x,y)}{p(y)}}dxdy \\
&= \int p(x,y) \log{\frac{p(x,y)}{p(x)p(y)}}dxdy \\
\end{aligned}
$$
连续变量的互信息是从离散变量的互信息求极限而来的，因此两者在本质上是统一的。对于离散随机变量，其概念的发展顺序是熵、联合熵、条件熵、互信息；而对于连续随机变量，熵这个概念是不存在的，转而定义了微熵、联合微熵、条件微熵、互信息。我们发现，离散和连续邻域，共同的概念是互信息。因此互信息才是信息论最基础的概念，而不是熵或者微熵。

## 15.10 离散信道容量
什么是信道呢? 香农奖获得者Thomas M. Cover说

    What do we mean when we say that A communicates with B? We mean that the physical acts of A induced a desired physical state in B.

A点的动作引起B点的状态的改变。我们可以从B点的状态改变去判断A点发生的情况，从而实现通信。

可以用条件概率$p(y|x)$来描述离散无记忆(memoryless)信道。无记忆的意思是，信道的输出只与信道当前的输入有关，而与历史的输入信号没有关系。条件概率$p(y|x)$描述的是，当输入为不同的$x$的时候，输出为不同的$y$值的概率。条件概率可以完全地描述一条离散信道。

相同的输入可以引起不同的输出，相同的输出可能是由不同的输入引起的，这就引起了信息的混淆。为了减少甚至消除这些混淆，可以在发射端采用编码技术，而在接收端采用解码技术。一个典型的通信系统为：
$$
\xrightarrow{Message}  Encoder \xrightarrow{X^N} Channel p(y|x) \xrightarrow{Y^N} Decoder \xrightarrow{Message}
$$

编码就是把一定长度的信息编成长度为$N$的符号串，称其为码字，经过信道后，把码字输入到解码器，解出发送的信息。这样做的理论基础是大数定律，当$N$较大的时候，把一个码字混淆为另外一个码字的概率就会下降。
码字的长度$N$越大，误码率越低，信息速率也越低。那么什么事最大的信息速率？是在什么误码率条件下的最大信息速率呢?

x信道容量所指的最大速率，是指在误码率趋向于零的时候的最大信息速率。从直觉上看，即使$N$再大也是会有误码的，按照这个定义，信道容量应该是零啊。但是信息论告诉我们，信道容量是一个不为零的值，如果信息速率低于信道容量，是可以做到误码率趋向于零的。

先来看无记忆离散信道的信道容量定义为:
$$
C=\max_{p(x)}{I(X,Y)}
$$
最大值是在所有的输入信息的概率分布上取的

互信息的定义为:
$$
I(X,Y)=H(X)-H(X|Y)=H(Y)-H(Y|X)
$$
其中，$H(X)$是信源$X$的的不确定度, $H(X|Y)$是在获得接收信号$Y$后$X$的不确定度，互信息是获得接收信号$Y$后信源$X$的不确定度减少的部分，也就是接收方可以获得的信息量。显然，如果$X$的分布确定，信道$p(y|x)$确定，那么接收信号$Y$的分布也就确定了，$I(X,Y)$也就确定了。

然而，对于不同的$X$的分布，$I(X,Y)$是不同的。例如，如果$X$就是确定信号，也就是$H(X)=0$,那么$I(X,Y)$也必然为零。而信道容量则是$I(X,Y)$的最大值，这个时候对应一个特定的$X$的分布。

这个信道容量是理论上的信道容量，是由公式计算出来的，但是在实际操作当中能不能达到呢？香农第二定理指出，如果通信速率低于信道容量，一定存在一个编码方法使得误码率任意小。也就是说，信道容量是可以达到的。
举一个简单的例子，一个二元对称离散信道，其互信息为
$$
\begin{aligned}
I(X;Y) &= H(Y) - H(Y|X)   \\
    &= H(Y) - \sum_{x}p(x) H(Y|X=x) \\
    &= H(Y) - \sum_{x}p(x)H(p) \\
    &= H(Y) - H(p) \\
    &\leqslant 1 - H(p) \\
\end{aligned}
$$
其中
$$
H(p) = -p\log_{2}p - (1-p)\log_2(1-p)
$$
可以看到，$1-H(p)$是互信息的一个高限。当$X$时均匀分布的时候，$Y$也是均匀分布的,这个时候$I(X;Y)$取到最大值$1-H(p)$,也就是说信道容量为$1-H(p)$

如果$p=0.5$,也就是信道的误码率为$50\%$,此时的信道容量为零。


## 15.11 加性高斯白噪声信道容量
加性高斯白噪声信道是最简单的符号集连续取值的信道，可以表达为
$$
Y= X + Z
$$
其中$X,Y,Z$都是连续取值的随机变量，$Z$是高斯噪声，方差为$N$,$X$的方差为$P$

连续信道的信道容量定义和离散信道是相同的，也就是
$$
\begin{aligned}
   C&= \max_{p(x)} I(X;Y) \\
I(X;Y) &= H(Y) - H(Y|X) \\ 
&= H(Y) - H(X + Z |X)  \\
&= H(Y) - H(Z|X)  \\
&= H(Y) - \frac{1}{2}\log_22\pi e N \\
&\leqslant \frac{1}{2}\log_22\pi e (P+N) -\frac{1}{2}\log_22\pi e N \\
&= \frac{1}{2}\log_2(1+\frac{P}{N})
\end{aligned}
$$
也就是
$$
C=\frac{1}{2}\log_2(1+P/N)
$$

在上面的推导中，有几个环节要注意。一是$H(X+Z|X)=H(Z|X)$,因为以$X$为条件，$X$是一个确定信号。第二个是$Y$的方差为$P+N$, 当$Y$时高斯白噪声的时候微熵最大，也就是$\frac{1}{2}\log_22\pi e (P+N)$。这个时候，$X$应该是方差为$P$的高斯白噪声信号。

这里信道容量的单位还是$bits/symbol$
如果信号的带宽为$B$，那么根据采样定理用$2B$的采样率采样可以无失真地表达原有信号。即每一个采样点都是一个独立的随机变量，每秒$2B$个采样点，因此每秒钟的总的信道容量为
$$
C=B\log_2(1+\frac{P}{N})
$$
这就是香农公式。直到1993年Turbo码的发明，才使得我们接近该极限。
这个结论称为香农信道容量第一定理。

## 15.12 注水定理
一个AWGN信道, $Y=X+Z$
其中，$X$是输入信号，$Z$是白噪声，$Y$是输出信号，都是复随机变量。它的信道容量为香农公式。

如果信号的功率为$P=P_1 + P_2$,则可以验证一个公式:
$$
\begin{aligned}
C &=\log{(1+ \frac{P_1 + P_2}{N})} \\
&= \log(1+\frac{P_1}{N}) + \log{(1 + \frac{P_2}{P_1 + N})} \\
&= C_1 + C_2
\end{aligned}
$$
$C_1$为信号功率为$P_1$,噪声为$N$时的容量；$C_2$为信号功率为$P_2$,噪声为$P_1 + N$时的容量
也就是说，第一份功率产生了一个容量，同时等效成为对第二份功率的噪声。

如果有$N$个并行的AWGN信道
$$
Y_i = X_i + Z_i, \space i=1,2,\dotsi, N-1
$$

则这$N$个信道上已经有一些噪声或者信号的功率，如果再有一小份功率，那么把它分配到哪个信道上能获得最大的信号容量呢?
这样分配的结果就是$N$个信道上的功率是相同的，这就是注水定理。

# 第16章 蜂窝通信
频率复用, 全向小区，天线位于六边形小区的中心; $120^{\degree}$定向天线，也叫三扇区天线，位于六边形小区的顶点上。复用簇。一个复用簇内小区的个数叫做复用因子K。

## 16.2 切换
每个小区的beacon, 在LTE中，公共参考信号CRS扮演了灯塔信号的角色,因此终端知道蜂窝系统灯塔信号的消息，包括采用了什么样的随机序列组。

终端会周期性地搜索和测量一组灯塔信号的信号强度，如果终端处于小区边界的地方，它会测量到多个比较强的灯塔信号。一般会选择接收强度最强的那个小区，这样就选择了离自己最近的小区，称作驻留在该小区。终端驻留时，会收听这个小区的广播信道，得到这个小区的配置信息，比如终端可以在哪条上行信道上向激战发送呼叫请求。

终端的测量是周期性的，始终驻留在离自己最近的小区，这个叫做小区选择和重选。

跨越边界时，有正在进行的业务，这个叫做切换。




