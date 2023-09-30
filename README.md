# study-5g-prj
I would like to study the book from Dr. Yang Xuezhi. 


## chap 1
### 极限,柯西, 函数的极限, 

空心邻域，

$$
\begin{align}
\lim\limits_{x \to x_0} f(x) = A \\ 
x_0的\delta 邻域,开区间(x_0-\delta, x_0+\delta),N(x_0,\delta) \\
\end{align}
$$

极限定义的思想，以及它所体现的数学的严密逻辑。

弄懂公式的意义，经过多次的思考训练，建立起条件反射。

## chap 2
### 2.4 连续
$$
\lim\limits_{x->x_0} f(x)=f(x_0)
$$

左连续、右连续

### 2.5 导数
斜率, 变量的变化除以自变量的变化，就是直线的斜率,

导数，微积分的基础概念。

$$
f^{'}(x_0) = \lim\limits_{\Delta x \to 0} \frac {f(x_0 + \Delta x) - f(x_0)} {\Delta x} \\
$$

### 2.6 微分
微分等于导数乘以自变量的微分

$$
dy = f^{'}(x)dx \\
f^{'}(x) = \frac {dy} {dx} \\
$$

导数也叫做微商, 


### 2.7 积分
黎曼，德国数学家。黎曼函数，黎曼积分，黎曼引理。黎曼流形，黎曼映射订立，黎曼-希尔伯特问题，黎曼思路回环矩阵和黎曼曲面。

$$
极限存在 \\
\lim\limits_{\lambda \to 0}\sum_{i=1}^n f(\xi_i)\Delta x_i \\
黎曼可积 \\
\int_{a}^{b} f(x)dx = \lim\limits_{\lambda \to 0}\sum_{i=1}^n f(\xi_i)\Delta x_i \\
$$

使子区间$[x_{i-1}, x_i]$中的子区间的宽度逼近于零, 这时候子区间内的所有点实际上收缩为一个点。

$$
\int_{a}^{b} f(x)dx = A
$$

黎曼可积比连续的条件要弱。

微积分第一基本定理

假定$f(x)$在闭区间$[a,b]$上连续
$$
F(x)= \int_a^b f(t)dt
$$
如果$F(x)$可导,且$F^{'}(x)=f(x)$

微积分第二基本定理

微分中值定理, 

$$
\int_a^b f(x)dx = F(b)-F(a)
$$

### 2.13 泰勒级数

泰勒中值定理，如果有函数$f(x)$在包含$x_0$的某个开区间$(a,b)$内有$n+1$阶导数，则对任意 $x \in (a,b)$,有

$$
f(x)=f(x_0) + f^{'}(x_0)(x - x_0) + \frac {f^{''}(x_0)} {2!} (x-x_0)^2 + \dotsb + \\
\frac {f^{n}(x_0)} {n!}(x-x_0)^n + R_n(x)
$$

其中
$$
R_n(x)=\frac {f^{(n+1)}(\xi)} {(n+1)!}(x-x_0)^{n+1}
$$

如果选$x_0=0$,则泰勒级数又称作麦克劳林级数,

用多项式来近似表示函数在某点周围的情况，如果用$n$阶多项式来近似一个函数，其误差为$R_n$,成为 $n$阶误差余项

如果$f(x)$是无穷可微的，泰勒级数就是 一个无穷级数，并且在全实数轴上收敛

$$
e^x = 1 + x + \frac 1 {2!} x^2 + \frac 1 {3!} x^3 + \dotsi \\ 
\\[0.5em]
cos(x) = 1 - \frac {x^2} {2!} + \frac {x^4} {4!} - \frac {x^6} {6!} + \dotsi \\[0.5em]
sin(x) = x - \frac {x^3} {3!} + \frac {x^5} {5!} - \frac {x^7} {7!} + \dotsi
$$

### 2.14 多员函数和偏导数
距离
$$
|P-P_0| = \sqrt{(x-x_0)^2 + (y-y_0)^2}
$$

二元函数的连续的概念

$$
\lim\limits_{P \to P_0} f(P) = f(P_0)
$$
则称$z=f(P)$在点$P_0$处连续

偏导数
$$
\frac {\partial f} {\partial x}(x,y) |_{x=x_0} = \lim\limits_{x \to x_0} \frac {f(x,y) - f(x_0, y)} {x-x_0}
$$

混合偏导去求导的顺序无关, 二元函数的偏导和积分可以直接推导到N维

1643年，牛顿出生。此时明朝正处于风雨飘摇之中

1687年, 牛顿<<数学原理>>发表

1769年，詹姆斯。瓦特改良蒸汽机, 

## chap 3 信号与系统

卷积运算 

$$
\begin{aligned}
y(t) &= x(t)*h(t) \\
h(t) &= 0, t<0 \\
y(t) &= \int_{-\infin}^tx(\tau)h(t-\tau)d\tau
\end{aligned}
$$

有了输入信号和冲击响应，线性、时不变系统的输出就完全被决定了。对于非线性系统，就不能使用卷积了。

### 3.6 卷积的性质
交换律

$$
x_1(t)*x_2(t)=x_2(t)*x_1(t) \\
x_1[n]*x_2[n]=x_2[n]*x_1[n] \\
$$

分配律

结合律

## chap 4 复变函数
complex variable functions

每一个复数$z=x+iy$都对应二维平面上的一个点$(x,y)$,我们把这个平面叫做复平面，也叫高斯平面。复数对应复平面上的点，也可以用模和幅角来唯一表示

$$
r=|z|=\sqrt{x^2+y^2},tan\theta=\frac y x
$$

一个复数相当于两个实数，如果仅仅为了表达两个实数，把它们写成一个矢量$(x,y)$就可以了。没有必要引入复数的概念。

复数的四则运算
$$
z_1 \cdot z_2 = x_1 x_2 - y_1 y_2 + i(x_1 y_2 + x_2 y_1) \\[0.5em]
i^2 = -1
$$
共轭复数
$$
\overline{z} = x - iy \\
z \overline{z} = x^2 + y^2 \\
$$
如果$z_2 \not = 0$
$$
\frac {z_1} {z_2} = \frac {z_1 \overline{z_2}} {z_2 \overline{z_2}} = \frac {x_1 x_2 + y_1 y_2} {{x_2}^2 + {y_2}^2} + i \frac {-x_1 y_2 + x_2 y_1} {{x_2}^2 + {y_2}^2}
$$

定义是一个知识体系的开始，是基础。有了虚数$i$的定义，才有了复变函数这门学科，现代的力学、电磁学、信号处理都建立在复变函数的基础之上。

分数，有理数，任意一个数都可以用一个有理数去无限逼近, 用数学语言去说，就是有理数在实数轴上是稠密的?

有理数集合是不完备的。

完备: 柯西序列，柯西收敛,$S$是完备的。假设$x_1,x_2,x_3,\dotsi$ 是集合$S$中的序列，如果对于任意的$\epsilon > 0$,都存在正整数$N$,使得当$m>N$, $n>N$时，有$|x_m - x_n|< \epsilon$成立，则称该序列是柯西序列。

然而对于无理数，这个序列是不收敛的，之间的距离是一直在减小的。但是序列收敛到一个无理数，因此在有理数的集合里面，序列是不收敛的，所以有理数集合不完备。

实数论的东西、概念。

概念的发展逻辑, 一是保持概念的连贯性，二是解决原有概念所无法解决的问题,

原来建立起来的理论体系要维持，不能够推倒重来，扩展部分不遵循又有概念的规律，也是非常自然的。

### 复指数函数
以$z=x+iy$为自变量的函数称为复变函数。最重要的复变函数就是复指数函数,
$$
f(z)=e^z=e^{x+iy}
$$

那么自然对数是怎么来的呢?
$$
e=(1 + \frac 1 {x})^x \\[0.5em]
e= \frac 1 {0!} +  \frac 1 {1!} + \frac 1 {2!} + \frac 1 {3!} + \frac 1 {4!} + \dotsb 
$$

当$x \to \infin$时，这个极限值存在，就是$e$
实指数函数的定义:
$$
e^x = \lim\limits_{n \to \infin}(1 + \frac x n)^n
$$
二项式展开
$$
\lim\limits_{n \to \infin}\sum_{i=0}^n {\begin{pmatrix} n \\ i \end{pmatrix}}{\bigg( \frac  x   n \bigg)}^i = 
\lim\limits_{n \to \infin} \sum_{i=0}^n \frac {n!} {n^i(n-i)!i!}x^i
\\[1em]
e^x = \lim\limits_{n \to \infin}\sum_{i=0}^n\frac 1 {i!} x^i \\
e^x = 1 + x + \frac 1 {2!} x^2 + \frac 1 {3!}x^3 + \dotsi
$$
这就是指数函数的麦克劳林级数

指数函数的导数是其自身，

复指数函数
$$
e^z = \lim\limits_{n \to \infin}(1 + \frac z n)^n= 
\lim\limits_{n \to \infin}\sum_{i=0}^n{\frac 1 {i!}}z^i
$$

### 4.5 欧拉公式
$$
e^{ix} = \cos x + i \sin x
$$
欧拉公式将三角函数的定义域扩展到了复数，建立了三角函数和指数函数之间的关系

$$
e^{i \pi } + 1 = 0 \\
z = re^{i \theta} \\
e^{iwt} = \cos wt + i \sin wt
$$

复指数信号，实部为余弦信号，虚部为正弦信号

## chap 5 傅里叶分析
LTE, OFDM, 就是傅里叶变换的结果

### 5.1 傅里叶级数
#### 5.1.1 三角形式的傅里叶级数
假定一个周期信号$x(t)$,周期为$T_1$,其角频率为$w_1= \frac {2\pi} {T_1}$,如果$x(t)$满足狄里赫利条件，则可以表达成傅里叶级数

$$
x(t)= a_0 + \sum_{n=1}^{\infin} \lbrace a_n \cos{(n w_1 t)} + b_n \sin {(n w_1 t)} \rbrace
$$

狄里赫利条件，指周期信号满足:
* 任意一个周期内，有限个间断点
* 任意一个周期，有限的极大值和极小值
* 任意一个周期，其绝对值可积

$a_n,b_n$的表达式
$$
\begin{cases}
a_0 = \frac 1 {T_1} \int_{- \frac {T_1} 2}^{\frac {T_1} 2}x(t) dt \\[0.5em]
a_n = \frac 2 {T_1} \int_{- \frac {T_1} 2}^{\frac {T_1} 2}x(t) \cos {(n w_1 t)} dt \\[0.5em]
b_n = \frac 2 {T_1} \int_{- \frac {T_1} 2}^{\frac {T_1} 2}x(t) \sin {(n w_1 t)} dt \\[0.5em]
\end{cases}
$$

三角函数的正交性，正交性是内积空间当中的一个概念，这个概念会在泛函分析里面讲到。傅里叶级数里面的每个频率成分都是一个维度，这里是一个无穷维的内积空间。从线性空间的角度去观察傅里叶变换。

正弦函数和余弦函数是交的，不同频率的正弦函数是正交的，不同频率的余弦函数也是正交的。

$$
x(t) = 0.5 + sinc(0.5) \cos(\pi t) + sinc(3x0.5) \cos(3 \pi t) + \dotsi \\[0.5em]
sinc(x) = \frac {\sin (\pi x)} {\pi x} 
$$

##### 为什么正弦信号如此重要呢?
这是因为三角函数作为线性系统的输入时具有频率不变的特性，这个特性为系统特性的描述、一些问题的解决带来了很大的方便。

举例：
假设输入信号为 $x(t)= \cos {(wt)}$
输出信号为 $y(t) = x(t) + a \cdot x(t-t_0)$

$$
\begin{aligned}
\begin{split}
y(t) &= \cos {(wt)} + a \cdot \cos {(wt - wt_0)} \\
&= (1 + a \cos {wt_0}) \cos {wt} + a \sin {wt_0} \sin {wt} \\
&= A \cos {(wt - \theta)} \\
\end{split}
\end{aligned}
$$
输出信号是由输入信号和一个延时的输入信号叠加得到的。经整形后，化为一个幅度、相位改变了的三角函数信号。

其它的周期性信号，比如方波、三角波，就不具备这种波形保持的特性。这种由系统引起的正弦信号幅度和相位的改变，反映了线性系统的特征，所以称为系统的幅频特性和相频特性，统称频率特性。频率响应。这种描述系统的方法是非常简洁的，因此获得了广泛的应用。

更一般的，我们假设一个线性系统的冲击响应为$h(t)$,输入信号为复指数形式的正弦信号，$x(t)=e^{jwt}$, 则输出信号为:

$$
\begin{aligned}
y(t) &= \int_{- \infin}^{\infin} h(\tau)e^{jw(t - \tau)}d\tau \\[0.5em]
&= e^{jwt} \int_{- \infin}^{\infin}h(\tau)e^{-jw\tau}d\tau \\[0.5em]
&= e^{jwt}H(jw)
\end{aligned}
$$

用复数表达的系统的频率特性。

#### 复指数形式的傅里叶级数
虚数单位，在工程领域用$j$来表示。根据欧拉公式
$$
cos(nw_1t) = \frac {e^{jnw_1t} + e^{-jnw_1t}} 2 \\
sin(nw_1t) = \frac {e^{jnw_1t} - e^{-jnw_1t}} {2j} \\
$$

代入三角形式的傅里叶级数公式，可以得到
$$
x(t) = a_0 + \sum_{n=1}^{\infin}[\frac {a_n - jb_n} {2} e^{jnw_1t} + \frac {a_n + jb_n} {2} e^{-jnw_1t}]
$$

我们令
$$
\begin{cases}
c_0 = a_0 \\[0.5em]
c_n = \frac {a_n -jb_n} 2 \space 当 n \ge 1 \\[0.5em]
c_{-n} = \frac {a_n + jb_n} {2} \space 当 n \ge 1
\end{cases}
$$
则
$$
x(t)=\sum_{n=- \infin}^{\infin}c_n e^{jnw_1t}
$$

$c_n$也被称作离散频谱,这就是复指数形式的傅里叶级数，其形式更加简洁和优美!
$$
c_n = \frac 1 {T_1} \int_{- \frac {T_1} 2}^{\frac {T_1 } 2} x(t)e^{-jnw_1t}dt
$$

负频率的意义，只是数学上的标识方法，并没有实际的物理意义。正频率和负频率存在对偶关系。是一对共轭复数，所以正频率、负频率所承载的信息是一样的。

调制
$$
cos(w_ct)cos(w_1t)= \frac {cos(w_c - w_1)t + cos(w_c + w_1)t} 2
$$

### 傅里叶变换
周期信号可以用傅里叶级数来表达，傅里叶系数又被称作离散频谱，因为谱线只出现在$w_1=1/T_1$的整数倍上。把这个概念推广到非周期信号上，就可以得到傅里叶变换。

从周期信号的复指数形式的傅里叶级数开始。

一个周期为$T_1$,角频率为$w_1 = 2\pi/T_1$的周期信号，其复指数傅里叶级数为
$$
x(t)=\sum_{n=-\infin}^{\infin}X(nw_1)e^{jnw_1t} \\
X(nw_1) = \frac 1 {T_1} \int_{- \frac {T_1} 2}^{\frac {T_1} 2} x(t) e^{-jnw_1t}dt
$$

非周期性信号可以认为是周期无限大的周期信号，让周期 $T_1 \to \infin$, 则谱线的间距$2 \pi/T_1 \to 0$,离散频谱变成了连续频谱

然而在这种情况下，$X(nw_1)$ 也有可能趋于零，这时就失去了意义。这种情况下在两边都乘以$T_1$
$$
X(nw_1)T_1 = \frac {2\pi X(nw_1)} {w_1} = \int_{- \frac {T_1} 2}^{\frac {T_1} 2}x(t)e^{-jnw_1t}dt
$$

再让$T_1$趋于无穷，于是$w_1$趋向于零，得到
$$
\lim_{w_1 \to 0} \frac {2 \pi X(nw_1)} {w_1} = \int_{- \infin}^{\infin} x(t)e^{-jnw_1t}dt
$$
采用$w=nw_1$,在$w_1$趋向于零的时候，$w$变成了一个连续变量，代入上式后得到

$$
X(w) = \int_{- \infin}^{\infin}x(t)e^{-jwt}dt
$$

这个公式就是傅里叶变换，通常记作
$$
X(w) = \digamma[x(t)] = \int_{- \infin}^{\infin} x(t)e^{-jwt}dt
$$

再来看傅里叶级数在$w_1$趋向于零的时候的情况，把傅里叶级数稍微改变一下形式
$$
x(t)=\sum_{n=-\infin}^{\infin}X(nw_1)e^{jnw_1t} = \frac 1 {2 \pi} \sum_{n= - \infin}^{\infin} \frac {2 \pi X(nw_1)} {w_1} e^{jnw_1t}w_1
$$

$w_1$是两条谱线之间的间隔，用积分的常用符号来记就是$\varDelta(nw_1)$,当$w_1$趋向于零的时候
$$
x(t) = \lim_{w_1 \to 0} \frac 1 {2\pi} \sum_{n= -\infin}^{\infin} \frac {2 \pi X(n w_1)} {w_1} e^{jnw_1t} \varDelta(nw_1)
$$
也就是逆傅里叶变换，或者傅里叶反变换
$$
x(t) = \digamma^{-1}[X(w)] = \frac 1 {2 \pi} \int_{- \infin}^{\infin} X(w) e^{jwt}dw
$$

如果你已经有了内积的指示，就可以知道，正变换就是信号与基函数做内积，而复数做内积需要取共轭，所以就有了一个负号。而反变换就是用基函数去合成原来的信号，所以就没有负号。

#### 谱密度函数
傅里叶系数$X(nw_1)$ 是无量纲的，而傅里叶变换
$$
X(w) = \lim_{T_1 \to \infin} X(nw_1)T_1 = \lim_{w_1 \to 0} \frac {2 \pi X(n w_1)} {w_1}
$$
带有时间的量纲，是一个频谱密度的概念

周期性信号的傅里叶系数是离散的，其频谱间隔为$w_1$。如果把离散谱看成是连续变量$w$的函数，这个函数在$w=nw_1$上的取值为傅里叶系数，而其它地方的取值为零。那么可以认为，在$w_1$的宽度上的谱值为$X(nw_1$，如果这个值均匀分布在$w_1$的宽度上，那么$X(nw_1)/w_1$就是平均谱密度。当$w_1$趋向于零的时候，$X(w)$就变成了谱密度函数。


#### 傅里叶变换存在的条件
要求满足绝对可积的条件才能存在
$$
\int_{- \infin}^{\infin}|x(t) |dt < \infin 
$$

这个条件要求信号在时间趋向正负无穷的时候，幅度要衰减到0.

周期型号的幅度保持恒定，因此不满足绝对可积信号。

从谱密度的角度去看，周期函数的谱线在宽度为零的离散谱线上，因此谱密度再这些点上是无穷大的。

但是如果引入冲击函数，则周期函数的傅里叶变换也可以用冲击函数来表达，傅里叶变换存在。

### 傅里叶变换的性质
(1)对称性
$$
\digamma[x(t)] = X(w) \\
则 \\
\digamma[X(t)] = 2 \pi x(-w)
$$

(2)线性
如果$a_i, i=1,\dotsi N$ 为标量，N为正整数，则
$$
\digamma[\sum_{i=1}^N a_i x_i(t)] = \sum_{i=1}^{N}a_i \digamma[x_i(t)]
$$

所谓线性，即总体为个体之和

(3)奇偶虚实性
如果
$$
X(w) = \digamma[x(t)] = \int_{- \infin}^{\infin} x(t) e^{-jwt}dt
$$
则
$$
\begin{cases}
\digamma[x(-t)] = X(-w) \\
\digamma[x^{*}(-t)] = X^{*}(w) \\
\digamma[x^{*}(t)] = X^{*}(-w) \\
\end{cases}
$$

对一个偶函数, $x(-t)=x(t)$,那么有$X(w) = X(-w)$, 偶函数的傅里叶变换也是偶函数

对于一个奇函数, $x(-t)=-x(t)$,那么有$X(w)=-X(-w)$,奇偶数的傅里叶变换也是奇函数

如果$x(t)$是实函数
$$
X(w) = \int_{- \infin}^{\infin} x(t) e^{-jwt}dt = \int_{- \infin}^{\infin} x(t) \cos {(wt)} dt -j\int_{- \infin}^{\infin}x(t) \sin {(wt)} dt
$$

用$\real (\cdot)$和$\Im (\cdot)$代表被操作数的实部和虚部，则
$$
\begin{cases}
\real [X(w)] = \int_{- \infin}^{\infin} x(t) \cos{wt} dt \\[0.5em]
\Im [X(w)] = \int_{- \infin}^{\infin} x(t) \sin{wt} dt
\end{cases}
$$
很容易验证
$$
\begin{cases}
\real [X(w)] = \real [X(-w)] \\[0.5em]
\Im [X(w)] = - \Im [X(-w)]
\end{cases}
$$

实函数的傅里叶变换的实部是偶函数，虚部是奇函数

用幅度和相位来表示，则有
$$
\begin{cases}
|X(w)| = \sqrt{\real [X(w)]^2 + \Im [X(w)]^2 } \\
\varPhi(w) = \arcctg {\frac {\Im [X(w)]} {\real [X(w)]}}
\end{cases}
$$
实函数的傅里叶变换的幅度是偶函数，相位是奇函数

如果$x(t)$同时是实函数和偶函数，则其傅里叶变换的实部和虚部都是偶函数。实偶函数的傅里叶变换的虚部既是偶函数，也是奇函数，因此虚部一定为零。所以，实偶函数的傅里叶变换是实偶函数。

(4) 尺度变换
$$
\digamma [x(at)] = \frac 1 {|a|} X(\frac w a)
$$
尺度变换因子$a$对时域和频域的作用是相反的。

(5) 时移特性
$$
\digamma [x(t-t_0)] = e^{-jwt_0}X(w)
$$
时域的时移对应于频域的相移。这是确实的。

$$
\digamma [x(t) e^{jw_0t}] = X(w - w_0)
$$
时域的相移对应于频域的频移。
在无线通信里, 调制技术, 将基带信号乘以一个高频的载波信号$e^jw_c t$,相当于把频谱搬移了$w_c$,变成适合发射的信号。

### 典型函数的傅里叶变换
(1) 矩形函数
$$
x(t) = \begin{cases}
    A \space -\tau/2 \le t \le - \tau/2 \\
    0 \space 其它
\end{cases} \\
X(w) = A \tau sinc(w \tau / 2 \pi)
$$
其中的$sinc$函数定义为
$$
sinc(x) = \frac {\sin \pi x} {\pi x}
$$
这是信号处理领域采用的$sinc$函数的定义，在$x$取整数的时候函数值为0

数学领域, $sinc$定义为
$$
sinc(x) = \frac {\sin x} x
$$
在零点处，$sinc(x)$为1

(2) 冲激函数
$ X(w) = \digamma[\delta (t)]  = 1 $
$X(w)$为常数1，意味着所有的频率上的频谱密度为1.因此成为白频谱。如果频谱的幅度随着频率有起伏，特别是频谱主要集中在一个或数个频段内，则称为“有色频谱”。
$\digamma^{-1}[1] = \delta (t)$

(3) 周期函数
看一看实信号$x(t)= \cos w_1t$ 的傅里叶变换
$$
\cos w_1 t = \frac {e^{jw_1 t} + e^{-jw_1 t}} {2}
$$
所以
$$
\digamma{[\cos w_1 t]} = \pi \delta (w - w_1) + \pi \delta (w + w_1)
$$
余弦信号的傅里叶变换是位于$w_1$和$-w_1)$处的两个冲激信号。余弦信号是实偶函数，傅里叶变换也是实偶函数。
类似地，也可以得到正弦信号的傅里叶变换
$$
\digamma{[\sin w_1 t]} = j\pi \delta (w + w_1) - j\pi \delta(w - w_1)
$$
正弦信号是实奇函数，傅里叶变换为虚奇函数

对于一个一般性的周期函数$x(t)$,周期为$T_1$,角频率为$w_1 = 2\pi/T_1$,表达成为复指数的傅里叶级数形式为
$$
x(t) = \sum_{n= - \infin}^{\infin} c_n e^{jnw_1 t}
$$
其中$c_n$为傅里叶系数
$$
c_n = \frac 1 {T_1} \int_{- \frac {T_1} 2}^{\frac {T_1} 2} x(t) e^{-jnw_1 t}dt
$$
那么$x(t)$的傅里叶变换为
$$
\digamma[x(t)] = 2\pi \sum_{n= - \infin}^{\infin}c_n \delta{(w - nw_1)}
$$
周期信号的傅里叶变换是一系列离散的冲激信号，每个冲激的轻度就是傅里叶系数乘以$2\pi$。傅里叶变换是谱密度函数。

### 卷积定理
卷积定理在信号分析中占用重要的地位。如果有2个时域信号，已知
$$
\digamma[x_1(t)] = X_1(w)  \\
\digamma[x_2(t)] = X_2(w)  \\
$$
则
$$
\digamma[x_1(t)*x_2(t)] = X_1(w)\cdot X_2(w)
$$
这个定理叫做时域卷积定理。在时域的卷积，在频域是乘积。在信号分析领域有一个分支叫做时频域分析，是应用最广泛的信号处理方法，它就是基于这个定理以及其对偶的频域卷积定理。

频域卷积定理，时域两个信号的乘积，在频域变成了卷积运算。

时域和频域的卷积定理，反映了时域和频域的对偶关系。

### 线性系统的频率特性
一个线性时不变系统可以用冲激响应完全刻划其特性。
$$
y(t) = x(t)*h(t) \\
Y(w) = X(w)\cdot H(w)
$$
$H(w)= \digamma[h(t)]$ 叫做系统的频率特性。幅度叫做幅频特性，相位叫做相频特性。

非线性系统或者线性时变系统都不能用这个方法来描述，因为这样的系统对正弦信号不具备波形保持特性。

线性时变系统在实际当中往往被处理成短时间内的线性时不变系统。在这种情况下，也可以用频率特性来描述，但是同时隐含了对信号进行周期化的处理过程。

### 离散傅里叶变换
实际应用的是离散傅里叶变换。不像连续信号有傅里叶级数和傅里叶变换之分。在离散域，傅里叶变换也就是傅里叶级数。

如果有一个周期为$N$的离散信号$\tilde{x}[n]$, $n \in (-\infin,  \infin)$, $\tilde{x}[n + N] = \tilde{x}[n]$,则按照连续信号傅里叶级数的思路，它也可以表达为角频率为$w_1 = 2\pi/N$的整数倍的三角函数的和。

我们省略了三角函数的表达方式，而直接采用了离散复指数函数的表达方式
$$
e_k[n]=e^{j\frac {2\pi} {N} kn} = \cos {\frac {2\pi} {N} k n} + j \sin {\frac {2\pi} N k n} , k= 0,1,\dotsi, N-1
$$
离散复指数信号可以认为是角频率为$\frac {2\pi} N kn$的连续复指数信号在整数点上的采样，也可以认为是角频率为$kw_1$的连续复指数信号在$t=\frac {2\pi} {Nw_1} n$上的采样
$$
e_k[n] = e^{j\frac {2\pi} {N} kt}|_{t=n} = e^{jw_1kt}|_{t=\frac {2\pi} {Nw_1} n}
$$
离散信号的频率与连续信号的频率的对应关系由采样频率决定。
$e_1[n]=e^{j\frac {2\pi} {N} n}$是以$N$为周期的周期信号，$e_1[n+N] = e_1[n]$, $N$也是$e_k[n]=e^{j\frac {2\pi} {N} kn}$的周期
$e_1[n]$的实部和虚部分别是离散余弦信号和离散正弦信号。
复指数函数的频率是离散的，并且有如下关系成立
$$
e_{k+N}[n] = e_k[n]
$$
$e_k[n]$的频率可以认为是$\frac {2\pi} {N} k$,也可以认为是$\frac{2\pi}{N}(k + lN), l \in \Z$。在$[0,2\pi)$内，复指数信号有$N$个不同的频率，不同频率的信号具有两两正交性，也就是
$$
\sum_{n=0}^{N-1}e_k[n]\overline{e_l[n]}=\sum_{n=0}^{N-1}e^{\frac {2\pi} {N}(k-l)n}=\begin{cases}
N \space k=l \\
0 \space k \not = l
\end{cases}
$$
因为$\tilde{x}[n]$是周期函数，只取其中的一个周期就可以完全表达，标记为$x[n]$
$$
x[n] = \tilde{x}[n], n=0,1,2,\dotsi,N-1
$$
周期为$N$的无限长度的周期信号，和长度为$N$的有限长度信号是一一对应的，或者说是等价的。周期离散信号的一个周期可以表达为
$$
x[n] = \sum_{k=0}^{N-1}c_ke_k[n] = \sum_{k=0}^{N-1}c_k e^{j\frac {2\pi} {N} kn}, n=0,1,\dotsi,N-1
$$
利用复指数函数的正交性，两边都乘以$\overline{e_k[n]}$并求和，可以计算系数$c_k$为
$$
c_k = \frac{1}{N}\sum_{n=0}^{N-1}x[n]e^{-j\frac{2\pi}{N}kn}
$$
从这里，定义离散傅里叶变换为
$$
X[k] = \sum_{n=0}^{N-1}x[n]e^{-j\frac{2\pi}{N}kn}, k=0,1,2,\dotsi,N-1
$$
$X[k]$也就是$c_k$的$N$倍，所以，正变换就是求频域系数。离散傅里叶变换$X[k]$,$k$的取值范围为$0,1,2,\dotsi,N-1$,频率在$[0,2\pi)$的范围内，但是可以把$X[k]$扩展成一个周期函数$\tilde{X}[k]$
$$
\tilde{X}[k] = X[k], k=0,1,2,\dotsi, N-1 \\
\tilde{X}[k+N] = \tilde{X}[k], k \in \Z \\
$$
而离散傅里叶逆变换为
$$
x[n] = \frac{1}{N}\sum_{k=0}^{N-1}X[k]e^{j\frac{2\pi}{N}kn}
$$
离散傅里叶变换对(正变换和反变换)可以标记为如下的记号
$$
x[n] \xleftrightarrow{DFT} X[k]
$$

### 离散序列的连续傅里叶变换
在离散傅里叶变换当中，$[0,2\pi)$当中一共有$N$个离散频率，不同频率的复指数信号具有两两正交性。从线性空间的角度来看，这$N$个复指数信号构成了$N$维线性复空间的一组正交基，任何信号都可以表达成这组基的线性组合。离散傅里叶变换就是求一个离散序列在这组正交基下的坐标。
一个线性空间的正交基不止一组，二是可以有无穷多组。比如
$$
{e_k}^{'}[n] = e^{jw_0n}e_k[n] = e^{j(\frac{2\pi}{N}k + w_0)n}, k=0,1,\dotsi,N-1
$$
可以验证，它们两两之间也是正交的
$$
\sum_{n=0}^{N-1}{e_k}^{'}[n]\overline{{e_l}^{'}[n]} = \sum_{n=0}^{N-1}e^{j\frac{2\pi}{N}(k-l)n}=\begin{cases}
N, k=l  \\
0, k \not = l \\
\end{cases}
$$

我们取$w_0 = \frac{\pi}{N}$,则
$$
{e_k}^{'}[n] = e^{j\frac{2\pi}{N}(k+0.5)n}, k=0,1,\dotsi, N-1 \\
X^{'}[k] = \sum_{n=0}^{N-1}x[n]e^{-j\frac{2\pi}{N}(k+0.5)n} \\
x[n] = \frac{1}{N}\sum_{k=0}^{N-1}X^{'}[k]e^{j\frac{2\pi}{N}(k+0.5)n} \\
$$

离散信号的连续傅里叶变换
$$
X(w) = \sum_{n=0}^{N-1}x[n]e^{-jwn}  \\
x[n] = \frac{1}{2\pi}\int_{0}^{2\pi}X(w)e^{jwn}dw
$$
这个变换对可以记为
$$
x[n] \xleftrightarrow{FT} X(w)
$$
$X(w)$的定义域可以认为是$(-\infin, \infin)$,是以$2\pi$为周期的周期函数，离散傅里叶变换$X[k]$是$X(w)$在$w=\frac{2\pi k}{N},k=0,1,\dotsi,N-1$上的采样。利用$X(w)$的一个周期可以合成时域离散信号，就是连续反变换，用$X(w)$的平均$N$个采样也可以合成时域离散信号，就是离散反变换。

### 离散傅里叶变换的性质
由于我们把离散傅里叶变换的时域索引$n$和频域索引$k$都局限在$[0,N-1]$内的整数，不存在负数索引，而连续信号的傅里叶变换的对称性都是关于零点的，从而需要做一定的处理。

一种方法是采用$x[n]$ 和$X[k]$的周期化形式$\tilde{x}[n]$和$\tilde{X}[k],k \in \Z$,这样就引入了负数索引，采用连续信号傅立叶变换的对称性可以平行地搬到傅立叶变换。另一种方式是把负数索引通过加$N$的整数倍搬到$[0,N-1]$的范围内，和第一种方法是等价的。定义以下符号
$$
((n))_N = n\pmod N
$$
表示模$N$的余数，取值范围在$[0,N-1]$
长度为$N$的有限长度信号$x[n]$和周期化信号$\tilde{x}[n]$之间存在如下的关系
$$
\tilde{x}[n] =x[((n))_N], n \in \Z
$$
如果$\tilde{x}[n]$为偶函数，也就是
$$
\tilde{x}[-n] = \tilde{x}[n]
$$
对称点为$N/2$

(1) 对称性
如果
$$
x[n] \xleftrightarrow{DFT} X[k] \\
$$
那么
$$
X[n] \xleftrightarrow{DFT} Nx[((-k))_N]
$$
(2) 线性
$$
a_1x_1[n] + a_2x_2[n] \xleftrightarrow{DFT} a_1X_1[k] + a_2X_2[k]
$$
(3) 奇偶虚实性
$$
\begin{cases}
    x[((-n))_N] \xleftrightarrow{DFT} X[((-k))_N] \\
x^{*}[((-n))_N] \xleftrightarrow{DFT} X^{*}[k]  \\
x^{*}[n] \xleftrightarrow{DFT} X^{*}[((-k))_N] \\
\end{cases}
$$

偶函数的离散傅里叶变换也是偶函数
奇函数的离散傅里叶变换也是奇函数

如果$x[n]$是实函数，则
$$
\begin{cases}
    \real \lbrace X[k] \rbrace = \sum_{n=0}^{N-1}x[n]\cos{\frac{2\pi}{N}kn} \\[0.5em]
    \Im \lbrace X[k] \rbrace = \sum_{n=0}^{N-1}x[n] \sin{\frac{2\pi}{N}kn} \\
\end{cases}
$$
实函数的傅里叶变换的实部是偶函数，虚部是奇函数
使用幅度和相位来表示，有
$$
\begin{cases}
|X[k]| = \sqrt{\real {\lbrace X[k] \rbrace}^2  + \Im {\lbrace X[k] \rbrace}^2 } \\[0.5em]
\varphi[k] = arctan \frac{\Im{\lbrace X[k] \rbrace}}{\real {\lbrace X[k] \rbrace}}
\end{cases}
$$
实函数的傅里叶变换的幅度是偶函数，相位是奇函数
实偶函数的离散傅里叶变换是实偶函数

(4) 尺度变换
连续信号存在尺度变换，但是不适用于离散信号

(5) 循环移位特性
$$
x[((n-m))_N] \xleftrightarrow{DFT} X[k]e^{-j\frac{2\pi}{N}km}
$$
时域的循环移位对应于频域的相移，相同的循环，对不同的频率的相移不同。频率越高，相移越大。

(6) 频移特性
$$
x[n]e^{j\frac{2\pi}{N}ln} = X[((k-l))_N]
$$
在时域乘以一个频率为$\frac{2\pi}{N}l$的复指数信号，相当于频谱移动了

### 循环卷积
周期为$N$的周期信号$\tilde{x}[n]$,经过系统$\tilde{h}[n]$,输出信号为$\tilde{y}[n]$,则
$$
\tilde{y}[n] = \sum_{k=-\infin}^{\infin}\tilde{x}[k]\tilde{h}[n-k]
$$
将系统的冲激响应切断并且累加，得到一个长度为$N$的有限长度序列$h(n)$,如果$\tilde{h}[n]$是有限长度的，并且长度小于$N$,就把$\tilde{h}[n]$补零得到长度为$N$的序列$h[n]$。于是得到
$$
y[n] = \sum_{m=0}^{N-1}x[m]h[((n-m))_N], n=0,1,\dotsi, N-1
$$
这个运算就叫做循环卷积，或者圆卷积，记作
$$
y[n] = x[n]\circledast h[n], n=0,1,\dotsi,N-1,
$$
循环卷积要求两个序列的长度相等，输出序列也是同样的长度。

### 离散卷积定理
时域的卷积对应频域的乘积，使用循环卷积来表示
$$
x[n] \circledast h[n] \xleftrightarrow{DFT} X[k]H[k]
$$

我们把$H[k]$称为系统的频率特性，$H[k]$是一个复数，可以写成幅值和相位的形式
$$
H[k] = |H[k]|e^{j\varphi[k]}, k=0,1,2,\dotsi,N-1
$$
如果输入信号的周期是$N$,那么只包含N个频率成分，只需要知道系统对这$N$个频率成分的响应特性就可以了。如何从一个任意长度的系统响应得到对$N$个频率成分的特性。

## 第6章 采样
采样保持电路,
开关$K$闭合的时候为跟随阶段，电容器被充电，如果电容值比较小，输入信号变化比较慢，电容器上电压的过渡过程可以忽略，那么电容器两端的电压就是输入信号。
开关$K$断开的时候为保持阶段，忽略电容器的漏电效应，则电容器上的电压保持不变。此时，A/D开始工作，将所采样的电压点转换为数字信号。

用一个时序来控制开关的闭合和断开，就实现了对输入信号的采样。

### 采样的数学表达方法
对一个输入的连续信号进行采样，在数学上表达为这个信号与一个采样周期信号$p(t)$的乘积。采样信号经常采用周期矩形脉冲和周期冲激信号

采样后的信号表达为
$$
x_s(t) =x(t)p(t)
$$
实际应用的一般是均匀采样。加入采样信号的周期为$T_s$,角频率为$w_s = 2\pi/T_s$,则其傅里叶变换为
$$
P(w) = 2\pi \sum_{n=-\infin}^{\infin}P_n \delta(w-nw_s)
$$
其中,$P_n$为$p(t)$的傅里叶系数，表达为
$$
P_n = \frac{1}{T_s}\int_{-\frac{T_s}{2}}^{\frac{T_s}{2}}p(t)e^{-jnw_st}dt
$$
采样后的信号的频率，是连续信号的频谱$X(w)$以$w_s$为周期重复，用采样信号的傅里叶系数加权并且累加得到。可以看到，如果相邻位置的连续频谱不重叠，则相加后它们互不影响，则采样信号的频谱完全保留了原来的连续频谱。这个原理就是采样定理的来源。

### 周期矩形脉冲
周期矩形脉冲的傅里叶系数为
$$
P_n = \frac{A\tau}{T_s}sinc(\frac{nw_s\tau}{2\pi})
$$
用矩形脉冲采样后的信号的傅里叶变换为
$$
X_s(w) = \sum_{n=-\infin}^{\infin}P_n X(w-nw_s) \\
= \frac{A\tau}{T_s}\sum_{n=-\infin}^{\infin}sinc(\frac{nw_s\tau}{2\pi})X(w-nw_s)
$$
周期矩形脉冲采样后的频谱，是连续信号的频谱$X(w)$以$w_s$为周期重复，用$sinc$函数加权并且累加得到

### 周期冲激脉冲
如果采样信号是周期冲激函数，周期为$T_s$
$$
p(t) = \sum_{n=-\infin}^{\infin}\delta(t - nT_s)
$$
其傅里叶系数为
$$
P_n = \frac{1}{T_s}\int_{-\frac{T_s}{2}}^{\frac{T_s}{2}}\delta(t)e^{-jnw_st}dt=\frac{1}{Ts}
$$

## 第7章 信号的谱分析
余弦信号
$$
\tilde{x}(t) = \cos{(2\pi t)}, \space t \in (-\infin, +\infin)
$$
这个信号的傅里叶变换为
$$
\tilde{X}(w) = \pi \delta(w-2\pi) + \pi\delta(w+2\pi)
$$
使用$2Hz$的采样频率采样，得到离散信号
$$
\tilde{x}[n] = \cos(2\pi t)|_{t=0.5n} = \cos(\pi n), \space (n \in \Z)
$$
取采样信号的一个周期
$$
x[n] = \tilde{x}[n], \space n=0,1
$$
对$x[n]$做连续傅里叶变换
$$
X(w) = \sum_{n=0}^{1}x[n]e^{-jwn} = 1 - e^{-jw} = 1-\cos{w} + j \sin{w}
$$
由上市可以求得幅度谱为
$$
|X(w)| = \sqrt{{(1-\cos{w})}^2 + {\sin}^2 w}=\sqrt{2(1-\cos{w})}
$$
相位谱为
$$
\tan{\varphi(w)}=\frac{\sin{w}}{1-\cos{w}}=\tan{(\frac{\pi}{2} - \frac{w}{2})} \\
\varphi(w) = \frac{1}{2}(\pi - w)
$$
对$X(w)$在$\frac{2\pi}{N}k=\pi k,\space k=0,1,\dotsi,N-1$的采样，就是离散傅里叶变换$X[k]$。在这里只有2个样点，直接写出来就是$X[0]=0,X[1]=2$
从线性空间的理论我们可以知道，$X[k]$其实就是在一组正交基下的坐标，这组正交基包括两个矢量
$$
e_0=[1,1], e_1=[1,-1]
$$
在$n=0$处，幅度为零，相位其实无意义，但是从相位谱连续性的角度定义为$\frac{\pi}{2}$。$n=0$对应直流成分，正弦信号显然直流成分为零。
在$n=1$处，幅度为2，相位为0，就是实数2，这条谱线对应频率点$1Hz$
还可以用$8Hz$的频率进行采样
可以发现傅里叶变换的对称性，对称点为$w=\pi$或者$n=N/2=4$。因为$x[n]$是实函数，$X(w)/X[k]$的幅度为偶函数，相位为奇函数。
离散频谱$X[k]$为$[0,4,0,0,0,0,0,4]$
在离散频谱上只有$X[1],x[7]$两条不为零的谱线，对应相位为零。其它谱线幅度为零，相位没有意义。在幅度为零的点上，相位出现了跳变。

### 频率分辨率
$\Delta=\frac{1}{T}$
要分辨一个频率成分，采样至少要达到一个周期。在采样时间$T$内，除直流外，能够分辨的最低频率就是在采样时间正好是一个周期。这个频率对应在离散频谱的第一根谱线，也称作基频，频率为$1/T$。这是相邻两根离散谱线之间的间隔，这就是频率分辨率。

### 泄漏效应
频谱的泄漏，是由非整数周期采样引起的。
直接从数值上看，这12个点的均值不为零，因此离散频谱当中会有一个直流成分。正弦周期信号在整数周期上均值为零，在非整数周期上均值不为零。
从理论上看，离散傅里叶变换就是信号在一组正交基上的投影，这组正交基都是复指数信号
$$
e_k[n]=e^{\frac{2\pi}{N} k n} = \cos(\frac{2\pi}{N}kn) + j\sin{(\frac{2\pi}{N}kn)}, \space n=0,1,\dotsi,N-1
$$

## 第8章 线性空间理论
数学里的空间，就是三维空间在概念上的自然拓展；因此线性空间里面的所有概念，都能够在三维空间里面找到我们所熟悉的对应概念。

$N$维线性空间是一个集合，其中的每一个元素都是一个$N$维的矢量，表示为$x=(x_1, x_2,x_3,\dotsi,x_N)$,矢量中的每一个元素，如果是实数，就是实空间。如果是复数，就是复空间。实空间是复空间的一个特例。

线性空间当中的一个元素，也称作一个点。
要把一个集合叫做空间，还需要满足对加法和数乘的封闭。

* 加法, $x_1 + x_2 \in Set$
* 乘法, $\alpha$是一个标量, $\alpha \cdot  x_1 \in Set$

三维空间中的一个立方体是一个集合，但是不是一个空间，因为立方体内的一个点的坐标乘以10会跑到立方体的外面，也就是说这个集合对数乘不封闭。对加法和乘法的封闭性，要求空间不能有边界。

但是没有边界并不意味着一定是无限的。在编码领域存在有限域上的线性空间。

### 8.3 度量空间，
距离的定义，对于线性空间中的2个点, $x=(x_1, x_2, x_3,\dotsi, x_N）$, $y=(y_1, y2，\dotsi, y_N）$，类似于三维空间，很容易就联想到它们之间的距离应该为
$$
d(x,y) = \sqrt{\sum_{n=1}^{N}|x_n - y_n|^2}
$$
这个距离叫欧几里得距离，这样的线性空间叫欧几里得空间。

**度量**
$V$是一个线性空间, $x,y \in V$，$\R$是实数域, 若$d(\cdot, \cdot): V \times V \mapsto{} \R$。如果满足下面3个条件，则称$d(\cdot,\cdot):V \times V \mapsto{} \R$是一个度量。

这个符号的意思是，$d$是一个函数，它需要两个属于$V$的元素作为自变量，值域为实数域$\R$。也就是说，这个函数是$V \times V$到$\R$的一个映射$\mapsto{}$。
(1)非负性，$d(x,y) \ge 0$,当且仅当$x=y$时，$d(x,y)=0$
(2)对称性，$d(x,y)=d(y,x)$
(3)三角不等式, $d(x,y) \le d(x,z) + d(y,z)$

度量是一个非负实数。

欧式距离是我们最常用的度量。其它形式的度量，例如$d(x,y)= \sum_{n=1}^{N} |x_n - y_n|$也满足上面的3个条件。

定义了度量的线性空间，就叫做**度量空间**

有了度量的定义，我们才能够定义极限，才能够定义积分、微分这些运算。

**定义:实数列的极限**
设${x_n}$为一个实数列，$A$为一个定数。若给定任意的$\epsilon > 0$, 总存在正整数$N$, 使得当$n > N$时，有$|x_n - A| < \epsilon$, 则称数列${x_n}$收敛于$A$, 定数$A$称为数列${x_n}$的极限，记作
$$
\lim\limits_{n-> \infin} x_n = A
$$

在一个更加广泛的度量空间里，极限的定义就扩展成为
**定义：度量空间中点列的极限**
设$x_n$是一个度量空间中的点列, $A$为度量空间中的一个定点。若对任意给定的$\epsilon > 0$, 总存在正整数$N$, 使得当$n > N$时有$d(x_n -A) < \epsilon$,则称点列${x_n}$收敛于$A$, 定点$A$称为点列${x_n}$的极限,记作
$$
\lim\limits_{n-> \infin} x_n = A
$$
可见，极限的定义依赖于度量的定义，有了度量，就可以定义极限了。而实际上，在实数列的极限当中，两个实数的差的绝对值也是一个度量。

### 8.4 赋范空间
比度量空间更进一步的概念叫做赋范空间。赋范空间就是定义了**范数**的线性空间。
**定义:范数**
设$V$是一个线性空间, $x,y\in V$, $\R$时实数域，$\Complex$是复数域，$\alpha \in \Complex$,若$||\cdot||: S \mapsto{} \R $满足以下3个条件，则称$||\cdot||: V \mapsto{} R$是$V$上的一个范数。

实际上，上式中, S在哪里定义的? $\alpha$没有用到吗? 

(1) 非负性: $||x|| \ge 0$; 且当且仅当$x=0$,才有$||x||=0$
(2) 齐次性: $||\alpha x|| = |\alpha| \cdot ||x||$
(3) 三角不等式: ||x + y|| \le ||x|| + ||y||

范数是一个非负实数，是实数的绝对值的一个扩展。可以验证，实数的绝对值也是一个范数。

我们经常使用到的一个范数系列叫做$p-$范数，定义如下:
假设$x=(x_1, x_2, x_3, \dotsi, x_N)$,则
$$
p-范数: ||x||_p = \sqrt[p]{\sum_{n=1}^{N}|x_n|^p}
$$

其中的$p$是正整数，典型地取$p = 1,2,\infin$,则得到最常用的三个范数

1-范数
$$
||x||_1 = \sum_{n=1}^{N} |x_n|
$$

2-范数
$$
||x||_2 = \sqrt{\sum_{n=1}^{N} |x_n|^2}
$$

$\infin$-范数
$$
||x||_{\infin} = \max_{n=1,2,\dotsi, N}|x_n|
$$
当$p$取无穷的时候，相当去取其中的最大值

定义了范数后，度量可以从范数中诱导出来，可以验证
$$
d(x,y) = ||x-y||
$$
是一个度量，而欧式距离就是
$$
d(x,y) = ||x-y||_{2} = \sqrt{\sum_{n=1}^{N}|x_n - y_n|^2}
$$

### 8.5 内积空间
比赋范空间更进一步的是**内积空间**，也就是定义了内积的线性空间

**定义:内积**
假定$V$是一个线性空间，$x,y,z \in V$, $\Complex$是复数域, $\alpha \in \Complex$, 若$\lang \cdot , \cdot \rang: V \times V \mapsto \Complex$满足以下4个条件，则称$\lang \cdot, \cdot \rang: V \times V \mapsto \Complex$是一个内积。

(1) 正定性: $\lang x,x \rang \ge 0$, $\lang x,x \rang=0$,当且仅当$x=0$
(2) 线性: $\lang x, y+z \rang = \lang x,y \rang + \lang x,z \rang $
(3) 线性: $\lang \alpha x, y \rang = \alpha \lang x,y \rang$
(4) 对称性:$ \lang x,y \rang = \overline{\lang y,x \rang} $

内积是一个复数，而向量和其自身的内积是一个非负实数。

假设$x=（x_1, x_2,\dotsi, x_N), y=(y_1, y_2,\dotsi,y_N)$,可以验证
$$
\lang x,y \rang = \sum_{n=1}^{N}x_n \overline{y_n}
$$
是一个内积。

从这个内积可以进一步诱导出$2-$范数和欧式距离
$$
||x||_2 = \sqrt{\lang x,x \rang} \\[0.5em]
d(x,y) = \sqrt{\lang x-y, x-y \rang }
$$

完备的内积空间叫做**希尔伯特空间**,完备的概念在实数论的部分已经讲过了，也就是柯西序列收敛，柯西准则和极限存在是等价的。实数集是完备的。而有理数集是不完备的。

大卫.希尔伯特, 1862~1943, 德国数学家。1900年他提出了23个数学问题，史称希尔伯特问题，激发了整个数学界的想象力。

**内积的作用:**
平面上有两个矢量$\lang x_1, y_1 \rang$, $\lang x_2, y_2 \rang$, 这里的坐标都是实数，它们之间的夹角为
$$
\begin{aligned}
\cos \alpha &= \cos{(\theta_2 - \theta_1)} \\
&= \frac{x_1x_2 + y_1y_2}{\sqrt{x_1^2 + y_1^2} \sqrt{x_2^2 + y_2^2}}
\end{aligned}
$$
三维空间中的两个矢量$( x_1, y_1, z_1)$, $( x_2, y_2, z_2 )$的夹角为
$$
\cos{\alpha} = \frac{x_1 x_2 + y_1y_2 + z_1z_2}{\sqrt{x_1^2 + y_1^2 + z_1^2} \sqrt{x_2^2 + y_2^2 + z_2^2}}
$$
表达式具有完美的对称结构。虽然超过三维的空间是什么样子我们想象不出来，但是对于$N$维欧式空间的两个矢量$x=(x_1, x_2, \dotsi,x_N)$,$y=(y_1, y_2, \dotsi, y_N)$,我们在这里仍然局限于实数坐标。可以证明以下的不等式

$$
|\sum_{n=1}^{N}x_ny_n| \le \sqrt{\sum_{n=1}^{N}x_n^2} \sqrt{\sum_{n=1}^{N}y_n^2}
$$
这个不等式称为**柯西-施瓦茨不等式**,在很多地方都会用到它

把三维空间矢量的夹角概念推广，可以得到$N$维空间矢量的夹角为
$$
\cos{\alpha} = \frac{\sum_{n=1}^{N}x_ny_n}{\sqrt{\sum_{n=1}^{N}x_n^2} \sqrt{\sum_{n=1}^{N}y_n^2}}
$$
这个式子的绝对值小于等于1，因此把它定义为夹角的余弦是合理的。分子就是内积，分母就是范数。上式可以另写为
$$
\cos{\alpha} = \frac{\lang x,y \rang}{\sqrt{\lang x,x \rang} \sqrt{\lang y, y \rang}} = \frac{\lang x,y \rang}{||x||_2 \cdot ||y||_2}
$$

在$N$维的实欧式空间当中，上面提到的内积有一个专门的名字，叫做**点积**

**定义:点积**
$V$是一个$N$维的实欧式空间, $x,y \in V$, $x=(x_1, x_2, \dotsi, x_N), y=(y_1, y_2, \dotsi, y_N)$,则称
$$
x\cdot y = \sum_{n=1}^{N} x_n y_n
$$
为$x,y$的点积，也称为标量基或者点乘

点积是内积在$N$维实欧式空间的一种具体形式，而内积的概念比点积更加普遍。

在$N$维复欧式空间当中，内积可以定义为
$$
\lang x,y \rang = \sum_{n=1}^{N} x_n \overline{y_n}
$$
而周期为$T$的连续周期函数也构成了一个线性空间，其中的内积可以定义为
$$
\lang f,g \rang = \int_{-\frac{T}{2}}^{\frac{T}{2}}f(t)\overline{g(t)}dt
$$
注意在复数的情况下，定义里面有一个共轭，因为这样才能够保持$\lang x, x \rang$是一个非负实数，满足内积定义的第一条性质。在内积的普遍顶一下，柯西-施瓦茨不等式仍然成立，也就是：

$V$是一个内积空间, $\lang \cdot, \cdot \rang:V \times V \mapsto \Complex$是$V$上的一个内积,$x,y \in V$, 则
$$
|\lang x,y \rang| \le \sqrt{\lang x,x \rang} \sqrt{\lang y,y \rang} = ||x|| \cdot ||y||
$$
数学家干的事情，把具体的概念搞得越来越抽象，适用范围越来越大，也越来越美。

### 正交与正交基
既然柯西-施瓦茨不等式在普遍的内积意义下仍然成立，那么也可以在普遍的意义下定义两个矢量的夹角，比如我们模仿$N$维的实欧式空间，这样来定义
$$
\cos{\alpha} = \frac{\lang x,y \rang}{||x|| \cdot ||y||}
$$
但是一般$\lang x,y \rang$是一个复数，一个角度的余弦怎么可以是一个复数呢?因此我们给内积加上求绝对值的操作。
$$
\cos{\alpha} = \frac{|\lang x,y \rang|}{||x|| \cdot ||y||}
$$
作为一个角度的余弦值，只能取非负值，余弦函数的值域被砍掉了一半，夹角只能是$[-\frac{\pi}{2}, \frac{\pi}{2}] + 2n\pi$, 多少还是让人不满意。

另外也可以改变一点，做如下定义:
$$
\cos{\alpha} = \begin{cases}
 \frac{|\lang x,y \rang|}{||x|| \cdot ||y||} \space \R{\lang x,y \rang} \ge 0 \\[0.5em]
  \frac{-|\lang x,y \rang|}{||x|| \cdot ||y||} \space \R{\lang x,y \rang} \lt 0
\end{cases}
$$

有两个角度非常重要。


