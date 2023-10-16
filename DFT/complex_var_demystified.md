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
使用上述推论
对$z$求导
$$
\frac{\partial}{\partial z}=\frac{\partial x}{\partial z}\frac{\partial}{\partial x} + \frac{\partial y}{\partial z}\frac{\partial}{\partial y} = \frac{1}{2}\frac{\partial}{\partial x} - \frac{i}{2}\frac{\partial}{\partial y}
$$

对$\overline{z}$求导
$$
\frac{\partial}{\partial\overline{z}}=\frac{\partial x}{\partial \overline{z}}\frac{\partial}{\partial x} + \frac{\partial y}{\partial \overline{z}}\frac{\partial}{\partial y}=\frac{1}{2}\frac{\partial}{\partial x} + \frac{i}{2}\frac{\partial}{\partial y}
$$


No dependence on $\overline z$ 意味着real and imaginary parts must independently vanish. This gives us the Cauchy-Riemann equations.

Now we use these results to write the derivatives $df/dz$ and $df/d\overline{z}$ in terms of derivatives with respect to the real variables $x$ and $y$
$$
\begin{aligned}
    \frac{\partial f}{\partial z} &=\frac{1}{2}(\frac{\partial}{\partial x} -i\frac{\partial}{\partial y})f \\[0.5em]
    &=\frac{1}{2}(\frac{\partial}{\partial x} -i\frac{\partial}{\partial y})(u+iv) \\[0.5em]
    &=\frac{1}{2}(\frac{\partial u}{\partial x} + \frac{\partial v}{\partial y})+\frac{i}{2}(\frac{\partial v}{\partial x} - \frac{\partial u}{\partial y})\\[1em]
\frac{\partial f}{\partial \overline{z}} &=\frac{1}{2}(\frac{\partial}{\partial x} + i\frac{\partial}{\partial y})f \\[0.5em]
    &=\frac{1}{2}(\frac{\partial}{\partial x} +i\frac{\partial}{\partial y})(u+iv) \\[0.5em]
    &=\frac{1}{2}(\frac{\partial u}{\partial x} - \frac{\partial v}{\partial y})+\frac{i}{2}(\frac{\partial v}{\partial x}+\frac{\partial u}{\partial y})
\end{aligned}
$$

The Cauchy-Riemann Equations,
$$
\frac{\partial u}{\partial x} = \frac{\partial v}{\partial y} \\[0.5em]
\frac{\partial u}{\partial y} =-\frac{\partial v}{\partial x} \\
$$
$f(z) = u(x,y) +iv(x,y), z_0 = x_0 + iy_0, \Delta{z}=\Delta{x}+i\Delta{y}, w=f(z)$
For notational convenience
$$
\begin{aligned}
\Delta{w}&= f(z_0+\Delta{z}) - f(z_0) \\
    &= u(x_0+\Delta{x}, y_0+\Delta{y}) - u(x_0,y_0) \\
&\space +i[v(x_0+\Delta{x}, y_0+\Delta{y})-v(x_0,y_0)]
\end{aligned}
$$
偏微分

如果偏微分$u_x, u_y,v_x,v_y$在点$(x_0,y_0)$上连续， 并满足柯西-莱曼方程，那么
$$
f'(z_0)=u_x(x_0,y_0)+iv_x(x_0,y_0) \\
f'(z_0)=v_y(x_0,y_0)-iu_y(x_0,y_0) \\
$$
另外，由上可知，$df/dz$的定义
$$
\frac{df}{dz}=\frac{\partial f}{\partial x} -i\frac{\partial f}{\partial y    }
$$

极坐标表示
$f(z)=u(r,\theta)+iv(r,\theta)$
柯西-莱曼公式的极坐标表示为
$$
\frac{\partial u}{\partial r} = \frac{1}{r}\frac{\partial v}{\partial \theta} \\[0.5em]
\frac{\partial v}{\partial r} = -\frac{1}{r}\frac{\partial u}{\partial \theta}
$$
同样
$$
f'(z)=e^{-i\theta}(\frac{\partial u}{\partial r} + i \frac{\partial v}{\partial r})
$$
一个数学家说这个复方程是regular、holomorphic的，正则函数，解析函数,在点的周围满足柯西-莱曼方程，

Singularity,
如果$f(z)$在点$z_0$上不满足analytic, 但是在包含$z_0$的邻域内满足analytic,我们说$z_0$是奇异的，singular point of $z_0$,在讨论复函数的级数展开时, singularities,关于奇特性的讨论是重要问题。

满足analytic的两个必要条件
- $f(z)$必须是连续的
- 满足柯西-莱曼方程

充分条件为:
- 在$z_0$的邻域$\epsilon$-neighborhood有定义
- 在邻域满足一阶偏导, $u_x, u_y, v_x, v_y$
- 偏导在$z_0$连续，且满足柯西-莱曼方程

解析函数的性质
Let $f(z)$和$g(z)$为域$D$内的两个解析函数,那么
* sum and difference $f\plusmn g$ is also analytic in $D$
* product $f(z)g(z)$ is analytic in $D$
* If $g(z)$ does not vanish at any pint in $D$, then the quotient $f(z)/g(z)$ is analytic in $D$
* The composition of two analytic functions $g[f(z)]$ or $f[g(z)]$ is analytic in $D$

Harmonic Functions
调和函数?满足Laplace's equation in some domain of the $x$-$y$ plane
$$
\frac{\partial^2 u}{\partial x^2} + \frac{\partial^2 u}{\partial y^2} = 0
$$
这里，我们假定$u(x,y)$具有连续的一阶，二阶偏导数, 一个重要的调和函数应用在物理学和工程学，是静电学领域。electrostatics,柯西-莱曼等式可以用来发现调和函数

如果$f(z)$是analytic function in doomain D, 那么u(x,y), v(x,y)都是调和函数。

Harmonic Conjugate,
suppose that $u$ and $v$ are two harmonic functions in domain $D$. If their first-order partial derivatives satisfy the Cauchy-Riemann equations, then we say that $v$ is the harmonic conjugate of $u$.

A function $f(z)=u(x,y)+iv(x,y)$ is analytic if and only if $v(x,y)$ is the harmonic conjugate of $u(x,y)$

例如, $u(x,y)=e^{-y}\sin{x}$ 是一个harmonic functiona吗?如果是的话，写下一个解析函数$f(z)$, $u(x,y)$是实部。

$$
\frac{\partial u}{\partial x}=e^{-y}\cos{x} \space \Rightarrow \frac{\partial^2 u}{\partial x^2}=-e^{-y}\sin{x}
$$
$$
\frac{\partial u}{\partial y}=-e^{-y}\sin{x} \space \Rightarrow \frac{\partial^2 u}{\partial y^2}=e^{-y}\sin{x}
$$
满足harmonic function的要求,
再使用Cauch-Riemann方程，
$$
\frac{\partial u}{\partial x} = e^{-y}\cos{x} = \frac{\partial v}{\partial y} \\
\frac{\partial u}{\partial y} = -e^{-y}\sin{x}=-\frac{\partial v}{\partial x} \\
$$
则可以得到$v(x,y)=-e^{-y}\cos{x}$,因此我们要求得解析函数为
$$
f(z)=u(x,y)+iv(x,y)=e^{-y}\sin{x} -ie^{-y}\cos{x}
$$


反射原理, Reflection Principle,
reflection principle允许我们能够如何成立 $\overline{f(z)} = f(\overline{z})$

# chap 4 elementary functions, 初等函数
**Complex Polynomials**
复多项式函数,
$$
f(z)=a_0 + a_1z+a_2z^2+\dotsi+a_nz^n
$$
The highest power $n$ is the *degree* of the polynomials
$a_j$是常量，叫做coefficients,系数,可以是复数,

可以理解为拥有复系数的实变量$x$和$y$的多项式,

**The Complex Exponential**
复指数函数, 
$$
f(z)=e^z=e^xe^{iy}
$$
使用欧拉公式，$e^{iy}=\cos{y}+i\sin{y}  $
则复指数函数的实部和虚部为
$$
Re(e^z)=u(x,y)=e^x\cos{y} \\
Im(e^z)=v(x,y)=e^x\sin{y} \\
$$

$e^z$ 是一个周期性函数，周期为$2k\pi i$, k是一个整数,

argument,是相位、角度。
$$
arg(e^z)=y+2n\pi, \space n=0,\plusmn1,\plusmn2,\dotsi
$$
logarithm is the inverse of exponential,
$$
e^{\ln{x}}=x
$$
因为$e^z$是一个周期函数，所以复对数有很多个解，
Let $z=e^w$, then $w=\ln{z}$
使用极坐标方式, $z=re^{i\theta}$
$$
w=\ln{z}=\ln{re^{i\theta}}=\ln{r}+\ln{e^{i\theta}}=\ln{r}+i\theta
$$
using the fact that the cosine and sine functions are $2\pi$ periodic,
$$
w=\ln{r} + i(\theta + 2k\pi), \space k=0,\plusmn 1,\plusmn 2, \dotsi
$$
复自然对数是一个多值的函数。$k=0$时，为主值, principal value, 或principal branch of $\ln{z}$. 此时我们将argument限定于$0 \le \theta \le 2\pi$ 或 $-\pi \le \pi$

**Trignometric Functions, 复三角函数**
$$
\cos{z} = \frac{e^{iz} + e^{-iz}}{2 } \\[0.5em]
\sin{z} = \frac{e^{iz} - e^{-iz}}{2i} \\[0.5em]
\tan{z} = -i\frac{e^{iz} - e^{-iz}}{e^{iz}+e^{-iz}} \\[0.5em]
\cot{z} = i\frac{e^{iz} + e^{-iz}}{e^{iz}-e^{-iz}} \\[0.5em]
\sec{z} = \frac{2}{e^{iz}+ e^{-iz}}\\[0.5em]
\csc{z} = \frac{2i}{e^{iz} - e^{-iz}}\\[0.5em]
$$
$\cos^2(z) + \sin^2(z) = 1$
三角函数的反函数
$$
\begin{aligned}
\cos^{-1}z &=\frac{1}{i}\ln{(z+\sqrt{z^2-1})} \\
\sin^{-1}z &=\frac{1}{i}\ln{iz + \sqrt{1-z^2}} \\
\tan^{-1}z &=\frac{1}{2i}\ln{\frac{1+iz}{1-iz}} \\
\sec^{-1}z &=\frac{1}{i}\ln(\frac{1+\sqrt{1-z^2}}{z}) \\
\csc^{-1}z &=\frac{1}{i}\ln(\frac{i+\sqrt{z^2-1}}{z}) \\
\cot^{-1}z &=\frac{1}{2i}\ln(\frac{z+i}{z-i}) \\
\end{aligned}
$$

**Hyperbolic functiosn, 双曲线函数**
$$
\cosh{z}=\frac{e^z+e^{-z}}{2} \\
\sinh{z}=\frac{e^z-e^{-z}}{2} \\
$$
这些函数有一些有趣的特性。$|cosh{z}|$的模在$y$轴的方向上有震荡,

$$
\cosh{z} = \cos{y}\cosh{x} + i\sin{y}\sinh{x}
$$
一些关系，双曲线函数和三角函数之间的一些关系，for complex arguments,
$$
\begin{aligned}
    \cosh{iz} &= \cos z \\
\sinh{iz} &= i\sin z \\
\cos{iz} &= \cosh z \\
\sin{iz} &= i\sinh z \\
\end{aligned}
$$
下列恒等式
$$
\cosh{(-z)}=\cosh{z} \\
\sinh(-z)=-\sinh{z} \\
\cosh^2z-\sinh^2z = 1 \\
\sinh(z+w) = \sinh{z}\cosh{w} + \cosh{z}\sinh{w} \\
\cosh(z+w) = \cosh{z}\cosh{w} + \sinh{z}\sinh{w}\\
$$
包含三角函数的恒等式
$$
\sinh{z}=\sinh{x}\cos{y} + i\cosh{x}\sin{y} \\
\cosh{z}=\cosh{x}\cos{y} + i\sinh{x}\sin{y} \\
|\sinh{z}|^2 = \sinh^2{x} + \sin^2{y} \\
|\cosh{z}|^2 = \sinh^2{x} + \cos^2{y} \\
$$
双曲线函数的周期也是 $2\pi i$
零点为:
$$
\cosh{z}=0, if\space z=(\frac{\pi}{2} + n\pi), n=0,\plusmn1,\plusmn2,\dotsi \\
\sinh{z}=0, if\space z=n\pi i, n=0,\plusmn1, \plusmn2, \dotsi
$$

$$
\tanh{z} = \frac{e^z - e^{-z}}{e^z + e^{-z}} \\
sech z = \frac{2}{e^z + e^{-z}} \\
csch z = \frac{2}{e^z - e^{-z}} \\
$$
With the analogous identities
$$
1- \tanh^2 z = sech^2z \\
\tanh(z\plusmn w) = \frac{\tanh{z}\plusmn \tanh w}{1\plusmn \tanh{z}\tanh{w}}
$$
反函数
$$
\cosh^{-1}z = \ln{(z + \sqrt{z^2 - 1})} \\
\sinh^{-1}z = \ln{(z + \sqrt{z^2 + 1})} \\
\tanh^{-1}z = \frac{1}{2}\ln{(\frac{1+z}{1-z})} \\
$$

**Complex Exponents ,复指数**
$f(z)=z^{\alpha}$, $\alpha$是一个复数,$f(z)=z^\alpha=e^{\alpha\ln{z}}$
$$
f(z)^{g(z)}=e^{g(z)\ln[f(z)]}
$$
从定义来看，复数$z$的幂是多值函数,

例子: 求$i^i$的值
Solution:
先求$\ln{i}$
$$
\begin{aligned}
    \ln{i}&=\ln{(1\cdot e^{i\pi/2})} \\
    &= \ln{1} + i(\frac{\pi}{2} + 2n\pi) \\
    &=  i(\frac{\pi}{2} + 2n\pi), \space n=0,\plusmn1,\plusmn2,\dotsi \\
\end{aligned}
$$
再代入
$$
\begin{aligned}
i^i &= e^{(i\ln{i})}  \\
    &= e^{i[\frac{\pi}{2} + 2n\pi]} \\
    &= e^{-(\frac{\pi}{2} + 2n\pi)}, \space n=0,\plusmn1,\plusmn2,\dotsi \\
\end{aligned}
$$
$i^i$的值都是实数,奇怪的是, 

**初等函数求导**
指数函数, exponential function,
$$
\frac{d}{dz}e^z = e^z
$$
多项式函数
$$
\frac{df}{dz}= a_1 + 2a_2z + 3a_3z^2 + \dotsi + na_nz^{n-1}
$$
对数函数
$$
\ln{z} = \ln{r} + i\theta,
$$
$\theta$限制在域$\alpha \le \theta \le \alpha + 2\pi$,这样我们就有了一个单值函数，实部、虚部为
$$
u=\ln{r}, v=\theta,
$$
该函数满足Cauchy-Riemann方程,
$$
f'(z)=e^{-i\theta}(\frac{\partial u}{\partial r} + i\frac{\partial v}{\partial r})
$$
因此我们得到
$$
\frac{d}{dz}\ln{z}=e^{-i\theta}(\frac{\partial u}{\partial r} + i\frac{\partial v}{\partial r})=e^{-i\theta}(\frac{1}{r}+i0)=\frac{1}{re^{i\theta}}
$$
所以于实数的情况相同,
$$
\frac{d}{dz}\ln{z}=\frac{1}{z}
$$
when $|z| \gt 0$, and $\alpha \lt \arg{z} \lt \alpha + 2\pi$
三角函数的导数
$$
\cos{z}=\cos(x+iy)=\cos{x}\cosh{y}-i\sin{x}\sinh{y} 
$$
对$u$,$v$求偏导
$$
\frac{\partial u}{\partial x} = -\sin{x}\cosh{y} \\[0.5em]
\frac{\partial u}{\partial y} = \cos{x}\sinh{y}  \\[0.5em]
\frac{\partial v}{\partial x} = -\cos{x}\sinh{y} \\[0.5em]
\frac{\partial v}{\partial y} = -\sin{x}\cosh{y} \\[0.5em]
$$
从中看出
$$
\frac{\partial u}{\partial x} = \frac{\partial v}{\partial y} \\[0.5em]
\frac{\partial u}{\partial y} = -\frac{\partial v}{\partial x} \\
$$
因此是满足Cauchy-Riemann等式,因此
$$
f'(z) = \frac{\partial u}{\partial x} +i\frac{\partial v}{\partial x} \\
=-\sin{x}\cosh{y} -i\cos{x}\sinh{y}\\
$$
另外我们已经知道$\sin{z}=\sin{x}\cosh{y}+i\cos{x}\sinh{y}$, 则
$$
\frac{d}{dz}\cos{z} = -\sin{z}
$$
对于$sin{z}$, 
$$
\begin{aligned}
\frac{d}{dz}\sin{z}&=\cos{z} \\
\frac{d}{dz}\tan{z}&= \sec^2{z} \\
\frac{d}{dz}\cot{z}&= -\csc^2{z} \\
\frac{d}{dz}\sec{z}&=\sec{z}\tan{z} \\
\frac{d}{dz}\csc{z}&=-\csc{z}\cot{z} \\
\end{aligned}
$$
对双曲函数的求导
$$
\begin{aligned}
\frac{d}{dz}\cosh{z}&=\sinh{z} \\
\frac{d}{dz}\sinh{z}&=\cosh{z} \\
\frac{d}{dz}\tanh{z}&=sech^2{z} \\
\frac{d}{dz}sech{z}&=-sech{z}\tanh{z} \\
\end{aligned}
$$
指数函数的求导
$$
\frac{d}{dz}z^{\alpha} = \alpha z^{\alpha -1}
$$

**Branches**
?一个多值函数，随着$z$在一个圆上的移动，在复平面上运动，周期性重复。在$0 \leqslant \theta \leqslant 2\pi$的范围内，函数是单值的。此时我们称我们在函数的一个branch里，当$\theta$大于$2\pi$时，函数会重复，此时我们说进入了函数的另一个branch. 一个多值函数会这样重复自己，无限重复下去。

branch cut, The point from which the branch cut originates is called a branch point. 函数不能穿过branch cut, 这样我们就可以是复函数称为一个单值函数了。

# chap 5, Sequences and Series
序列和级数, 在实数领域，我们可以用一个实变量的无限级数扩展来表示一个函数。那么对于复函数来说我们也可以把它展成级数。

**sequences**
序列表达为$\lbrace f(n) \rbrace$, or $\lbrace a_n \rbrace$

The limit of a sequence
判断一个序列是否会收敛、逼近一个有限值，当$n$趋于无限值时。其定义为, 给定任何一个正值$\epsilon$,可以找到一个数$N$,使得
$$
|a_n - \ell| \lt \epsilon, \space for \space all \space n \gt N
$$
我们记为
$$
\lim\limits_{n to \infin}a_n = \ell
$$
收敛convergent, 发散divergent,给定序列的极限是唯一的，不可能收敛到多个值。

复函数的序列,
$$
\lim\limits_{n \to \infin}f_n(z) = f(z)
$$
同样定义极限, $|f_n(z) - f(z)| \lt \epsilon$ , for $n \gt N$

**Infinite Series, 无限级数**
将序列的每一项都加起来，我们得到一个级数, partial sums, 
Let $\lbrace a_n(z) \rbrace$ be some complex sequence,我们将partial sums, 写为:部分和，部分总和, 
$$
S_n = a_1(z) + a_2(z)+ a_3(z) + \dotsi + a_n(z) \\
\sum_{n=1}^{\infin}a_n(z)
$$
如果级数的极限存在，那么级数是收敛的。
$$
\lim\limits_{n \to \infin}S_n(z) = S(z)
$$
收敛的一个条件是
$$
\lim\limits_{n \to \infin}a_n(z) = 0
$$
**Convergence 收敛**
复分析里的级数的一个重要概念是radius of convergence, 收敛半径，R。在复平面的哪个区域里面级数收敛。级数只在unit disc里面收敛。我们说。

monotonic increasing, $a_{n+1} \geqslant a_n$, 单调增

monotonic decreasing, $a_{n+1} \leqslant a_n$, 单调递减

The sequence is bounded, $|a_n| < M$, bounded above by some constant $M$

Cauchy's convergence criterion,
So, $\{a_n\}$ converges if given an $\epsilon > 0$, we can find an $N$ such that
$$
|a_m - a_n| \lt \epsilon, \space m,n \gt N
$$

**复级数的收敛**
一种方法是检查级数的实部、虚部的收敛性。$\sum a_j + ib_j$收敛的话,$\sum a_j$和$\sum b_j$两者也都收敛。

$\sum a_n$绝对收敛，converges absolutely, 就是说下式收敛
$$
\sum_{n=1}^{\infin}|a_n|
$$
ratio test, 序列的比例测试
$$
\lim\limits_{n \to \infin}|\frac{a_{n+1}}{a_n}| = R
$$

* 当$R<1$时， 级数绝对收敛
* 当$R>1$时，级数发散

nth root test, 根测试
$$
\lim\limits_{n \to \infin}\sqrt[n]{|a_n|} = R
$$
$R <1$,级数绝对收敛，否则发散

Raabe's test, 
$$
\lim\limits_{n \to \infin} n(1-|\frac{a_{n+1}}{a_n}|) = R
$$
$R < 1$,级数绝对收敛，否则发散

Weierstrass M-test, 
$|a_n(z)| \leqslant M_n$, 如果$M_n$不依赖于$z$, 如果$\sum M_n$收敛，那么$\sum a_n(z)$也收敛。

**Uniformly Converging Series**
一致收敛级数,
在一个域内, for all $z$, of the complex plane, the convergence is uniform. 
$$
|a_n(z) - R| < \epsilon, for \space n > N
$$
一致收敛到$R$

Power Series,幂级数
$$
a_0 + a_1z+a_2z^2 + \dotsi = \sum_{n=0}^{\infin}a_n(z-z_0)^n
$$
$a_n$是常数, 成为幂级数. 当级数收敛时, $|z-z_0|< R$, $R$为收敛半径, radius of convergence. 在复分析中，级数收敛的区域通常是一个disc, 因此术语term, 就有了一个实际的几何意义。

**Taylor and Maclaurin Series**
泰勒和麦克劳林级数,
如$f(z)$在复平面的某个区域里是解析的, analytic, $z_0$作为这个区域里的一个点。$f(z)$可以用幂级数展开, 就是泰勒级数
$$
f(z) = f(z_0) + f'(z_0)(z-z_0) + \frac{f''(z_0)}{2!}(z-z_0)^2 + \dotsi 
    + \frac{f^{n}(z_0)}{n!}(z-z_0)^n + \dotsi
$$
如果$z_0=0$, 那么展开的就是麦克劳林级数

幂级数的原理,

一些常见的级数
$$
e^z = 1+z+\frac{1}{2!}^2 +\dotsi+ \frac{1}{n!}z^n = \sum_{n=0}^{\infin}\frac{1}{n!}z^n\\[0.5em]
\cos{z}=1-\frac{z^2}{2!}+\frac{z^4}{4!}-\frac{z^6}{6!}+\dotsi+\frac{(-1)^n}{(2n)!}z^{2n}=\sum_{n=1}^{\infin}\frac{(-1)^n}{(2n)!}z^{2n}\\[0.5em]
\sin{z}=z-\frac{z^3}{3!}+\frac{z^5}{5!}-\frac{z^7}{7!}+\dotsi+\frac{(-1)^(n-1)}{(2n-1)!}z^{2n-1} = \sum_{n=1}^{\infin}\frac{(-1)^{n-1}}{(2n-1)!}z^{2n-1}\\[0.5em]
\ln{(1+z)}=z-\frac{z^2}{2}+\frac{z^3}{3}+\dotsi+\frac{(-1)^{n-1}}{n}z^n = \sum_{n=1}^{\infin}\frac{(-1)^{n-1}}{n}z^{n}\\[0.5em]
\tan^{-1}z=z-\frac{z^3}{3}+\frac{z^5}{5}-\dotsi+\frac{(-1)^{n-1}}{2n-1}z^{2n-1}=\sum_{n=1}^{\infin}\frac{(-1)^{n-1}}{2n-1}z^{2n-1}\\[0.5em]
$$
If $|r|\lt 1$, then the geometric series converses as,几何级数的收敛值为:
$$
\sum_{n=0}^{\infin}r^n = \frac{1}{1-r}
$$
harmonic series, 调和级数是发散的,
$$
\sum_{n=1}^{\infin}\frac{1}{n}=\infin
$$
然而交替调和级数是收敛的,alternating harmonic series,
$$
\sum_{n=1}^{\infin}\frac{(-1)^{n-1}}{n} = \ln{2}
$$

例子:Bessel function,贝塞尔函数是差分方程的解, 
$$
x^2(\frac{d^2y}{dx^2})+x(\frac{dy}{dx})+(x^2-a^2)y=0
$$
贝塞尔函数的级数表示可以用
$$
J_0(x)=\sum_{n=0}^{\infin}[{\frac{(-1)^n}{(n!)^{2'}}}(\frac{x}{2})^2]
$$
我们可以写为
$$
J_0(x)=\frac{1}{2\pi}\int_{0}^{2\pi}\cos{(x\cos{(\phi)})}d\phi
$$
Solution,推导方式:
$$
\begin{aligned}
J_0(x)=&\frac{1}{2\pi}\int_{0}^{2\pi}\cos{(x\cos{(\phi)})}d\phi\\
=&\frac{1}{2\pi}\int_{0}^{2\pi}\sum_{n=0}^{\infin}\frac{(-1)^n}{(2n)!}(x\cos{\phi})^{2n}d\phi \\
=&\sum_{n=0}^{\infin}\frac{1}{2\pi}\int_{0}^{2\pi}\frac{(-1)^n}{(2n)!}(x\cos{\phi})^{2n}d\phi\\
=&\sum_{n=0}^{\infin}\frac{1}{2\pi}\frac{(-1)^{n}}{(2n)!}x^{2n}\int_{0}^{2\pi}(\cos{\phi})^{2n}d\phi\\
=&\frac{1}{2\pi}\sum_{n=0}^{\infin}\frac{(-1)^{n}}{(2n)!}x^{2n}\int_{0}^{2\pi}(\cos{\phi})^{2n}d\phi\\
\end{aligned}
$$
可以证明，you can verify that
$$
\int_{0}^{2\pi}(\cos{\phi})^{2n}d\phi = \frac{(2n)!}{2^{2n}(n!)^2}2\pi\\
$$
Hence
$$
\begin{aligned}
J_0(x)=&\frac{1}{2\pi}\sum_{n=0}^{\infin}\frac{(-1)^{n}}{(2n)!}x^{2n}\int_{0}^{2\pi}(\cos{\phi})^{2n}d\phi\\
=&\frac{1}{2\pi}\sum_{n=0}^{\infin}\frac{(-1)^{n}}{(2n)!}x^{2n}\frac{(2n)!}{2^{2n}(n!)^2}2\pi\\
=&\sum_{n=0}^{\infin}\frac{(-1)^{n}}{(n!)^2}(\frac{x}{2})^{2n}\\
=&J_0(x)\\
\end{aligned}
$$

**Laurent Series**
劳伦级数, 表示一个复变函数$f(z)$,与泰勒级数相比，劳伦级数包括的项具有负幂部分。
$$
f(z)=\sum_{n=-\infin}^{\infin}a_n(z-z_0)^n
$$
劳伦级数的系数,使用Cauchy's integral formula, 柯西的积分公式,
$$
a_n=\frac{1}{2\pi i}\oint\frac{f(z)}{(z-z_0)^{n+1}}dz, for\space n=0,1,2,\dotsi
$$
annulus, 环空，环带,
Laurent series可以写为
$$
f(z)=a_0 + a_1(z-z_0) + a_2(z-z)^2+ \dotsi + \frac{a_{-1}}{z-z_0} + \frac{a_{-2}}{(z-z_0)^2}+\dotsi
$$
colloquially,口语地说，通俗地说，奇点说明这个点不可微分,
analytic part of the series, 级数的解析部分，是展开部分,

**奇点的种类**
quintessential example, 典型的例子, 奇点会导致函数blow up, 但是函数的极限是存在的。典型的例子是$f(z)=(\sin{z})/z$, f(0)不存在，无定义。然而$\lim\limits_{z \to z_0}f(z)=1$, 极限是存在的。如果你能够理解这一点的话，你就可以理解removable singularity的概念。

假定劳伦级数有有限个项
$$
\frac{a_{-1}}{z-z_0}+\frac{a_{-2}}{(z-z_0)^2}+\dotsi+\frac{a_{-n}}{(z-z_0)^n}
$$
$z=z_0$叫做极点，阶为n，n阶极点, 极点会造成函数无限大, 如果$a_{-1}$是唯一的不为零的系数，我们说$z=z_0$是一个简单极点，simple pole,

essential singularity, 本质极点, 有限数个负幂项，在Laurent扩展里面, 

branch point $z=z_0$, 是一个多值函数的点，当曲线卷过$z_0$时，函数值会变化,

A singularity at infinity is a zero of $f(z)$ if we let $z=1/w$ and consider the Function $F(w)=f(1/z)$

**Entire Functions**
整函数, 在复平面上都是解析的, analytic的函数, 整函数可以泰勒展开，收敛半径是有限的。

**Meromorphic Functions**
亚纯函数在复平面上处处解析，除了有限数目的极点外。







