# Complex Variables DeMystified
>A self-teaching guide

书籍，demystified series

Complex variable, more advanced version , Complex analysis, one of the most fascinating areas in pure and applied mathematics.

imaginary number, 引入了复数后，进入了复变量的领域,复分析,
comp

想要成为一名职业的纯数学家，或者应用数学家的学生都需要深入掌握复分析。复数，欧拉方程，Euler's identity, 欧拉恒等式。应用方向:
* 电磁场场分析
* fluid dynamics, 流体动力学, 
* 温度，静电学，函数的积分方程
* 量子理论, 

复数 $c = a+ ib$
comlex conjugate: $a - ib$
$c \overline{c} = a^2 + b^2 = (a+ib)(a-ib)$
复数除法
$$
\begin{aligned}
\frac{c}{k} &= \frac{a+ ib}{m + in} \\  
&=\frac{am+bn}{m^2+n^2} + i\frac{bm-an}{m^2 + n^2}
\end{aligned}
$$
complex variable,
复分析完全能够替代实分析, real analysis, 在物理和工程方面发现了很多的应用。
$$
\cos{\theta} = \frac{e^{i\theta} + e^{-i\theta}}{2} \\[0.5em]
\sin{\theta} = \frac{e^{i\theta} - e^{-i\theta}}{2i} \\
$$
我们使用$z$来表示一个复数, complex variable, 在多项式的研究中，实系数。
let $p$是一个实系数的多项式，$z$是$p$的根，那么$\overline z$也是$p$的根。

我们可以将复数画在$x-y$平面上, 成为复平面，$z$平面, y为虚轴，x为实轴
$r=|z|=\sqrt{x^2 + y^2}$

复共轭的规则，rules
let $z=x+iy, w=u+iv$,为两个复变量,
$$
\overline{z+w} = \overline{z} + \overline{w} \\
\overline{zw} = \overline{z}\overline{w} \\[0.5em]
\overline{\big( \frac{z}{w} \big)} = \frac{\overline{{z}}}{\overline{w}}
$$

inverse of $z$
$$
zz^{-1} = 1 \\[0.5em]
z^{-1} =\frac{\overline{z}}{|z|^2} = \frac{1}{z}\\[0.5em]
\frac{z}{w} = \frac{z\overline{w}}{w\overline{w}} = \frac{z\overline{w}}{|w|^2}
$$

Pascal's Triangle
$(x+y)^n$

## 复数系统的定理
$u,w,z \in \Complex$, then
$z+w \in \Complex$, $zw \in \Complex$, closure law
$z+w = w+z$, commutative law of addition
$u+(w+z)=(u+w)+z$, associative law of addition
$zw=wz$, commutative law of multiplication
$u(wz)=(uw)z$, associative law of multiplication
$u(w+z)=uw+uz$, distributive law,
$z=0+0i$, identity with respect to addition,
$$
z + 0 = 0+z
$$
$z=1+i0=1$, identity with respect to multiplication,
$$
z\cdot 1 = 1\cdot z = z
$$
additive inverse, $-z, z+(-z) = (-z) +z = 0$
multiplicative inverse $z^{-1}$
$$
zz^{-1}=z^{-1}z=1
$$
A set满足上述属性的集合，称为field, 域。复数集合是最小的代数闭合域，包含实数集，作为一个子集

**modulus**
magnitude, abolute value of a complex number, 绝对值，模, 将实数与它的共轭相乘即得到一个正数，取平方根
有定义
$$
|z_1z_2| = |z_1||z_2| \\[0.5em]
\lvert \frac{z_1}{z_2}\rvert = \frac{|z_1|}{|z_2|}
$$

triangle inequality,三角不等式
$$
\begin{aligned}
    |z_1 + z_2| &\leqslant |z_1| + |z_2| \\
    |z_1 + z_2 + \dotsi + z_n &\leqslant |z_1| + |z_2| + \dotsi + |z_n| \\
    |z_1 + z_2| &\geqslant |z_1| - |z_2| \\
    |z_1 - z_2| &\geqslant |z_1| - |z_2| \\
\end{aligned}
$$

also $w\overline{z} + \overline{w}z =2\Reals(z\overline{w}) \leqslant 2|z||w|$

## Polar representation
使用极坐标来表示复数, 笛卡尔坐标表示法, Cartesian representation of a complex number,用极化坐标来表示$(r,\theta)$
$$
x=r\cos{\theta}, \space y=r\sin{\theta}
$$
转化成极坐标, polar coordinate
$$
r=\sqrt{x^2 + y^2} = |x+iy| \\
\tan{\theta} = y/x \\
z = x + iy = r(\cos{\theta} + i\sin{\theta})
$$

**argument of z**
value of $\theta$, is called the argument of $z$ or $arg z$, $\arg z, -\pi \le \Theta \le \pi$

$$
\arg z = Arg z + 2n\pi, \space n=0,\plusmn1, \plusmn2, \dotsi
$$
The principla value can be specified to between $0$ and $2\pi$

欧拉公式,
泰勒展开,对$\theta=0$展开
$$
\cos{\theta} = 1 - \frac{1}{2!}\theta^{2} + \frac{1}{4!}\theta^{4} - \frac{1}{6!}\theta^{6} + \dotsi  \\[0.5em]
\sin{\theta} = \theta - \frac{1}{3!}\theta^3 + \frac{1}{5!}\theta^5  - \frac{1}{7!}\theta^7 +  \dotsi
$$

泰勒级数展开
$$
f(x) = \sum_{n=0}^{\infin}\frac{f^{(n)}(x_0)(x-x_0)^n}{n!}
$$
$e^{i\theta} = \cos{\theta} + i\sin{\theta}$
complex exponential form, polar form
$$
z = re^{i\theta} \\
\cos{\theta} = \frac{e^{i\theta} + e^{-i\theta}}{2} \\
\sin{\theta} = \frac{e^{i\theta} - e^{-i\theta}}{2i} \\
$$
乘法运算非常方便
$$
zw = (re^{i\theta})(\rho e^{j\phi})=r\rho e^{i(\theta + \phi)}
$$
除法
$$
\frac{z}{w} = \frac{re^{i\theta}}{\rho e^{i\phi}} = \frac{r}{\rho}e^{i(\theta - \phi)}
$$
reciprocal of a complex number
$$
z^{-1} = \frac{1}{r}e^{-i\theta}
$$
rasing a complex number to a power
$$
z^n = r^n e^{in\theta}
$$
complex conjugate
$$
\overline{z} = r e^{-i\theta}
$$
欧拉方程
$$
e^{i\pi}=\cos{\pi} + i\sin{\pi} \Rightarrow e^{i\pi}= -1 \\
$$

**DeMoivre's Theorem**
棣摩福定理， 棣莫弗定理，
let $z_1=r_1(\cos{\theta_1} + i\sin{\theta_1}$ and $z_2=r_2(\cos{\theta_2} + i\sin{\theta_2})$, 根据三角恒等式，可以得到
$$
z_1z_2=r_1r_2[\cos{(\theta_1} + \theta_2) + i\sin{(\theta_1 + \theta_2)}] \\
z_1/z_2=\frac{r_1}{r_2} [\cos{(\theta_1 - \theta_2) + i\sin{(\theta_1 - \theta_2)}}]\\
z^n = r^n(\cos{n\theta} + i\sin{n\theta}) \\
$$
**nth root of unity**
$$
z^n = 1 \\
z=(\cos{2k\pi/n} + i\sin{2k\pi/n})=e^{i2k\pi/n} \\
k=0,1,2,\dotsi, n-1 \\
$$
如果$w=e^{i2\pi/n}$,那么$n$ roots为$1,w, w^2,w^3, \dotsi,w^{n-1}$

例子, $\sin^{-1}z = -i\ln{(iz \plusmn \sqrt{1-z^2})}$
*solution*
$$
\cos^2\theta + \sin^2\theta = 1 \\
\cos{\theta} = \plusmn\sqrt{1-\sin^2\theta}
$$
Now let $\theta = \sin^{-1}z$, 则
$$
\cos{(\sin^{-1}z)}= \plusmn \sqrt{1-\sin^2{(\sin^{-1}z)}}=\plusmn\sqrt{1-z^2}
$$
再根据Euler's formula
$$
e^{i\theta} = \cos{\theta} + i\sin{\theta}
$$
Again  let $\theta = \sin^{-1}z$, 则
$$
e^{i\sin^{-1}z} = \cos{(\sin^{-1}z)} + i\sin{(\sin^{-1}z)}=\plusmn\sqrt{1-z^2} + iz
$$
方程两边计算自然对然,
$$
i\sin^{-1}z = \ln{(iz \plusmn \sqrt{1-z^2})} \\
\Rightarrow \sin^{-1}z = -i\ln{(iz \plusmn \sqrt{1-z^2})}
$$
得证。

# chap 2 Functions,Limits, Continuity
complex functions, alculus like limits and continuity,
复数函数, $w=f(z), z \in \Complex$

a restricted set $S$, domain of the function, 

$f(z) = 1/z, z \in \Complex \backslash \{0\}$

$f(z) = f(x+iy)= u(x,y)+iv(x,y)$
$$
Re(f)=u(x,y) \\
Im(f)=v(x,y) \\
$$
$\overline{f(z)}=\overline{f(x+iy)}=u(x,y)-iv(x,y)$
$$
f + \overline{f} = 2u \\
f - \overline{f} = 2iv \\
$$
另一方面
$$
u(x,y) = \frac{f(z) + \overline{f(z)}}{2} \\[0.5em]
v(x,y) = \frac{f(z) - \overline{f(z)}}{2i} \\
$$

# chap 2 Functions, Limits, Continuity
$z=re^{i\theta}$
$f(z) = f(re^{i\theta})=u(r,\theta) + iv(r,\theta)$
$|f(z)| = f(z)\overline{f(z)}$

# chap 3 The derivative and analytic functions
Derivative 定义,
$$
f^{'}(z_0) = \lim_{z \to z_0}\frac{f(z) - f(z_0)}{z-z_0}
$$
If a limit exists for all points in a domain $D$, we say that $f(z)$ is differentiable in $D$. Then we can say $f(z)$ is complex differentiable at the point $z_0$

Let $\Delta z = z - z_0$, then the derivative of $f(z)$ at the point $z_0$ can be 
$$
f^{'}(z_0) = \lim_{\Delta z \to 0}\frac{f(z_0 +\Delta z)-f(z_0)}{\Delta z}
$$
Leibniz notation,

定义:Analytic and Entire Functions,
Suppose that $f(z)$ is differentiable in an $\epsilon$-neighborhood of point $z_0$. We define the domain $D$ 
$$
|z-z_0| < \epsilon
$$
For some $\epsilon > 0$, $f^{'}(z)$ exists for all $z \in D$, then we say that $f(z)$ is analytic at the point $z_0$
如果$f(z)$is analytic on the whole complex plane, then we say the function $f(z)$ is entire!

微分的Leibniz notation, 莱布尼兹表示法, $w=f(z)$, then
$$
\Delta{w} = f(z) - f(z_0) \\[0.5em]
f'(z_0) = \lim\limits_{\Delta z \to 0}\frac{\Delta w}{\Delta z}= \frac{dw}{dz}
$$
和实数域一样，可以得到$\frac{d}{dz}(z^2) = 2z$
不幸的是，实数域的基本微积分操作无法直接移过来使用。$f(z)=\overline{z}$ 的求导并不存在。

在计算某个复数变量函数的导数时，一些规则需要从实数空间的微积分里采用过来,
* 常数求导
* 多项式求导
* 乘法规则
* 除法规则

Let $\alpha$ be a constant , which s a complex number, then 
$$
\frac{d}{dz}\alpha = 0 \\[0.5em]
\frac{d}{dz}(\alpha f)= \alpha\frac{df}{dz} \\
$$
For complex function in a series:
$$
f(z) = \sum_{n=0}^{\infin}a_n z^n
$$
求微分，对级数的每一项分别求导
$$
\frac{df}{dz}=\frac{d}{dz}(\sum_{n=0}^{\infin}a_n z^n) =\sum_{n=1}^{\infin}na_nz^{n-1}
$$

一些基本函数的求导,初等函数
$$
\frac{d}{dz}e^{z} = e^z
$$

The Product and Quotient Rules
$$
\frac{d}{dz}(fg) = \frac{df}{dz}g + \frac{dg}{dz}f
$$
Provided that $g(z) \not = 0$
$$
\frac{d}{dz}(\frac{f}{g}) = \frac{f'g -g'f}{g^2}
$$
The chain rule for composite functions, If $F(z)=g[f(z)]$, then
$$
F'(z) = g'[f(z)]f'(z)
$$

Theorem:
>If $f(z)$ is differentiable at a point $z_0$, then it is also continuous at $z_0$

L'HOPITAL's rule
Let $f(z), g(z)$ be two functions that are analytic at a point $z_0$, then provided $g'(z_0) \not = 0$, if $f(z_0)=g(z_0)= 0$, then 
$$
\lim\limits_{z \to z_0}\frac{f(z)}{g(z)} = \lim\limits_{z \to z_0}\frac{f'(z)}{g'(z)}
$$

复函数之比的极限等于它们的导数的比的极限

**The Cauchy-Riemann Equations**
柯西-黎曼方程, 所有的数学里面最重要和优雅的结果，快速判断方程是否analytic,
假设复方程为$f(z) = u(x,y) + iv(x,y)$

连续可微方程
Consider a open region $D$ in the complex plane and a function $f:D \to \Complex$. 如果这个函数是连续的，偏导数$\partial f/\partial x$ and $\partial f/\partial y$ 存在且连续，我们说$f$ 在$D$ 连续可微。如果$f$ $k$ 次连续可微，那么$f$ is $C^k$. 如果$f$ is $C^0$, 则 $f$是一个连续方程，不可微。

如果$f$在域$D$内连续可微，不依赖$\overline{z}$的话，$f$是analytic的。

function $f$ is analytic in a domain $D$ provided that 
$$
\frac{df}{d\overline{z}} = 0
$$
analytic 的函数又被称作 *holomorphic*, 解析函数，全纯函数,

有复数变量$z=x + iy$,则有
$$
\frac{\partial z}{\partial x} = 1,  \space
\frac{\partial z}{\partial y} = i \\
$$
复数共轭$\overline{z} = x - iy$,则有
$$
\frac{\partial z}{\partial x} = 1,  \space
\frac{\partial z}{\partial y} = -i \\
$$
反向求得, $x=(z + \overline{z})/2, y=(z-\overline{z})/2i$
$$
\frac{\partial x}{\partial z} = \frac{\partial x}{\partial \overline{z}}=\frac{1}{2} \\[0.5em]
\frac{\partial y}{\partial z} = -\frac{i}{2}, \space \frac{\partial y}{\partial \overline{z}}=+\frac{i}{2}
$$



No dependence on $\overline z$ 意味着real and imaginary parts must independently vanish. This gives us the Cauchy-Riemann equations.








