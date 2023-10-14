# Pre-calculus,

**参考书**:
>precalculus mathematics for calculus 5th edition
Complex variable demystified
Schaum's outlines complex variable
complex variable and applications
Mathematics of the discrete fourier transform, 这是最终要finish的书
Mathematics in the Modern World,
Mathematics in the real world,



conceptual understanding ,technical skills, in modeling the real-world,
yard, 码， 3英尺，0.9米，
=> implies
<=> is equivalent to,
vignettes, 简介
natural numbers, 自然数,
integers, 整数，
rational numbers, $r=m/n$
irrational numbers, $\sqrt{3}, \pi,$ 
real numbers,
* communicative properties, 交换律
* associative properties, 结合律
* distributive properties, 分配率, 乘法和加法
  
real line, 实数轴,
sets, 
elements,
set-builder notations,
$$
A = \{x | x is an integer and 0 < x < 7\}
$$
union, $S \cup T$
intersection, $S \cap T$
empty set, $\varnothing$
intervals, certain sets of real numbers, 
open interval, $(a,b) = \{ x| a \lt x \lt b \}$
closed interval, $[a,b] = \{ x| a \leqslant x \leqslant b \}$
absolute value, $|a|$
distance, $d(a,b) = |b-a|$

需要往多维的方向去考虑问题，在理解单维的基础上,

integer exponents, $a^n = a\cdot a \cdot a \cdot a \dotsi$
square root of $\sqrt{a} = b$
principal nth root, $\sqrt[n]{b}$
rational exponents, $(a^{1/n})^n = 1, a^{m/n} = (\sqrt[n]a)^m$
if $n$ is even, we require that $a \geqslant 0$
rationalizing the denominator, 分母有理化,
algebraic expressions, 
monomial, 单项式 , $ax^k$
binomial, sum of 2 monomials, 
trinomial, sum of 3 monomials,
polynomial, 多项式, $a_nx^n + a_{n-1}x^{n-1} + \dotsi + a_1x + a_0$
degree $n$
terms of the polynomial,
special product formulas
$$
(A+B)(A-B)=A^2 - B^2\hspace{50cm} \\
(A+B)^2 = A^2 + 2AB + B^2 \hspace{{50cm}} \\
(A-B)^2 = A^2 - 2AB + B^2 \hspace{{50cm}} \\
% Cube of sum
(A+B)^3 = A^3 + 3A^2B + 3AB^2 + B^3 \hspace{{50cm}} \\
% Cube of difference
(A-B)^3 = A^3 - 3A^2B + 3AB^2 - B^3 \hspace{{50cm}} \\
A^3-B^3=(A-B)(A^2 + AB + B^2) \hspace{{50cm}} \\
A^3+B^3=(A+B)(A^2 - AB + B^2) \hspace{{50cm}} \\
$$
factoring, 分解因式

查找式子的模式的相同之处,

rational expressions, 
domain of an Algebraic Expression, 定义域,
simplifying rational expressions,
equations, 方程
linear equations, $ax+b=0$
quadratic equation, $ax^2 + bx +c = 0$
quadratic formula
$$
x=\frac{-b \pm \sqrt{b^2 - 4ac}}{2a}
$$
Discriminant, $D= b^2 - 4ac$
modeling with equations:
* identify the variable
* express all unknown quantities in terms of variable
* setup the model
* solve the equation and check your answer

inequalities, 不等式
linear inequalities
nonlinear inequalities,
quadratic inequalities,
coordinate geometry, 坐标几何，解析几何?
coordinate plane, cartesian plane, 
distance formula
$$
d(A,B) = \sqrt{|x_2-x_1|^2 + |y_2-y_1|^2}
$$

对称是一个很基本的公式

midpoint formula, $A(x_1,y_1), B(x_2, y_2)$
$$
(\frac{x_1 +x_2}{2}, \frac{y_1+y_2}{2})
$$
graphs of equations in two variables,
intercepts, x-intercepts, y-intercepts
circles, $C(h,k)$, $d(P,C)=r$
$$
(x-h)^2 + (y-k)^2 = r^2
$$
symmetry with respect to the $x-axis$
symmetry with respect to the $y-axis$
symmetry with respect to the origin
graphing calculator
lines,
slope of line, $slope = rise/run$
perpendicular lines,
modeling variation,
direct variation, $y=kx$, varies directly as x, y is directly proportional to x, y is proportional to x, $k$ is the constant of proportionality
inverse variation, $y=k/x$
joint variaion, $z=kxy$

理解问题的方法:
* What is unknown?
* What are the given quantities
* What are the given conditions

draw a diagram
introduce suitable notation

思考一个计划
* try to recognize something familiar
* try to recognize patterns
* use analogy, 
* introduce something extra
* take cases, 化为子问题
* work backward, 
* establish subgoals
* indirect reasoning, proof by contradiction, 
* mathematical induction, 数学的推导

Carry out the plan
Look back, 总结一下解题过程,

# 2 function
函数
square fucntion, $f(x) = x^2$
a piecewise defined function, 
Domain of a function, 
Four ways to represent a function:
* verbally, description in words
* algebraically, by an explicit formula
* visually, by a graph
* numerically, by a table of values

function types:
linear functions: $f(x) = ax +b $
power functions: $f(x) = x^n$
root functions: $f(x) = \sqrt[n]x$
reciprocal functions: $f(x) = 1/x^n$
absolute value functions: $f(x)=|x|$
greatest integer functions: $f(x)=\llbracket x \rrbracket$

increasing function
decreasing function
even function: $f(-x)=f(x)$
odd function: $f(-x)=-f(x)$
quadratic functions: $f(x)=ax^2 + bx +c$, 图像是parabola, 
If a > 0, then minumum value is $f(-\frac{b}{2a})$
If a < 0, then maximum value is $f(-\frac{b}{2a})$

modeling with functions,
combining functions:
sums,differences, products, quotients
algebra of functions
$$
(f+g)(x) = f(x) + g(x) , Domain A \cap B \\
(f-g)(x) = f(x) - g(x) , Domain A \cap B \\
(fg)(x) = f(x)g(x), Domain A \cap B \\[0.5em]
(\frac{f}{g})(x) = \frac{f(x)}{g(x)}, Domain \{ x \in A \cap B | g(x) \not = 0\}\\
$$
composition of functions, $(f \circ g)(x)=f(g(x))$
one-to-one function, $f(x_1) \not = f(x_2), whenever \space x_1 \not = x_2$
inverse function, $f^{-1}(y)=x  \hArr f(x)=y$

# chap 3 Polynomial and rational functions
多项式和有理数方程


多项式函数的图像会多次地上升和下降，由于这个原因，它们在模拟现实场景、物体时非常有用。
船只设计时，会将不同的cubic function, cubic splines拼接在依赖来设计船体的自然曲线。也就是用多项式方程来进行3D建模。

A polynomial function of degree n:
$$
P(x) = a_nx^n + a_{n-1}x^{n-1} + \dotsi + a_1x^1 + a_0
$$

多项式的系数: $a_0, a_1, \dotsi, a_n$
$a_0$为常系数, constant coefficient, constant term, 不会随$x$自变量变化的量
$a_n$是最高次幂的系数，leading coefficient, 
$a_nx^n$, leading term

多项式的图像是连续光滑曲线, 
leading term的极值表现,多项式的极值由leading term确定
Intermediate value theorem for polynomails
>If P is a polynomail function and P(a) and P(b) have opposite signs, then there exists at least one value c between a and b which P(c) = 0

Guidelines for graphing polynomial functions
1. zeros
2. test points, above $x\text{-}axis$ or not
3. end behavior,
4. Graph,

local extrema,
dividing polynomials,
$$
P(x) = D(x)\cdot Q(x) + R(x)
$$
factor theorem
>$c$ is a zero of P if and only if $x-c$ is a factor of $P(x)$
rational zeros theorem
>If the P(x) has integer coefficents, 每一个rational zero的形式都为
>$$
\frac{p}{q}
$$
>where p is a factor of the constant coefficient $a_0$
>q is a factor of the leading coefficient $a_n$

synthetic division,
>一种快速分解多项式的方法,divisor is of the form$(x-c)$

remainder theorem
>If the polynomial is divided by $x-c$, then the remainder is $P(c)$
Descartes' Rule of Signs
>Let P be a polynomial with real coefficients
1. The number of positive real zeros of $P(x)$ is either equal to the number of variations in sign in $P(x)$ or is less than that by an even whole number
2. The number of negative real zeros of $P(x)$ is either equal to the number of variations in sign in $-P(x)$ or is less than that by an even whole number

The upper and lower bounds theorem
1. If we divide $P(x)$ by $x-b$ with $b>0$ using synthetic division, and if the row that contains the quotient and remainder has no negative entry, then $b$ is an upper bound for the real zeros of $P$
2. If we divide $P(x)$ by $x-a$ with $a<0$ using synthetic , and if the row contains the quotient and remainder has entries that are alternately nonpositive and nonnegative, then $a$ is a lower bound for the read zeros of $P$

complex numbers, $\sqrt{-1} = i$
Multiplication
$$
(a+bi)\cdot(c+di) = (ac -bd) + (ad + bc)i
$$
complex conjugate $\overline{z} = a-bi$
$$
z\cdot \overline{z} = (a+bi)(a-bi)=a^2 + b^2
$$
dividing complex numbers
$$
\frac{a+bi}{c+di}=\frac{(ac+bd)+(bc-ad)i}{c^2+d^2}
$$
zeros Theorem
>Every polynomial of degree $n\geqslant 1$has exactly $n$zeros, provided that a zero of mulitplicity $k$ is counted k times

conjugate zeros theorem
>If polynomial P has read coefficients, and if the complex number $z$ is a zero of P, then its complex conjugate $\overline{z}$ is also a zero of $P$

Rational functions
$$
r(x) = \frac{P(x)}{Q(x)}
$$
where $P, Q$ are polynomials. 假设它们之间没有公共因子。

vertical asynptote,
horizontal asymptote,
asymptotes of rational functions
Let $r$ be the rational function
$$
r(x) = \frac{a_nx^n + a_{n-1}^x{n-1} + \dotsi + a_1x + a_0}{b_mx^m + b_{m-1}x^{m-1} + \dotsi + b_1x + b_0}
$$
1. the vertical asymptotes of $r$ are the lines $x=a$, where $a$ is a zero of the denominator
2. (a) if $n<m$,then $r$ has horizontal asymptote $y=0$
3. (b) if $n=m$, then $r$ has horizontal asymptote $y=\frac{a_n}{b_m}$
4. (c) if $n>m$, then $r$ has no horizontal asymptote

sketchng Graphs of Rational Functions
1. factor, 分解分子，分母多项式
2. intercepts, 找到$x-intercepts$ by numerator zeros, 找到$y-intercepts$ by value of $x=0$
3. Vertical Asymptotes, 根据zeros of the denominator, $y \to \infin, y \to -\infin$
4. Horizontal Asymptotes, letting $x \to \plusmn \infin$
5. Sketch the graph, 画图

# chap 4 Exponential and Logarithmic Functions
指数和对数方程
$$
f(x) = 2^x
$$
指数方程是用来描述一些模型的，自然过程，比如人口增长、放射性衰变。
$$
f(x)=a^x , \space a > 0 \space and \space a \not = 1
$$
自然指数函数
$$
e=f(n)=(1+ \frac{1}{n})^n \\
f(x)=e^x
$$
用数学方程来模拟病毒的传播速度
logistic curve, 
logittic growth model,
**计算复利**，
compound interest,如果有一笔钱$P$, principal,投资的利息率是$i$ per time period.after one time period the interest is $P_i$, and the amount A of money is：
$$
A = P + P_i = P(1+i)
$$
在$k$periods time, the amount is
$$
A = P(1+i)^k
$$
如果年利息是$r$,利息的计算是每年计算$n$次。那么年内每段时间的利息率为 $i=r/n$, $t$ 年则会计算$nt$时间段。这就带来了$t$年后，总量的计算
$$
A(t) = P(1+\frac{r}{n})^{nt}
$$
continuously compounded interest:
$$
A(t) = Pe^{rt}
$$
>P, principal
r, interest rate per year
t, number of years

**对数方程**
Let $a$ be a positive number with $a\not = 1$, The logarithmic function with base a, denoted by $\log_a$, is define by
$$
\log_ax=y  \hArr f(y)=x
$$
common logarithm
$$
\log x = \log_{10} x
$$
科学家们使用对数函数来建模人类对刺激的响应, 如光、声、压力。对声音的强度来说, 物理声强要增加很多倍，我们才会觉得声音加倍响了
$$
S = k \log(\frac{I}{I_0})
$$
声音，分贝, 
**自然对数**
natural logarithm, $\ln x = \log_e x$

Laws of Logarithms
$$
log_a(AB) = log_aA + log_aB \\
log_a(\frac{A}{B}) = log_aA - log_aB \\
log_a(A^C) = C \log_aA
$$

**The law of forgetting**
Ebbinghaus' 遗忘定理, 如果一个任务掌握的程度为$P_0$, 在一段时间$t$后，对技能的掌握技能表示为
$$
\log P = \log P_0 - c \log(t+1)
$$
$c$为与任务有关的一个常量，$t$为月
$$
P=\frac{P_0}{(t+1)^c}
$$
改变对数的底
$$
y=\log_{b}x \\[0.5em]
y= \frac{\log_ax}{\log_a b} \\[0.5em]
\log_b a = \frac{1}{\log_a b}
$$
使用上面的定理可以很快的去计算任意底的对数计算
$$
\log_8{5} = \frac{\log_{10}5}{\log_{10}8}  \approx 0.77398
$$

辐射衰变,
$$
m(t) = m_0 e^{-rt}
$$
half-life,半衰期， 
牛顿的Law of Cooling,
$$
T(t) = 70 + 130 e^{-kt}
$$

# chap 5 Trigonometric functions of real numbers
实数的三角函数,
复习
Unit Circle 单位圆
$$
x^2 + y^2 = 1
$$
**reference number**
>$\overline t$ associated with $t$ is the shortest distance along the unit circle between the terminal point determined by t and $x-axis$

circuilar functions

Fundamental Identities
$$
\csc{t} = \frac{1}{\sin t} \\[0.5em]
\sec{t} = \frac{1}{\cos t} \\[0.5em]
\cot{t} = \frac{1}{\tan t} \\[0.5em]
\tan{t} = \frac{\sin t}{\cos t} \\[0.5em]
\cot{t} = \frac{\cos t}{\sin t} \\[0.5em]
$$
Pythagorean Identities
$$
\sin^2 t + \cos^2 t = 1 \\
\tan^2 t + 1 = \sec^2 t \\
1 + \cot^2 t = \csc^2 t \\
$$
Periodic Properties of Sine and Cosine
$$
\sin{(t + 2\pi)} = \sin{t} \\
\cos{(t + 2 \pi)} = \cos{t} \\
$$

Scientists use sine function to model the population of a predator and its prey.

Periodic Properties
$$
\tan(x+\pi) = \tan x \\
\cot(x + \pi) = \cot x \\
\csc(x + 2\pi) = \csc x \\
\sec(x + 2\pi) = \sec x \\
$$

Evaluating Functions
$$
\sin t = 1 - \frac{t^3}{3！} + \frac{t^5}{5!} - \frac{t^7}{7!} + \dotsi \\[1em]
\cos t = 1 - \frac{t^2}{2!} + \frac{t^4}{4!} - \frac{t^6}{6!} + \dotsi \\
$$

**Harmonic Motion**
为谐波运动建模, modeling periodic behavior, 

# chap 6 Trigonometric functions of angles
Radian Measure, radians, rad, 
Degrees and Radians
$$
180^{\circ} = \pi rad \\[0.5em]
1 rad = \Big(\frac{180}{\pi}\Big)^\circ  \\[1em]
1^{\circ} = \frac{\pi}{180}rad \\
$$
1 rad $\approx 57.296^\circ$, $1^\circ \approx 0.01745$ rad 
Angular speed
$$
\omega = \frac{\theta}{t}
$$
hypotenuse, 弦
opposite, 对边
adjacent,邻边

**Law of Cosine**
$$
a^2 = b^2 + c^2 - 2bc \cos A \\
b^2 = a^2 + c^2 - 2ac \cos B \\
c^2 = a^2 + b^2 - 2ab \cos C \\
$$

# chap 7 Analytic Trignometric
trigonometric identity
$$
\sin^2 \theta + \cos^2 \theta = 1 \\
\sin{2\theta} = 2\sin \theta \cos{\theta} \\
\sin{A}\cos{B} = \frac{1}{2}[\sin{A+B} + \sin{A-B}]
$$
Guidelines for proving Trigonometric Identities
>Start with one side
Use known identities
Convert to sines and cosines

Addition and Subtraction Formulas
$$
\sin{(s + t)} = \sin{s}\cos{t} + \cos{s}\sin{t} \\
\cos{(s + t)} = \cos{s}\cos{t} - \sin{s}\sin{t} \\
\tan{(s+t)} = \frac{\tan{s} + \tan{t}}{1 - \tan{s}\tan{t}} \\
$$

Half-angle formulas
$$
\sin^2{x}  = \frac{1-\cos{2x}}{2} \\[0.5em]
\cos^2{x} = \frac{1 + \cos{2x}}{2} \\[0.5em]
\tan^2{x} = \frac{1- \cos{2x}}{1+ \cos{2x}} \\[0.5em]
$$

product-to-sum formulas
$$
\sin{u}\cos{v} = \frac{1}{2}[\sin{(u+v)} + \sin{(u-v)}] \\[0.5em]
\cos{u}\sin{v} = \frac{1}{2}[\sin{(u+v)} - \sin{(u-v)}] \\[0.5em]
\cos{u}\cos{v} = \frac{1}{2}[\cos{(u+v)} + \cos{(u-v)}] \\[0.5em]
\sin{u}\sin{v} = \frac{1}{2}[\cos{(u-v)} - \cos{(u+v)}] \\[0.5em]
$$

sum-to-product formulas
$$
\sin x + \sin y = 2\sin{\frac{x+y}{2}}\cos{\frac{x-y}{2}} \\[0.5em]
\sin x -\sin y = 2\cos{\frac{x+y}{2}}\sin{\frac{x-y}{2}} \\[0.5em]
\cos{x}+\cos{y}=2\cos{\frac{x+y}{2}}\cos{\frac{x-y}{2}} \\[0.5em]
\cos{x}-\cos{y}=-2\sin{\frac{x+y}{2}}\sin{\frac{x-y}{2}}\\
$$

**Inverse Trignometric Functions**
$$
\arcsin(x) \space for \space -1 \leqslant x \leqslant 1 \\
\arccos(x) \space -\frac{\pi}{2} \leqslant x \leqslant \frac{\pi}{2} \\
$$

# chap 8 Polar coordinates and Vectors
**nth Roots of Complex Numbers**
$$
w_k = r^{1/n}[\cos{(\frac{\theta + 2k\pi}{n})} + i \sin{(\frac{\theta + 2k\pi}{n})}] \\
for \space k= 0,1,2,\dotsi, n-1
$$
DeMoivre's Theorem
$$
w^n = z
$$

**Fractals**
Mandelbrot set,$c$ is a complex number, 
$$
f(z) = z^2 + c
$$
Iterate $z_0, z_1, z_2, \dotsi, $will form a bounded set. 看起来很简单，有机会的话试一试。

**vectors**
initial point A, terminal point B,
$$
u = \overrightharpoon{AB} \\
v = \overrightharpoon{{BC}} \\
$$
vectors in the coordinate plane,
We represent $v$ as an ordered pair of real numbers,
$$
v = \langle a, b \rangle
$$
magnitude of a Vector
$$
|v| = \sqrt{a^2 + b^2}
$$
Algebraic Operations on Vectors
If $u=\langle a_1, b_1 \rangle$,and $v=\langle a_2, b_2 \rangle$
$$
u+v = \langle a_1 + a_2 , b_1 + b_2 \rangle \\
cu = \langle ca_1, cb_1  \rangle, \space c \in \Z
$$

**Dot Product**
Very important, $u\cdot v = a_1a_2 + b_1b_2$, it's a real number, or scalar
Dot Product Theorem
$$
u\cdot u = |u|^2 \\
u\cdot v = |u| |v| \cos{\theta} \\
|u -v |^2 = |u|^2 + |v|^2 -2|u| |v| \cos{\theta} \\
\cos{\theta} = \frac{u\cdot v}{|u| |v|} \\
$$

The component of $u$ along $v$ can be computed by
$$
|u|\cos{\theta} = \frac{|v| |u| \cos{\theta}}{|v|} = \frac{u\cdot v}{|v|}
$$
计算功
$$
W = F\cdot D = (|F|\cos{\theta})|D| = |F||D|\cos{\theta}
$$

# chap 9 Systems of Equations and Inequalities
在现实世界里，许多建模里面涉及很多变量，不能用一个单一方程来描述。比如，天气预报依赖于多种因素，包括:温度、风速、空气压强、湿度...对天线预测来说，科学家使用了多个方程，每个方程都有多个变量。这样的方程系统一起描述了天气情况。

使用*augmented matrix*来解这些方程。matrix equation
$$
AX=B
$$
$X$ is the unknown matrix, analogous to solving the algebraic equation $ax=b$ for the number $x$

我们考虑矩阵的多钟用法, 包括人口增长，计算机图形学。

多元方程的解法:
* Substitution Method, 替换法,
* Elimination Method, 消元法, 
* 图形法, 找到曲线的交点, 

Linear Equations in Two Variables,
Modeling with Linear Systems,
多元线性方程组,
高斯消元, Gaussian Elimination,
>1.Augmented matix
>2. Row-Echelon Form
>3. Back-Substitution

使用线性方程来进行建模, 

Matrix, row=m, col=n, $m\times n$
Elementary Row Operations
$$
R_i + kR_j \to R_i \\
kR_i \\
R_i \leftrightarrow  R_j
$$

Gauss-Jordan Elimination,

方程组的解的情况
- No solution, 无解, inconsistent, 
- One solution, 一个解
- infinitely many solutions, dependent,

**Algebra of Matrices**
矩阵代数, 加、减、乘
矩阵乘法
$$
C=AB,  
$$
Properties of Matrix Multiplication
$$
A(BC) = (AB)C , Associative \space  Property \\
A(B+C) = AB + AC, \\
(B+C)A = BA + CA , \space Distributive \space Property \\
$$
transition matrix,

Identity matrices,单位矩阵,
$ A\cdot I_n = A $
**Inverse of Matrix**
$ AA^{-1}= A^{-1}A = I_n $
Finding the Inverse of a Matrix
$$
If \space A= \begin{bmatrix}
    a & b \\
    c & d \\
\end{bmatrix}
then \space A^{-1} = \frac{1}{ad-bc} \begin{bmatrix}
    d  & -b \\
    -c &  a
\end{bmatrix}
$$
如果$ad - bc = 0$, 则$A$没有inverse

Solving a Matrix Equation
$$
AX=B \\
X=A^{-1}B \\
$$

Determinants of matrix
行列式, 
$$
A_{ij} = (-1)^{i+j}M_{ij}
$$

**Cramer's Rule**
The linear syste:
$$
\begin{cases}
    ax + by = r \\
    cx + dy = s \\
\end{cases}
$$
解为
$$
x = \frac{\begin{vmatrix}
    r & b \\
    s & d \\
\end{vmatrix}}{\begin{vmatrix}
    a & b \\
    c & d \\
\end{vmatrix}}, \space
y= \frac{\begin{vmatrix}
    a & r \\
    c & s \\
\end{vmatrix}}{\begin{vmatrix}
    a & b \\
    c & d \\
\end{vmatrix}}
$$

**Partial Fractions**
部分分式, 部分分式的分解，decomposition,

**不等式系统**
Systems of Inequalities

# chap 10 Analytic Geometry
conic sections, cut in the cone,
* circle
* Ellipse
* parabola
* hyperbola

analyzing the geometric properties, path of a projectile, 弹道线, 

**parabola**
>定义, the set of points in the plane equidistant from a fixed point F (called the *focus*) and a fixed line *l*(called the directrix)

axis of symmetry, let $P(x,y)$ be any point on the parabola ,focus point is $(0,P)$, 

the distance from P to F is
$$
\sqrt{x^2 + (y-p)^2}
$$
the distance from P to the directrix
$$
|y - (-p)| = |y + p|
$$
parabola的方程为
$$
x^2 = 4pyloo
$$
抛物线有一个重要的特征，就是作为灯盏、射电望远镜的反射器, 反射聚焦, *reflection property*, 

**Ellipses**
椭圆的定义
>the set of all points in the plane the sum of whose distances from two fixed points $F_1$ and $F_2$ is a constant, These two fixed points are the *foci* of the ellipse,

令foci为$(-c,0), (c,0)$,距离之和为$d(P,F_1) + d(P,F_2)=2a$
$$
\sqrt{(x+c)^2 + y^2} + \sqrt{(x-c)^2 + y^2} = 2a \\[0.5em]
(a^2 - c^2)x^2 + a^2y^2 = a^2(a^2 - c^2) \\[0.5em]
2a>2c, a^2-c^2>0, \\
\frac{x^2}{a^2} + \frac{y^2}{a^2-c^2}= 1 \\
$$
我们设$b^2 = a^2 - c^2, b < a$
方程整理为
$$
\frac{x^2}{a^2} + \frac{y^2}{b^2} = 1
$$
major axis is 2a, minor axis is 2b, 

**eccentricity**
离心率, 
$$
e=\frac{c}{a}
$$

行星轨迹的2个焦点，近焦点叫perihelion,远焦点叫aphelion, 

**hyperbolas**
双曲线, 定义
>the set of all points in the plane, the difference of whose distances from two fixed points $F_1$ and $F_2$ is a constant, these 2 fixed points are the *foci* of the hyperbola

$$
d(P,F_1) - d(P, F_2) = \plusmn 2a \\[0.5em]
\sqrt{(x+c)^2 + y^2} - \sqrt{(x-c)^2 + y^2} = \plusmn 2a \\[0.5em]
(c^2 - a^2)x^2 - a^2y^2 = a^2(c^2 - a^2) \\[0.5em]
\frac{x^2}{a^2} - \frac{y^2}{b^2} = 1 \\
$$
equation of the hyperbola, 

center, transverse axis, branches, two parts,
用于卡塞格伦天线，双曲线的反射特性, 抛物面的交点和双曲线的一个焦点重合，这样平行射入的光汇聚到双曲线的焦点并反射到双曲线的另一个焦点上。
*Cassegrain-type* telescope

**LORAN system**
Long Range Navigation system, 1990, 4对基站，实现两条双曲线，双曲线的交点，即可实现定位，好方法!

**Shifted Conics**

坐标轴旋转角度$\phi + \theta$
原来的x坐标
$$
\begin{aligned}
    x &= r \cos{(\theta +\phi)} \\
    &= r(\cos{\theta}\cos{\phi} - \sin{\theta}\sin{\phi}) \\
    &= (r\cos{\theta})\cos{\phi} - (r\sin{\theta})\sin{\phi} \\
    &= X\cos{\phi} - Y\sin{\phi} \\
\end{aligned}
$$
原来的y坐标
$$
\begin{aligned}
y&=r\sin{(\theta + \phi)} \\
&= r(\sin{\theta}\cos{\phi} + \cos{\theta}\sin{\phi}) \\
&= Y\cos{\phi} + X\sin{\phi} \\
\end{aligned}
$$

Relation of Axes Formulas
$$
x = X\cos{\phi} - Y\sin{\phi} \\
y = X\sin{\phi} + Y\cos{\phi } \\
X = x\cos{\phi} + y\sin{\phi } \\
Y = -x\sin{\phi} + y\cos{\phi} \\
$$

**General Equation of a Conic**
广义形式为
$$
Ax^2 + Bxy + Cy^2 + Dx + Ey + F = 0
$$
可以将x,y转换为X,Y坐标系，不包含XY项。

discriminant of the equation, 判断conic的形式$B^2-4AC$
1. a parabola if $B^2-4AC=0$
2. an ellipse if $B^2-4AC<0$
3. a hyperbola if $B^2-4AC>0$

图形学的旋转
$$
R=\begin{bmatrix}
    \cos{\phi} & -\sin{\phi} \\
    \sin{\phi} & \cos{\phi} \\
\end{bmatrix}
$$

**Polar Equations of Conics**
Equivalent Description of Conics


Plane curves and Parametric Equations,

*cycloid*
>As a circle rolls along a straight line, the curve traced out by a fixed point $P$ on the circumference of the circle is called a cycloid.

最快下降曲线.? 有意思, 

Lissajous figure,
$ x=A\sin{w_1t}, \space y=B\cos{w_2t} $

# chap 10 Sequences and Series
 数组，序列, 
Sequence
>a set of numbers written in order, 按照某种顺序排列的许多数

递归定义的序列
**sieve of Eratosthenes**
去掉所有的质数的倍数
**Fibonacci Sequence**
斐波那契数列, 序列，数列, 
$F_n = F_{n-1} + F_{n-2}$
是在研究兔子的繁殖时发现的，在自然界存在许多现象满足。

**sigma notation**
$$
\sum_{k=1}^{n}a_k = a_1 + a_2 + a_3 + \dotsi + a_n
$$
index of summation, summation variable,

**golden ratio**
$1.618$

算术平均数
$$
m=\frac{a+b}{2}
$$

**Geometric Sequences**
几何序列, 
$$
a,ar, ar^2, ar^3, ar^4,\dotsi \\
S_n = a + ar + ar^2 + ar^3 + ar^4 + \dotsi \\
rS_n = ar + ar^2 + a^3 + a^4 + \dotsi \\
S_n - rS_n = a - ar^n \\[0.5em]
S_n = \frac{a(1-r^n)}{1-r}
$$
r是common ratio

**Finding Patterns**
triangular numbers,
square numbers,
pentagonal numbers,

**Mathematics of Finance**
金融数学, 
annuity, amount of an annuity,年金, 
Amount of an Annuity
$$
A_f = R\frac{(1+i)^n -1}{i}
$$

Mathematical Induction,
数学归纳法, 
数学的两大方面是发现和证明, discovery and proof, 
猜想一个，奇数之和为$n^2 = 1 + 3 + 5 + \dotsi + (2n-1)$
induction, 归纳法, induction hypothesis, 

**sums of Powers**
$$
\sum_{k=1}^n 1 = n \\
\sum_{k=1}^n k = \frac{n(n+1)}{2} \\
\sum_{k=1}^n k^2 = \frac{n(n+1)(2n+1)}{6} \\
\sum_{k=1}^n k^3 = \frac{n^2(n+1)^2}{4} \\
$$

**The Binomial Theorem**
二项式定理, $a+b$这样的额表达式被称为二项式, then we expand $(a+b)^n$

$$
\begin{aligned}
(a+b)^1 &= a+ b \\
(a+b)^2 &= a^2 + 2ab + b^2 \\
(a+b)^3 &= a^3 + 3a^2b + 3ab^2 + b^3 \\
(a+b)^4 &= a^4 + 4a^3b + 6a^2b^2 + 4ab^3 + b^4 \\
(a+b)^5 &= a^5 + 5a^4b + 10a^3b^2 + 10a^2b^3 + 5ab^4 + b^5 \\
&\vdots
\end{aligned}
$$

**The Binomial Coefficient**
>let n and r be nonnegative integers with $r \leqslant n $,
$$
\begin{pmatrix}
    n \\
    r \\
\end{pmatrix} = \frac{n!}{r!(n-r)!} \\[1em]
\begin{pmatrix}
    n \\
    r \\
\end{pmatrix} = \begin{pmatrix}
    n \\
    n-r \\
\end{pmatrix}
$$

For any nonnegative integers $r$ and $k$ with $r \leqslant k$
$$
\begin{pmatrix}
    k \\
    r-1 \\
\end{pmatrix}+
\begin{pmatrix}
    k \\
    r \\
\end{pmatrix}=
\begin{pmatrix}
    k+1 \\
    r \\
\end{pmatrix}
$$

# chap 12 Limits
极限的概念, 定义
$$
\lim\limits_{x\to a}f(x) = L
$$
left and right-hand limits
$$
\lim\limits_{x \to a}f(x) = L, \space 
$$
if and only if
$$
\lim\limits_{x \to a^{-}}f(x) = L = \lim\limits_{x \to a^{+}}f(x)
$$

roller coaster,

Done




