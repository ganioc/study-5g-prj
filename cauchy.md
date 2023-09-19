# 柯西不等式的证明
## 中学数学,柯西不等式
设$a_1,a_2,a_3, \dotsi,a_n; b_1,b_2,b_3, \dotsi, b_n$为实数，则有

$(a_1b_1+ a_2b_2+a_3b_3+\dotsi+a_nb_n)^2 \le ({a_1}^2 + {a_2}^2 + \dotsi + {a_n}^2)({b_1}^2 + {b_2}^2 + \dotsi + {b_n}^2)$


## 二维形式
$a,b,c,d \in R$ 
$$
\begin{equation}
\begin{split}
(a^2 + b^2)(c^2 + d^2) 
&= a^2 \cdot c^2 + a^2 \cdot d^2 + b^2 \cdot c^2 + b^2 \cdot d^2 \\
&= a^2 \cdot c^2 + 2abcd + b^2 \cdot d^2 + a^2 \cdot d^2 - 2abcd + b^2 \cdot c^2 \\
&= (ac + bd)^2 + (ad - bc)^2 \\
&\ge (ac + bd)^2
\end{split}
\end{equation}
$$

仅当 $ad -bc = 0$ 时成立

## 三角形式
这里用到了上面二维形式的结论
$$
\begin{equation}
\begin{split}
\Big(\sqrt{(a^2 + b^2)} + \sqrt{c^2 + d^2}\Big)^2
&= a^2 + b^2 + c^2 + d^2 + 2\sqrt{(a^2 + b^2)}\cdot \sqrt{(c^2 + d^2)} \\
&\ge a^2 + b^2 + c^2 + d^2 + 2|ac + bd| \\
&\ge a^2 + b^2 + c^2 + d^2 + 2(ac + bd) \\
&= a^2 + 2ac + c^2 + b^2 + 2bd + d^2 \\
&= (a+c)^2 + (b+d)^2
\end{split}
\end{equation}
$$

## 柯西不等式的应用
### 1 巧拆常数证不等式 

例: 设$a,b,c$为正数且互不相等。

求证:
$$
\frac 2 {(a+b)} + \frac 2 {(b+c)} + \frac 2 {(c+a)}  > \frac 9 {(a+b+c)}
$$

**证明**:
由上式，两边乘以$(a+b+c)$,转换为

$$
(a + b + b + c + c+ a)*(\frac 1 {(a+ b)} + \frac 1 {(b+c)} + \frac 1 {(c+a)})> 9 \\[0.5em]
\Harr  \frac 2 {(a+b)} + \frac 2 {(b+c)} + \frac 2 {(c+a)} > \frac 9 {(a+b+c)}
$$

设 $2x=a+b , \space 2y = b+c ,\space 2z = c+ a$


则所证不等式等价于

$$
\begin{equation}
\begin{split}
\frac 1 x + \frac 1 y + \frac 1 z &> \frac 9 {x+y+z} \\
\frac {(x+y+z)} x + \frac {(x+y+z)} y + \frac {(x+y+z)} z &> 9 \\
1 + \frac {(y+z)} x + 1 + \frac {(x+z)} y + 1 + \frac {(x+y)} z &> 9 \\
\frac {(y+z)} x + \frac {(x+z)} y + \frac {(x+y)} z &> 6 \\
(\frac y x + \frac x y) + (\frac z x + \frac x z) + (\frac y z + \frac z y) &> 6 \\
\end{split}
\end{equation}
$$

因为
$$
(\frac y x + \frac x y) > 2 \\[0.5em]
(\frac z x + \frac x z) > 2 \\[0.5em]
(\frac y z + \frac z y) > 2 \\[0.5em]
$$
所以上式显然成立


### 2 求函数极值
例：求函数$y=3 \sqrt{(x-5)} + 4 \sqrt{(9-x)}$的极大值

解：
已知$x$的定义域为 $x \in [5,9] , y > 0$

$$
\begin{equation}
\begin{split}
y &= 3 \sqrt{(x-5)} + 4 \sqrt{(9-x)} \\
&\le \sqrt{(3^2 + 4^2)}\sqrt{(x-5) + (9-x)} \\
&= 5*2 \\
&= 10
\end{split}
\end{equation}
$$

仅在$4\sqrt{(x-5)} = 3\sqrt{(9-x)}$时，

即$x=6.44$时取到最大值$10$



