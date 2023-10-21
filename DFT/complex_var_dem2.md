# chap 8 More complex integration and the laplace transform
更复杂的积分和拉普拉斯变换

使用留数定理解决更复杂的积分问题，还会讨论一下拉普拉斯变换。


**Fesnel Integrals**
菲涅尔积分,
$$
\int_0^{\infin}\cos{(t^2)}dt =\int_0^{\infin}\sin{(t^2)}dt=\frac{\sqrt{\pi}}{2\sqrt{2}}
$$
考虑analytic funciton, 解析函数, $f(z)=e^{-z^2}$
$$
\int_{C}e^{-z^2}dz=2\pi i\sum{residues}
$$
显然等于零，因为没有pole,
我们将曲线积分，分成3个部分,并将z表示为$z=re^{i\theta}$, at $r=R$, and $dz=dr(e^i\theta) + ire^{i\theta}d\theta$

**Laplace Transform**
拉普拉斯变换
变换的数学方法，带来很多计算的简化，比如解微分方程，转换为代数方程, 第一个讨论的变换就是。

拉普拉斯变换可以将一个时域的函数转换为一个复数变量$s$的函数。这个级数非常有用，可以将一般的微分方程转换为容易解决的代数方程。
复变量$s$
$$
s=\sigma + iw
$$
变换
$$
F(s)=\int_{-\infin}^{\infin}f(t)e^{-st}dt
$$
实际上通讯里的傅里叶变换可以用拉普拉斯变换来代替的,
$ F(s)= L{f(t)} $

Example, $f(t)=\theta(t)$, where
$$
\theta(t)=\begin{cases}
    1, t \geqslant 0 \\
    0, t \leqslant 0 \\
\end{cases}
$$
Solution:
解：
$$
F(s)=\int_{0}^{\infin}e^{-st}=-\frac{1}{s}e^{-st}|_0^{\infin}=\frac{1}{s}
$$
Therefore we have the Laplace transform pair
$$
L\{\theta(t)\}=\frac{1}{s}
$$

Example, $f(t)=e^{-at}u(t)$
$$
L\{e^{-at}\theta(t)\}=\frac{1}{s+a}
$$

Example, $f(t)=te^{-at}\theta(t)$
Solution:
$$
F(s)=\int_{0}^{\infin}te^{-at}e^{-st}dt=\int_{0}^{\infin}te^{-(a+s)t}dt
$$
回顾, recalling the integration by parts formula,
$$
\int udv = uv - \int vdu
$$
In the case at hand, we set
$$
u=t, \rArr du=dt \\
dv=e^{-(a+s)t}dt, \rArr v=-\frac{1}{s+a}e^{-(s+a)t} \\
$$
Therefore, applying the integration by parts formula we obtain,
$$
F(s)=-\frac{1}{s+a}te^{-(s+a)t}|_0^{\infin} + \frac{1}{s+a}\int_0^{\infin}e^{-(s+a)t}dt
$$
前一项为零，则
$$
F(s)= -\frac{1}{(s+a)^2}e^{-(s+a)t}|_0^{\infin} = \frac{1}{(s+a)^2}
$$

Example, Let $\alpha > -1$, The factorial function is defined by $\alpha! = \int_0^{\infin}e^{-t}t^{\alpha}dt$
Find (-1/2)!, show the Laplace transform of $t^{\beta}$ is given by $\beta!/s^{\beta + 1}$
Solution:
we have
$$
(\frac{1}{2})!= \int_0^{\infin}e^{-t}t^{-\frac{1}{2}}dt\\
$$
Let $\sqrt{t}=x$, then $dx=\frac{1}{2\sqrt{t}}dt$, $t=x^2$, and
$$
(\frac{1}{2})!=2\int_0^{\infin}e^{-x^2}dx = 2(\frac{1}{2})\int_{-\infin}^{\infin}e^{-x^2}dx=\sqrt{\pi}
$$
$t^{\beta}$的拉普拉斯变换是
$$
\int_{0}^{\infin}e^{-st}t^{\beta}dt
$$
Let $r=st$, then $dr=sdt$, $t=r/s$ , $\rArr$
$$
\int_{0}^{\infin}e^{-st}t^{\beta}dt=\int_{0}^{\infin}e^{-r}(\frac{r}{s})^{\beta}\frac{dr}{s} = \frac{1}{s^{\beta+1}}\int_0^{\infin}e^{-r}r^{\beta}dr=\frac{(\beta)!}{s^{\beta + 1}}
$$
得证。精彩

**拉普拉斯变换的重要性质**
拉普拉斯变换是一个线性变换, 
$$
L\{ \alpha f_1(t) + \beta f_2(t) \} = \alpha F_1(s) + \beta F_2(s)
$$
time scaling, 
$$
L\{ f(at) \} = \frac{1}{a}F(\frac{s}{a})
$$
time shifting,
$$
L\{ f(t - t_0)\}=e^{-st_0}F(s)
$$
拉普拉斯的微分
$$
L\{\frac{df}{dt} \}=\int_0^{\infin}\frac{df}{dt}e^{-st}dt=f(t)e^{-st}|_0^{\infin} + s\int_0^{\infin}f(t)e^{-st}dt \\
=-f(0) + sF(s) \\
$$
$$
\frac{d}{ds}[F(s)]=\int_{-\infin}^{\infin}\frac{d}{ds}[f(t)e^{-st}]dt=-\int_{-\infin}^{\infin}tf(t)e^{-st}dt \\[0.5em]
-\frac{dF}{ds}=\int_{-\infin}^{\infin}tf(t)e^{-st}dt \\
$$
So 微分
$$
L\{ tf(t) \} = -\frac{dF}{ds}
$$

Example , 已知
$$
L\{ \cos{(\beta t)} u(t) \}=\frac{s}{s^2 + \beta^{2}}
$$
求 $t\cos{(\beta t)} u(t)$的变换,
Solution:
First we recall the derivative of a quotient is given by
$$
(\frac{f}{g})'=\frac{f'g -g'f}{g^2}
$$
利用上面的定理,
$$
\frac{d}{ds}=\frac{(s^2+\beta^2)-2s(s)}{(s^2+\beta^2)^2}=\frac{\beta^2 - s^2}{(s^2+\beta^2)^2} \\
$$
加一个负号即为所求

$$
L\{u(t)\} = \frac{1}{s}\\
$$

**Abel's integral**
阿贝尔积分， 
$$
f(x)=\int_0^{x}\frac{\phi(t)}{\sqrt{x-t}}dt
$$

**The Bromvich Inversion Integral**
The inverse Laplace transform , $g(t)=e^{-ct}f(t)$, $c$ is a real constant. Using Fourier transforms:
$$
\begin{aligned}
    g(t)&=\int_{-\infin}^{\infin}e^{iwt}G(w)dw\\[0.5em]
    &=\int_{-\infin}^{\infin}e^{iwt}(\frac{1}{2\pi}\int_{-\infin}^{\infin}e^{-iw\tau}g(\tau)d\tau)dw\\[0.5em]
\end{aligned}
$$
$$
f(t)=\frac{1}{2\pi i}\int_{c-i\infin}^{c+i\infin}e^{zt}F(z)dz\\
$$
Bromvich contour, 是一条沿着y轴方向从$c-iR$到$c+iR$的直线，we let $R \to \infin$

Example, $F(s)=1/(s^2+w^2)$的反变换
$$
f(t)=\frac{\sin{wt}}{w}
$$

# chap 9 Mapping and Transformations
一些数学技巧，将复平面的一部分区域转换为另一个不同的区域。成为映射, mapping.
**Linear Transformations**
$w = \alpha z + \beta$
$\alpha, \beta$ 都是复常量, 
设$\alpha = ae^{i\phi}$, $z=re^{i\theta}$, 则
$$
w=\alpha z=(ae^{i\phi})(re^{i\theta})=are^{i(\phi+\theta)}
$$
如果$a>1$, transformation expands the radius vector of z , 
如果$a<1$, transformation contracts the radius vector, 
The transformation rotates the point $z$ by an angle $\phi = arg(\alpha)$
$w$ plane is defined by the coordinate $w=u+iv$

Example, 
Explain what the transformation $w=iz$ does to the line $y=x+2$ in the $x-y$ plane.
Solution:
$w = iz=i(x+iy)= -y + ix$
So we have the relations
$$
u = -y \\
v = x \\
$$
The line is transformed to
$$
y=x+2 \rArr -u = v+2, \\
v=-u-2 \\
$$

**The transformation $z^n$**

**Conformal Mapping**
共形映射，保形映射, 
Let $C_1$和$C_2$ be two curves in the $z$ plane. Suppose that a given trnasformation $w$ maps these curves to curves $C_1', C_2'$ in the $w$ plane. Let $\theta$ be the angle between the curves $C_1$ and $C_2$ and $\phi$ be the angle between curves $C_1'$ and $C_2'$. If $\theta = \phi$ in both magnitude and sense, we say that the mapping is conformal. Put another way, a conformal mapping preserves angles. There is an important theorem related to conformal mappings.

Suppose that $f(z)$ is analytic and that $f'(z) \not = 0$ in some region $R$ of the complex plane. It follows the mapping $w=f(z)$ is conformal at all points of $R$.

**The Mapping $1/z$**
Consider the transformation $w=1/z$, 
$$
w=\frac{1}{z}=\frac{\overline{z}}{z\overline{z}}=\frac{x-iy}{(x+iy)(x-iy)}=\frac{x}{x^2+y^2}-i\frac{y}{x^2+y^2}\\
$$
we also can get the coordinates in the $z$ plane related to $w$ plane
$$
x=\frac{u}{u^2+v^2},\space y=-\frac{v}{u^2+v^2}
$$
因此$1/z$映射
* Transform lines in the $z$ plane to lines in the $w$ plane
* Transform circles to circles in $w$ plane
* Circle 不穿过原点的，映射后也不穿过原点
* Circle穿过原点的，映射成一条直线不穿过原点
* line 不穿过原点的，映射为穿过原点的一个circle
* line 穿过原点的，映射为穿过原点的一条直线

假设一条线为$z=re^{ia}$穿过零点, 通过映射$w=1/z=1/r e^{-ia},$

**Mapping of Infinite Strips**
一些重要的转换可以将无限长带状区域，映射为$w$ plane 的上半平面。
Consider the transformation $w=e^z$

**Rules of Thumb**

**Mobius Transformations**
$$
T_z=\frac{az+b}{cz+d}, \space ad-bc\not = 0 \\
$$
bilinear transformation, fractional transformation, Mobius transformation. 双线性变换,

* Dilation, linear transformation $az$
* Translation, $z+b$
* Reciprocation, $1/z$

将圆变换成圆，将直线变换成直线,

Now suppose that $a_0,z_1,z_2$and $z_3$ are four distinct points in the complex plane. The cross ratio is given by
$$
\frac{(z_3 - z_0)(z_1 - z_2)}{(z_1 - z_0)(z_3 - z_2)}
$$
在一个mobius tansformation中，cross ratio是不会变的,

Let $a$ be a complex number with $|a| < 1$ and suppose that $|k|=1$, then
$$
w=k\frac{z-a}{1-\overline{a}z}
$$
maps the unit disk from the $z$ plane to the unit disk in the $w$ plane. Now let $a$ be a complex number with the requirement that $Im(a)>0$, The transformation
$$
w=k\frac{z-a}{z-\overline{z}}
$$
maps the upper half of the $z$ plane to the unit disk in the $w$ plane. Notice that when $z$ is purely real, $|w|=|k|=1$

Example:

# chap 10 The Schwarz-Christoffel Transformation,
施瓦茨-克里斯托弗 变换, 这种变换将一个simple closed polygon 映射到上半平面。通常用于fluid dynamics, electrostatics.

**Riemann mapping Theorem**
莱曼映射定理,
To map a region $R$ of the $z$ plane to a region $R'$ of the $w$ plane. Let $w=f(z)$ be an analytic function in $R$ and let $R$ be enclosed by a simple closed curve $C$.  Suppose that the region $R'$ is the unit disk at the origin bounded by the unit circle $C'$, that is a circle with radius $|w|=1$.

Riemann映射原理说这个函数w=f(z)存在，且区域R里的每一个点都能映射到区域R'里。
If $z_0 \in R$ with $f(z_0)=0$ and $f'(z)>0$ then the mapping $w=f(z)$ is unique.

施瓦茨-克里斯托弗变换映射
* 多边形的内部映射到上半平面
* 多边形的边界映射到实轴

我们这里做一个启发性的解释, 这些讨论基于Levinson, Redheffer的贡献。
We can also assume the existence of an inverse mapping, which we denote by $z=g(w)$.
边界的顶点映射到实轴$x$ axis, denoted by: $x_1, x_2, x_3,\dotsi, x_n$
Now, since $w=f(z)$, it follows that
$$
dw=f'(z)dz
$$
Next we assume that the mapping and its inverse $w=f(z)$, $z=g(w)$ are analytic on the sides of the polygon in addition to its interior. Picking a point $w$ on the polygon which is not a vertex, the image of $w$ is a point $z$. The point $dz$ is a positive vector on the real axis $x$.

$dw$ is a vector on the edge of the polygon pointing in the positive sense(in the counterclockwise direction).

The arguments of $f'$ and $w'$ are then related in the following way:
$$
arg[f'(z)]=arg(\frac{dw}{dz})
$$
Now imagine moving the point $w$ around the polygon and moving the image point $z$ in the positive direction along the $x$ axis. Each time a point $w$ moves past a vertex of angle $\alpha_1\pi$, the arguemnt changes as $\pi(1-\alpha_1)$. But $arg(dz)=0$. Therefoer, to the left of the point $x_1$, $arg[f'(z)]$ is a constant, but at the point $x_1$ it will change by $\pi(1-\alpha_1)$ to maintain Eq. 

As $z$ moves from $x<x_1$ to $x>x_1$, $arg[(z-x_1)]$ decreases from $\pi$ to $0$. This means that the argument of $(z-x_1)^{\alpha_1 -1}$ is changed by $\pi(1-\alpha_1)$. This change will occur at every vertex. So we choose
$$
f'(z)=A(z-x_1)^{\alpha_1/\pi -1}(z-x_2)^{\alpha_2/\pi-1}...(z-x_n)^{\alpha_n/\pi -1}
$$
Then, 
$$
\frac{dw}{dz}=A(z-x_1)^{\alpha_1/\pi -1}(z-x_2)^{\alpha_2/\pi-1}...(z-x_n)^{\alpha_n/\pi -1}
$$
Integrating, we obtain the form $w=f(z)$
$$
w=A\int (z-x_1)^{\alpha_1/\pi -1}(z-x_2)^{\alpha_2/\pi-1}...(z-x_n)^{\alpha_n/\pi -1} dz + B
$$
The constant $A$ and $B$ are in general complex that indicate the orientation, size, and location of the pentagon in the $w$ plane. 

example,
Find the image in the upper half plane using the transformation
$$
w=\int_0^{z}\frac{1}{\sqrt{(1-t^2)(1-k^2t^2)}}dt
$$
when $0<k<1$

Let's rewrite the integral in a more suggestive form:
$$
w=\int_0^{z}(1-t^2)^{-\frac{1}{2}}(1-k^2t^2)^{-\frac{1}{2}}dt
$$
Each angle is increased by $\pi/2$ at each vertex. The polygon described by this is a rectangle. 

这里书上讲得实在是不清楚!?

# chap 11 The Gamma and Zeta functions
复分析的两个重要函数, gamma and zeta functions.

**The Gamma Function**
When $Re(z)>0$ 
$$
\Gamma(z)=\int_0^{\infin}t^{z-1}e^{-t}dt\\
$$
We can show that it is convergent in the right-handl plane by examining its behavior at $t=0$ and as $t \to \infin$. Using $|z| \leqslant Re(z)$, we have
$$
|t^{z-1}e^{-t}| \leqslant t^{Re(z)-1}
$$
It's finite at $t=0$. As $t \to \infin$, note that we have
$$
|t^{z-1}e^{-t}| \leqslant t^{Re(z)-1}e^{-t} \leqslant e^{-t/2}
$$
This shows that the integral is convergent for larget $t$. If $n$ is a positive integer, then 
$$
\Gamma(n+1)=n(n-1)\dotsi1=n!\\
$$
This follows from the recursion relation for the gamma function, which holds for any $z$(not just integers)
$$
\Gamma(z+1)=z\Gamma(z)
$$

Example,
The alternative definition of the gamma function is given by
$$
\Gamma(z)=2\int_0^{\infin}x^{2z-1}e^{-x^2}dx \\
$$

**Evaluating $\Gamma(z)$ when $0<z<1$**
It is given as a definition in most texts that
$$
\Gamma(\frac{1}{2})=\sqrt{\pi}
$$
$$
\Gamma(z)\Gamma(1-z)=\frac{\pi}{\sin{\pi z}}
$$

**$\Gamma$ function properties**
$$
\Gamma(z)=\frac{\Gamma(z+n+1)}{z(z+1)(z+2)\dotsi(z+n)}
$$
meromorphic function? 亚纯函数
Euler's constant
$$
\gamma = \lim\limits_{p\to \infin}\{ 1+\frac{1}{2}+\frac{1}{3}+\dotsi +\frac{1}{p} - \ln{p} \}=0.5772157\dotsi
$$

Using Euler's constant, we can write down an infinite product representation of the gamma function,
$$
\frac{1}{\Gamma(z)}=ze^{\gamma z}\prod_{k=1}^{\infin}\big( 1+\frac{z}{k} \big)e^{-\frac{z}{k}}
$$
Using Gauss's $\Pi$ function $\Pi(z,k)$
$$
\Pi{(z,k)}=\frac{1\cdot 2\cdot 3 \dotsi k}{(z+1)(z+2)(z+3)\dotsi(z+k)}k^z
$$
The gamma function can be written as
$$
\Gamma(z+1)=\lim\limits_{k \to \infin}\Pi{(z,k)}
$$
The duplication formula tells us that
$$
2^{2z-1}\Gamma(z)\Gamma(z + \frac{1}{2})=\sqrt{\pi}\Gamma(2z)
$$

Example,
Show that
$$
\Gamma(z)=\frac{\Gamma(z+n+1)}{z(z+1)(z+2)\dotsi(z+n)}
$$

Example,
Show that the gamma function is analytic on the right half plane.
Consider,
$$
\Gamma_{\epsilon}(z)=\int_{\epsilon}^{1/\epsilon}t^{z-1}e^{-t}dt
$$
The gamma function is the only meromorphic function which has the following three properties:
* $\Gamma(z+1)=z\Gamma(z)$
* $\Gamma(1)=1$
* $log(\Gamma(x))$ is convex
convex - 凸面的?

Example:
Show that the gamma function is logarithmically convex on the real axis.
$$
\frac{1}{\Gamma{(z)}}=ze^{\gamma z}\prod_{k=1}^{\infin}(1+\frac{z}{k})e^{-z/k}
$$
We take logarithm on both sides:
$$
\log{\frac{1}{\Gamma(z)}}=\log{z}+\gamma z + \sum_{k=1}^{\infin}\{ \log{(1+\frac{z}{k})} - (\frac{z}{k}) \}\\[0.5em]
\log{\Gamma(z)}=-\log{z}-\gamma z - \sum_{k=1}^{\infin}\log(1+\frac{z}{k})+\sum_{k=1}^{\infin}(\frac{z}{k})\\
$$
Therefore
$$
\frac{\partial}{\partial z}\log(\Gamma(z))=-\frac{1}{z}-\gamma+\sum_{k=1}^{\infin}(\frac{1}{k})(\frac{z}{z+k})
$$
Computing the second derivative we find
$$
\frac{\partial^2}{\partial z^2}\log{\Gamma(z)}=\frac{1}{z^2}+\sum_{k=1}^{\infin}\frac{1}{(z+k)^2}
$$
Evaluating this for real argument,
这里我有些不明白了，可以直接把x代进入替换z吗?

**Contour Integral Representation**
We close by noting that the gamma function can be written as
$$
\frac{1}{\Gamma(z)}=\frac{1}{2\pi i}\oint \frac{e^t}{t^z}dt\\
$$

**Stirling Formula**
Stirling approximation, for the gamma function,
$$
\Gamma(z+1) \approx \sqrt{2\pi}e^{-z}z^{z+\frac{1}{2}}
$$

**Beta Function**
$Re(m)>0$and $Re(n)>0$
$$
B(m,n)=\int_{0}^{1}t^{m-1}(1-t)^{n-1}dt
$$
By using the substitution $t=\sin^2\theta$ , we can move to polar coordinates and write the beta function in terms of trigonometric functions.
$$
dt=2\sin{\theta}\cos{\theta}d\theta\\
$$
We have
$$
\begin{aligned}
B(m,n)&=\int_0^1t^{m-1}(1-t)^{n-1}dt \\
&=\int_0^{\pi/2}(\sin^2\theta)^{m-1}(\cos^2\theta)^{n-1}2\sin{\theta}\cos{\theta}d\theta\\
&=2\int_{0}^{\pi/2}(\sin^2{\theta})^{2m-1}(\cos^2{\theta})^{2n-1}d\theta\\
\end{aligned}
$$
The beta function is related to the gamma function via
$$
B(m,n)=\frac{\Gamma(m)\Gamma(n)}{\Gamma(m+n)}
$$
Furthermore, we can write
$$
B(p,1-p)=\int_0^{\infin}\frac{t^{p-1}}{1+t}dt=\Gamma(p)\Gamma(p-1)=\frac{\pi}{\sin{p\pi}}
$$
Provided that $0<Re(p)<1$

**The Riemann Zeta Function**
Riemann在研究数论的时候找到的zeta函数
$$
\zeta(z)=\frac{1}{1^z}+\frac{1}{2^z}+\frac{1}{3^z}+\dotsi=\sum_{k=1}^{\infin}\frac{1}{k^z}\\
$$
Notice we can write
$$
\zeta(z)=\sum_{k=1}^{\infin}\frac{1}{k^z}=\sum_{k=1}^{\infin}\frac{1}{e^{ln(k^z)}}=\sum_{k=1}^{\infin}e^{-z\ln{k}}
$$
Be defined in terms of gamma function
$$
\zeta(z)=\frac{1}{\Gamma(z)}\int_0^{\infin}\frac{t^{z-1}}{e^t + 1}dt\\
$$
Another way
$$
\zeta(1-z)=2^{1-z}\pi^{-z}\Gamma{(z)}\cos{(\frac{\pi z}{2})}\zeta(z)\\
$$
所有的零点都在$Re(z)=1/2$上, 
$$
\frac{1}{\zeta(z)}=(1-\frac{1}{2^z})(1-\frac{1}{3^z})(1-\frac{1}{5^z})\dotsi = \prod_{p}(1-\frac{1}{p^z})
$$
Interesting ,mysterous feature, the product is taken over all positive primes $p$.

# chap 12 Boundary Value Problems
复分析可以用来解偏微分方程, Dirichlet problems, Neumann problem, 

Harmonic functions, 满足下列形式的，in a region $R$ of the $x-y$ plane,
$$
\nabla^2\phi=\frac{\partial^2 \phi}{\partial x^2}+\frac{\partial^2\phi}{\partial y^2}=0\\
$$
如果一个复函数在区域$R$内是analytic的，那么$u(x,y),v(x,y)$都是harmonic functions. 而且它们为共轭。
$$
\frac{\partial^2 u}{\partial r^2}+\frac{1}{r}\frac{\partial u}{\partial r}+\frac{1}{r^2}\frac{\partial^2 u}{\partial \theta^2}=0
$$

使用保形映射来接边界值问题,
First, we state Poisson's formulas, which give the solutions to the Dirichlet problem on the unit disk and for the upper half plane.

1. Let $C$ be the unit circle and $R$ be its interior. 假定$f(r,\theta)$ is harmonic in $R$ and that it assumes the value $g(\theta)$ on the curve $C$. That is , $f(1,\theta)=g(\theta)$. Then the solution to Laplace's equation on the unit disk is given by Poisson's formula for a circle which states that
$$
f(r,\theta)=\frac{1}{2\pi}\int_0^{2\pi}\frac{(1-r^2)g(\phi)}{1-2r\cos{(\theta-\phi)}+r^2}d\phi
$$
Next we consider a function $f(x,y)$, which is harmonic in the upper half plane $y>0$ and assumes the value $f(x,y)=g(x)$ on the boundary, which in this case is the $x$ axis, that is $-\infin < x < \infin$. the solution to Laplace's equation for the upper half plane is given by
$$
f(x,y)=\frac{1}{\pi}\int_{-\infin}^{\infin}\frac{yg(s)}{y^2+(x-s)^2}ds\\
$$
We call it Poisson's formula for the half plane.

The idea is to map the region $R$ to the unit disk or to the half plane. The mapping function that we use must be analytic. There are three stesp involved in obtaining a solution:
* Use a conformal transformation to map the boundary value problem for a region $R$ to a boundar value problem on the unit disk or half plane,
* Solve the problem using above eq.
* Find the inverse of the solution to write down the solution in the region $R$

Remember that a simply connected region is one that includes no sigularities. While the mapping of the region $R$ to region $R'$ in the $w$ plane must be conformal, the mapping of the boundary does not have to be conformal.

Three theorems are useful for solving these types of problems. 




