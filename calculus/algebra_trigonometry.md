Algebra and Trigonometry
====

# chap 1 Numbers
## 1 Introduction
代数, Algebra, 最重要的两个数字系统是
* integers, 整数, 
* rational numbers, 整数和分数, fractions,

hypotenuse, 斜边,

## 2 实数系统的代数性质
equivalence laws,
closed under addition,
associative law, $(a+b)+c = a+(b+c)$
zero $0$, identity element for addition,
negative number, $a + (-a) = 0$, additive inverse
commutative law, $a+b=b+a$
closed under multiplication,
associative law, $(ab)c = a(bc)$
one $1$, identity element for multiplication,
reciprocal, multiplicative inverse of
$$
a\frac{1}{a}=1
$$
commutative law, $ab=ba$
The left distributive law, $a(b+c)=ab+ac$

field,
an important part of advanced modern algebra,
21                                    

set,
subsets, $B \subset A$,B is a subset of A, B is contained in A,
null set, $\empty$, void set, empty set,

## 8. 集合的代数运算， The algebra of sets
$U$ as the universal set,集合, 
union
intersection of 2 subsets,
$X\bigcup Y$= {set of all elements that belong to X or to Y or to both}   
$X \bigcap Y$= {set of all elements that belong to both X and Y}

Venn diagrams, 维恩图, 满足的运算
Communicative laws, 交换律,
$A\cup B=B\cup A, A\cap B=B\cap A$
Associative laws, 结合律,
$(A\cup B)\cup C = A\cup(B\cup C)$
$(A\cap B)\cap C = A \cap(B\cap C)$
Distributive law, 分配率
$A\cap(B\cup C)=(A\cap B)\cup(A\cap C)$
Identity laws, 同一律,
$A\cup \empty = A, A\cap U = A, A\cup U=U, A\cap \empty=\empty$

Complement of $A$, $\tilde{A}$
DeMorgan's laws,德摩根定律
$\overline{A\bigcup B}=\tilde{A}\bigcap \tilde{B}$
$\overline{A\bigcap B}=\tilde{A}\bigcup \tilde{B}$

Boolean algebra, 布尔代数, 这个分配率太重要了啊，神器!

## 9 Variables
变量, 
用一个符号$x$来表示集合里的不确定的成员, let x be an arbitrary real number. Such a symbol is called a *variable*. The set is called the scope of the variable. also called the replacement set. 
A variable whose scope is a set consisting of only one object is called *constant*.

## 10 The function Concept
independent variable,
dependent variable,
one to one, ordered pairs,

函数图像,
coordinate axes, 坐标轴, 
origin, 原点, 
abscissa, x-coordinate, x,
ordinate, y-coordinate, y,
quadrants, four planes divided by coordinate axes,
Cartesian coordinate system, 
analytic geometry, 
Pythagorean theorem, 

# chap 3 Equations
solution set, solutions,
solution or root of the equation,
$y=kx$, $y$ varies directly as $x$,

Quadratic Equations,
二次方程, 
$ax^2 + bx +c =0$
$(x+\frac{b}{2a})^2 - \frac{b^2-4ac}{4a^2}=0$
Factoring the left member as the difference of two squares , we obtain
$$
[(x+\frac{b}{2a})-\frac{\sqrt{b^2-4ac}}{2a}][(x+\frac{b}{2a})+\frac{\sqrt{b^2-4ac}}{2a}]=0\\
$$
quadratic formula
$$
x=\frac{-b \plusmn \sqrt{b^2-4ac}}{2a}
$$
by adding and multiplication, we obtain
$$
r_1 + r_2 = -\frac{b}{a}\\
r_1r_2=\frac{c}{a}
$$

## 17 Equations Containing Radicals
$\sqrt{x-1} + \sqrt{3x+1} = 6$
移位，平方，解出来后，重新代入进行检验。

# 4 Inequalities
绝对值， 

# 5 Systems of Linear Equations
Solution set, 

# 6 Matrices and Determinants
矩阵和行列式, 
$$
a_1x + b_1y = c_1 \\
a_2x + b_2y = c_2 \\
$$
square matrix of order two, elements, columns 
$$
\begin{pmatrix}
    a_1 & b_1 \\
    a_2 & b_2 \\
\end{pmatrix}
$$

determinant,
$$
\begin{vmatrix}
    a_1 & b_1\\
    a_2 & b_2 \\
\end{vmatrix}
$$
$a_1b_2 - b_1a_2$

Third-order matrix,
coefficient matrix,
线性方程组的解,

**Cramer's Rule**
克莱默规则, 
Consider the set of linear equations
$$
\tag{9}\begin{aligned}
    a_1x+b_1y+c_1z &= d_1 \\
    a_2x+b_2y+c_2z &= d_2 \\
    a_3x+b_3y+c_3z &= d_3 \\
\end{aligned}
$$
The matrix of the coefficients is
$$
M=\begin{pmatrix}
    a_1 & b_1 & c_1\\
    a_2 & b_2 & c_2 \\
    a_3 & b_3 & c_3 \\
\end{pmatrix}
$$
Thus we have
$$
\lvert M \rvert \cdot x = d_1A_1 + d_2A_2 + d_3A_3
$$
解方程组,
$$
x=\frac{\begin{vmatrix}
    d_1 & b_1 & c_1 \\
    d_2 & b_2 & c_2 \\
    d_3 & b_3 & c_3 \\
\end{vmatrix}}{|M|}
$$

$$
y=\frac{\begin{vmatrix}
    a_1 & d_1 & c_1 \\
    a_2 & d_2 & c_2 \\
    a_3 & d_3 & c_3 \\
\end{vmatrix}}{|M|}
$$

$$
z=\frac{\begin{vmatrix}
    a_1 & b_1 & d_1 \\
    a_2 & b_2 & d_2 \\
    a_3 & b_3 & d_3 \\
\end{vmatrix}}{|M|}
$$
对于实际系统中，拥有100个方程的情况may arise. High speed electronic computers have made feasible the solution of such large systems.

矩阵的特性:
* If the rows and columns of a matrix be interchanged, the value of the determinant of the matrix is unaltered.
* The sign of the determinant of a matrix is changed by interchanging two rows or two columns of the matrix
* If a matrix has two of its rows or two of its columns identical, the value of the determinant of the matrix is zero
* If a matrix has a row or column consisting entirely of zeros, the determinant of the matrix is zero
* Multiplying each element of a row (or column) of a matrix by the same number multiplies the determinant of the matrix by that number
* If to the elements of any row (or column) of a matrix are added constant multiples of the corresponding elements of another row(or column), the value of the determinant of the matrix is unchanged.

**矩阵的代数运算**

# 7 Mathematical induction, the binomial theorem and progressions
数学归纳法, 

Binomial Theorem, 二项式定理
$(a+b)^n$
$(a+b)^1=a+b$    
$(a+b)^2=a^2+2ab+b^2$
$(a+b)^3=a^3+3a^2b+3ab^2+b^3$
$(a+b)^4=a^4+4a^3b +6a^2b^2+4ab^3+b^4$
$(a+b)^5=a^5+5a^4b+10a^3b^2+10a^2b^3+5ab^4+b^5$

the symbol $n!$, read n factorial. 

$(a+b)^n=a^n + \binom{n}{1}a^{n-1}b + \binom{n}{2}a^{n-2}b^2 + \dotsi + \binom{n}{k}a^{n-k}b^k + \dotsi + b^n$
$$
\binom{n}{r} = \frac{n!}{r!(n-r)!}a^{n-r}b^r
$$

**Arithmetic Progressions**
等差数列
common difference, difference between, 
arithmetic mean, 算术平均数, 

**geometric progressions**
几何级数, common ratio, 
$$
S_n = a\frac{1-r^n}{1-r}
$$

Common fractions
Repeating Decimals,

# 8 Exponents and logarithms
$(xy)^n=x^ny^n$

$a\sqrt[n]{x}$, $\sqrt[n]{x}$ is called a radical, n is called the index or order of the radical, x is called the radicand. a is called the coefficient of the radical.

根, 

common logarithms, $\log_{10} N$
natural logarithms,  $\ln{N}$

# 9 The Trigonometric Functions
三角函数, 

# 10 Trigonometric Analysis
number of radians in $360^{\circ}$ is $2\pi$
$$
\sin^2\theta + \cos^2\theta = 1\\
1+ \tan^2\theta = \sec^2\theta \\
1+ \cot^2\theta = \csc^2\theta \\
$$
公式:
$$
\cos{(A-B)}=\cos{A}\cos{B}+\sin{A}\sin{B}\\
\sin{A+B}=\sin{A}\cos{B}+\cos{A}\sin{B}\\[0.5em]
\tan{(A+B)}=\frac{\tan{A} + \tan{B}}{1-\tan{A}\tan{B}}\\[0.5em]
\cos{2A} = 1 - 2\sin^2A = 2\cos^2{A} -1 \\
$$
Formulas
$$
\sin{(A+B)}=\sin{A}\cos{B}+\cos{A}\sin{B} \\
\sin{(A-B)}=\sin{A}\cos{B}-\cos{A}\sin{B} \\[0.5em]
\sin{A}\cos{B}=\frac{1}{2}[\sin{(A+B)}+\sin{(A-B)}]\\[0.5em]
\cos{A}\sin{b}=\frac{1}{2}[\sin{(A+B)}-\sin{(A-B)}]
$$
同理也可以
$$
\cos{A}\cos{B}=\frac{1}{2}[\cos{(A+B)}+\cos{(A-B)}]\\[0.5em]
\sin{A}\sin{B}=-\frac{1}{2}[\cos{(A+B)}-\cos{(A-B)}]\\[0.5em]
$$

Let
$A+B=u, A-B=v$
Then by adding and subtracting we get
$A=\frac{1}{2}(u+v), B=\frac{1}{2}(u-v)$

$$
\sin{u}+\sin{v}=2\sin{\frac{(u+v)}{2}}\cos{\frac{(u-v)}{2}}\\[0.5em]
\sin{u}-\sin{v}=2\cos{\frac{(u+v)}{2}}\sin{\frac{(u-v)}{2}}\\[0.5em]
\cos{u}+\cos{v}=2\cos{\frac{(u+v)}{2}}\cos{\frac{(u-v)}{2}}\\[0.5em]
\cos{u}-\cos{v}=-2\sin{\frac{(u+v)}{2}}\sin{\frac{(u-v)}{2}}\\[0.5em]
$$

第二部分，The Complex Number System
$$
x=r\cos{\theta}, y=r\sin{\theta}\\
r=\sqrt{x^2+y^2}, \tan{\theta}=\frac{y}{x}\\
$$

**DeMoivre's Theorem**
$$
[r(\cos{\theta} +i\sin{\theta})]^n=r^n(\cos{n\theta} +i\sin{n\theta})
$$

**复数的根**
To find all complex numbers $z=r(\cos{\theta} + \sin{\theta})$ such that $z^n=w$
$$
r^n[\cos{n\theta}+i\sin{n\theta}]=R(\cos\phi +i\sin{\phi})
$$
则
$$
n\theta = \phi + k\cdot 360^\circ , \space \theta=\frac{\phi+k\cdot 360^{\circ}}{n}
$$

# 12 Theory of Equations
Polynomial equation of degree $n$
P(x) and D(x) $\not = 0$
$$
P(x)=D(x)\cdot Q(x) + R(x)
$$
$Q(x)$ is quotient, $R(x)$ is remainder.

**Factor Theorem**

**synthetic division**
简易除法, $(x-a)$

**Graph of a Polynomial**
多项式的图,
如果多项式$P(x)$的系数是实数, 那么$P(x)$ 定义了一个函数，called a polynomial function, $y=P(x)$. 

求根的方法。


















