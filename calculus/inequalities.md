# Inequalities
elementary inequalities

NML, New Mathematical Library, In 1961 by the school Mathematics Study Group . To make available to high school students short expository books on various topics not usually covered in the high school syllabus.

**NML**, into a steadily growing series of some 20 titles of interest not only to the originally intended audience but to college students and teachers at all levels.

Previously published by Random House and L. W. Singer

MAA, Mathematical Association of America

AMS/MAA, Anneli Lax New Mathematical library

Student Mathematical Library,

Springer book series(Undergraduate/Graduate Texts in Mathematics)

Little Mathematical library

看哪一本书呢?
- little mathematics library 系列的 inequalities
- elementary inequalities
- mathematics olympiad ... inequalities
- geometric inequalities


# <Elementary Inequalities>
推荐书籍:
- John William Archbold，Algebra, 1970,
- Advanced Algebra, Robson , 1948 

## 0.1 Inequalities involving Mean Value
和平均值有关的不等式
### 0.1.1 For every set of positive numbers $A=\{a_1,a_2,\dotsi,a_n \}$
$$
\begin{aligned}
    \min{(a_1,a_2,\dotsi,a_n)} &\leqslant \frac{n}{\frac{1}{a_1}+\frac{1}{a_2}+\dotsi + \frac{1}{a_n}}\\
&\leqslant (a_1 a_2 \dotsi a_n)^{1/n}\\
&\leqslant \frac{a_1+a_2+\dotsi +a_n}{n}\\
&\leqslant (\frac{a_1^2 + a_2^2 +\dotsi + a_n^2}{n})^{1/2}\\
&\leqslant \max{(a_1,a_2,\dotsi, a_n)}\\
\end{aligned}
$$
where
harmonic mean of the numbers $A$, 调和平均值,
geometric mean,几何平均值,
arithmetic mean,
root-mean-square,

$1^{\circ}$ Consider the first inequality
算术平均数 $\geqslant$ 几何平均数
$$
A_n \equiv \frac{a_1+a_2+\dotsi +a_n}{n} \geqslant (a_1 a_2 \dotsi a_n)^{1/n} \equiv G_n
$$
**Proof 1:**
For $n=2$,  
$$
(\sqrt{a_1} - \sqrt{a_2})^2 \geqslant 0 \\[0.5em]
a_1 + a_2 \geqslant 2\sqrt{a_1 a_2}\\[0.5em]
\frac{a_1 + a_2}{2} \geqslant (a_1a_2)^{1/2}\\
$$
Assume that it is valid for $n=k$, i.e., $A_k \geqslant G_k$
By induction
$$
A\equiv \frac{a_{k+1} + (k-1)A_{k+1} }{k} \geqslant (a_{k+1}(A_{k+1})^{k-1})^{1/k}\equiv G\\
$$

这里就是一个很典型的阅读数学推导，理解不下去，卡住了的场景!

解释:
从另一个角度来看，上面这个等式并没有从前文提到过，而是突然出现的。作者突然插进来这个东西，作为读者是有点诧异的。实际上这里还是使用了之前$A_n\geqslant G_n$的公式。代$a_1, a_2,a_3$ 以 $a_{k+1}, A_{k+1}, A_{k+1},A_{k+1},\dotsi$, 其中有$(k+1)$个$A_{k+1}$

作者是如何想到这个可以用来解题的例子的呢？不知。这不是一种线性思维，而是在最终解题完毕后，重新描述得一条思维推导道路。不是那么自然得就能得到得解题步骤。

Thus, it follows that, 这里作者又构造了另一个例子、场景
$$
A_{k+1}=\frac{A_k + A}{2} \geqslant (A_kA)^{1/2} \geqslant (G_kG)^{1/2} = ((G_{k+1})^{k+1}(A_{k+1})^{k-1})^{1/2k}
$$
这里又看不懂了。
此处使用得数学技巧是:将$A_k$本身作为$A$的一部分，这里有点嵌套的意思。

解释:
首先, 有一组实数序列$a_1,a_2,\dotsi, a_k, a_{k+1}$
$A_k = (a_1+a_2+\dotsi + a_k)/k$
$G_k = (a_1a_2\dotsi a_k)^{1/k}$
$a_{k+1}$
$A_{k+1}=(a_1+a_2+\dotsi + a_k + a_{k+1})/(k+1)$
$G_{k+1} = (a_1a_2\dotsi a_ka_{k+1})^{1/(k+1)}$

凭空构造了一个k个元素的序列 {$a_{k+1}, A_{k+1},A_{k+1},\dotsi$}
假定在n=k时，不等式是成立的。

又构造了一个2个元素的序列 $\{ A_k, A \}$, 将这个2元素序列的算术平均数作为新的元素$A_{k+1}$

这里思维卡在了$(G_kG) \sim (G_{k+1}^{k+1}A_{k+1}^{k-1})^{1/k}$,这里是怎么替换出来的呢？前面并没有非常明确的说明。

$G_k=(a_1a_2\dotsi a_k)^{1/k}=(a_{k+1}a_{k+1}\dotsi a_{k+1})^{1/k}$
$G= (a_{k+1}(A_{k+1})^{k-1})^{1/k}$
$G_{k+1}^{k+1}=((a_1a_2\dotsi a_{k+1})^{1/(k+1)})^{k+1}=a_1a_2\dotsi a_{k+1}$
我们再来求$G_k G$
$$
G_kG=(a_1a_2\dotsi a_{k})^{1/k}\cdot a_{k+1}^{1/k}(A_{k+1}^{k-1})^{1/k}\\[0.5em]
G_kG=(G_{k+1}^{k+1} A_{k+1}^{k-1})^{1/k}\\
$$
所以我们得到了:
$$
A_{k+1} \geqslant (G_kG)^{\frac{1}{2}} =(G_{k+1}^{k+1}A_{k+1}^{k-1})^{\frac{1}{2k}}\\
$$
继续推导
$$
A_{k+1} \geqslant (G_{k+1}^{\frac{k+1}{2k}})(A_{k+1}^{\frac{k-1}{2k}})\\
$$
两边同时计算$2k$方
$$
A_{k+1}^{2k} \geqslant G_{k+1}^{k+1} A_{k+1}^{k-1 }
$$
如果$G_{k+1} > A_{k+1}$,那么
$$
A_{k+1}^{2k} \geqslant G_{k+1}^{k+1} A_{k+1}^{k-1} \ge A_{k+1}^{k+1}A_{k+1}^{k-1} = A_{k+1}^{2k}
$$
显然除了$=$外，是不成立，一个数不能大于其自身，
所以
$$
A_{k+1} \geqslant G_{k+1}
$$

这个证明真的是又臭又长啊

其中$A_{k+1} = \frac{1}{2}(A_k + A)$ 这个式子，难道没有问题吗?
也是需要证明的。
$A_{k+1}= (a_1+a_2+\dotsi +a_{k+1})/(k+1)$
$A_{k}= (a_1+a_2+\dotsi +a_{k})/k$
取右式
$$
\begin{aligned}
A_k + A &= \frac{a_1+a_2+\dotsi+a_k}{k} + \frac{a_{k+1} + (k-1)A_{k+1}}{k}\\
&=\frac{(k+1)A_{k+1} + (k-1)A_{k+1}}{k}\\
&=\frac{2kA_{k+1}}{k}\\
&=2A_{k+1}\\
\end{aligned}
$$
易证。这一步是最难的!

On the basis of thei proof, equality holds if and only if $a_1=a_2=\dotsi=a_n$

This result is obvious if $n=2$. We can see that if $A_{k+1}=G_{k+1}$, then $A_k=A, A_k=G_k, A=G$

**Proof 2**
第二种证明方式，看起来也不错,

Consider the relations:
$$
(a_1+a_2+\dotsi + a_n)^2 \equiv a_1^2 + a_2^2 + \dotsi + a_n^2 + 2(a_1a_2 + a_1a_3 + \dotsi + a_{n-1}a_n)\\
$$
$2a_ia_j \leqslant a_i^2 + a_j^2$, since $(a_i-a_j)^2 \geqslant 0$
Replacing $2a_ia_j$ by $a_i^2 + a_j^2$ on the right-hand side of the identity. we obtain the inequality
$$
(a_1+a_2+\dotsi + a_n)^2 \leqslant n(a_1^2 + a_2^2 +\dotsi + a_n^2)\\
$$
If all $a_i$ are positive, it follows from that
$$
a_1+a_2+\dotsi + a_n \leqslant \{ n(a_1^2 + a_2^2 +\dotsi + a_n^2) \}^{1/2}
$$
whence
$$
\frac{a_1+a_2+\dotsi + a_n}{n}\leqslant \{\frac{a_1^2 + a_2^2 +\dotsi + a_n^2}{n}\}^{\frac{1}{2}}
$$

It will now be shown that 
$$
\min{(a_1,a_2,\dotsi,a_n)} \leqslant \frac{n}{\frac{1}{a_1}+\frac{1}{a_2}+\dotsi + \frac{1}{a_n}}
$$
Without loss of generality, suppose that
$$
0 < a_1 \leqslant a_2 \leqslant \dotsi \leqslant a_n
$$
and hence $\min{(a_1,a_2,\dotsi,a_n)} = a_1$
We know
$$
\frac{a_1}{a_1} + \frac{a_1}{a_2} + \dotsi + \frac{a_1}{a_n} \leqslant n\\[0.5em]
\frac{1}{a_1}+ \frac{1}{a_2} + \dotsi + \frac{1}{a_n} \leqslant \frac{n}{a_1}
$$
所以
$$
\min(a_1,a_2,\dotsi,a_n) \leqslant \frac{n}{\frac{n}{a_1}} \leqslant a_1
$$
$max()$ 最大值的证法类似。

### 0.1.2 Prove the inequality
$$
\min(\frac{a_1}{b_1},\frac{a_2}{b_2}, \dotsi,\frac{a_n}{b_n})\leqslant \frac{a_1+a_2 + \dotsi + a_n}{b_1+b_2+\dotsi + b_n}\\[0.5em]
\leqslant \max(\frac{a_1}{b_1},\frac{a_2}{b_2}, \dotsi,\frac{a_n}{b_n})
$$
where $b_1,b_2,\dotsi,b_n$ are positive numbers.

If $m$ is the smallest and $M$ the largest of the numbers 
$$
\frac{a_1}{b_1},\frac{a_2}{b_2}, \dotsi,\frac{a_n}{b_n}
$$
then
$$
m \leqslant \frac{a_1}{b_1} \leqslant M, m \leqslant \frac{a_2}{b_2} \leqslant M, \dotsi, m \leqslant \frac{a_n}{b_n} \leqslant M
$$
whence it follows that
$$
m\sum_{k=1}^{n}b_k \leqslant \sum_{k=1}^{n} a_k \leqslant M\sum_{k=1}^{n}b_k \\[0.5em]
m \leqslant \frac{\sum_{k=1}^{n}a_k}{\sum_{k=1}^{n}b_k} \leqslant M\\
$$
as was to be proved.

Mean value, 平均值是概率论里的重要理论, 数学分析。

## 0.2 Bernoulli's Inequality
伯努利不等式, 
If $h>-1$ and $n$ is a natural number, then Bernoulli's inequality states that
$$
(1+h)^n \geqslant 1+nh
$$
Proof:
Apply the method of mathematical induction. If $n=1$ then the relation holds as an equality. Suppose that the relation holds for $n=k \space (k\geqslant 1)$, i.e. that
$$
(1+h)^k \geqslant 1+kh\\
$$
Multiplying this inequality by $1+h\space(>0)$, we obtain
$$
(1+h)^{k+1} \geqslant (1+kh)(1+h)\\
(1+h)^{k+1} \geqslant 1+(k+1)h+kh^2 $$
as $kh^2>0$, whence $(1+h)^{k+1} \geqslant 1+(k+1)h$
The proof is essentially complete.

Next the generalized Bernoulli inequalities, required in differential calculus, will be established:
$(1+x)^a>1+ax$, $(-1<x\not = 0,a>1$ or $a<0)$,
$$
(1+x)^{a} < 1+ax, \space (-1<x\not = 0, 0<a<1>)\tag{5}
$$
我开始用自己的方式，缓慢地阅读这本讲基本不等式的书.

In fact using Taylor's formula, we obtain
$$
(1+x)^a-1-ax=\frac{a(a-1)x^2}{2}(1+\theta x)^{a-2}\space (0<\theta<1) \tag{6}
$$
首先，回忆一下泰勒展开,
$f(x)$ 在某邻域具有任意阶到时，且余项$R_n(x)=0, n\to \infin$
$$
f(x)=f(x_0) + f'(x_0)(x-x_0)+\frac{1}{2!}f''(x_0)(x-x_0)^2 + \dotsi \\
+\frac{1}{n!}f^{(n)}(x_0)(x-x_0)^n
$$
所以展开$(1+x)^a$
如果对$0$ 值展开的话，就是麦克劳林级数展开,
$$
(1+x)^a = 1 + ax +\frac{a(a-1)}{2!}x^2 + \dotsi
$$
$f^{(2)}(x')$, $x'=\theta x$
In fact using Taylor's formula , we obtain
$$
(1+x)^a = 1 + ax +\frac{a(a-1)(1+\theta x)^{a-2}}{2!}x^2 
$$
其中$0<\theta<1$. Since by assumption, $1+\theta x>0$, this gives
$$
sgn\{ (1+x)^a -a -ax \} = sgn\{ a(a-1) \}, \space x\not =0\\
$$
通过这个式子来完成对上式$(5)$的证明。正确.

## 0.3 Chebychev's Inequality
If
$$
a_1\leqslant a_2 \leqslant \dotsi \leqslant a_n \space and \space b_1\leqslant b_2\leqslant \dotsi \leqslant b_n \tag{1}
$$
then Chebychev's inequality states:
$$
\big( \frac{1}{n}\sum_{v=1}^{n}a_v \big)\big( \frac{1}{n}\sum_{v=1}^{n}b_v \big) \leqslant \frac{1}{n}\sum_{v=1}^n a_vb_v \tag{2}
$$
算术平均值之积小于点乘的算术平均值
也就是要证明:
$$
\tag{3} n\sum_{v=1}^na_vb_v \geqslant\sum_{v=1}^na_v \sum_{v=1}^nb_v 
$$
Proof：
1. Let $\sum a\equiv \sum_{k=1}^{n}a_k, \sum b\equiv \sum_{k=1}^{n}b_k,\sum c\equiv \sum_{k=1}^{n}c_k$

then, 
$$
\sum_{u}\sum_{v}(a_ub_u-a_ub_v)\equiv \sum_{u}(na_ub_u -a_u\sum b)\equiv n\sum ab -\sum a \sum b\\[0.5em]
\sum_{u}\sum_{v}(a_vb_v - a_vb_u)\equiv \sum_{v}(na_vb_v-a_v\sum b)\equiv n\sum ab - \sum a\sum b \\
$$
Hence,
$$
\begin{aligned}
    n\sum ab - \sum a\sum b &\equiv \frac{1}{2}\sum_{u}\sum_{v}(a_ub_u - a_ub_v + a_vb_v-a_vb_u)\\
    &\equiv \frac{1}{2}\sum_{u}\sum_{v}(a_u-a_v)(b_u-b_v )\\
\end{aligned}
$$
这里的推导要结合上一行才可以理解。
我们知道，$(a_u-a_v)(b_u-b_v) \geqslant 0$, $(u,v=1,2,\dotsi,n)$
因为前者后者，要么都为正，要么都为负
所以 $n\sum ab - \sum a\sum b \geqslant 0$
If and only if
$a_1=a_2=\dotsi=a_n$ or $b_1=b_2=\dotsi=b_n$

Proof 2,
还要用证明2，作者真的是精力充沛啊！也许他觉得是小菜一碟，举手之劳呢。
Let
$$
a_1=p_1,a_2-a_1=p_2,\dotsi,a_n-a_{n-1}=p_n,\\
b_1=q_1,b_2-b_1=q_2,\dotsi,b_n-b_{n-1}=q_n\\
$$
with $p_v \geqslant 0, q_v \geqslant 0$, $v=2,3,\dotsi,n$, 这里是从$v=2$ 开始，注意了。$(2)$ 式可以写成
$$
n\sum_{v=1}^{n}\big(\sum_{i=1}^{v}p_i \big)\big( \sum_{j=1}^{v}q_j \big) \geqslant \big( \sum_{i=1}^{n}(n+1-i)p_i \big)\big( \sum_{j=1}^n(n+1-j)q_j \big)
$$
能想出这个式子，真的不简单。
or
$$
\sum_{i,j=2}^n n[n+1-max(i,j)]p_iq_j \geqslant \sum_{i,j=2}^n(n+1-i)(n+1-j)p_iq_i
$$
上面这个不等式的右边，实际上就是简单的展开。不等式的左边，看起来就是这样，因为显然$n \geqslant [n+1-min(i,j)]$
Since
$$
(n+1-i)(n+1-j)\equiv [n+1-max(i,j)][n+1-min(i,j)]
$$
the last inequality becomes
$$
\sum_{i,j=2}^{n}[n+1-max(i,j)][min(i,j)-1]p_ip_j \geqslant 0
$$
This second proof is due to D. Djokovic.

**Generalization**
归纳, If
$$
0 \leqslant a_1 \leqslant a_2 \leqslant \dotsi \leqslant a_n \\
0 \leqslant b_1 \leqslant b_2 \leqslant \dotsi \leqslant b_n \\
0 \leqslant c_1 \leqslant c_2 \leqslant \dotsi \leqslant c_n \\
$$
then
$$
\frac{\sum a}{n}\frac{\sum b}{n}\dotsi\frac{\sum c}{n} \leqslant \frac{\sum ab\dotsi c}{n}
$$

举个例子:
If $a,b,c$是正数, $n$ 是个自然数，也就是大于零的整数, then
$$
(a+b+c)^n \leqslant 3^{n-1}(a^n + b^n + c^n)
$$
证明:
$1^\circ$,  不等式$(3)$ 取等号当且仅当$a_1=a_2=\dotsi=a_n$ 或者 $b_1=b_2=\dotsi=b_n$ 才成立
$2^\circ$ ,在归纳的切比雪夫不等式里，$a_n,b_n,c_n$都是大于等于0的数。
什么意思？证明没证明呢?

## 0.4 Abel's Inequality
阿贝尔不等式



