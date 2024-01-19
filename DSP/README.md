# Study of Digital Signal Processing
- C++ algorithms for digital signal processing

使用Ninja作为项目build工具

在根目录放置meson.build, 然后运行命令

```shell
meson build
ninja -C build
```

## 数字信号处理基础
离散时间上的量化了的信号，对于计算机来说就是一个数的数组。
输入$x(n)$,操作符为$O(n)$, 输出为$y(n)$。操作符是线性的，非线性的。

操作符对数组序列的作用效果:
1. 提取参数或特征
2. 生成一个特征加强了或笑出了的类似序列
3. 将序列恢复成早一些的状态
4. 对序列进行编码或压缩

一维信号处理，二维图像处理, 

采样定理:
$$
x_s(t) = \sum_{n=-\infin}^{\infin}x(t)\delta(t-nT)
$$

### 1.3 Digital Filters
$$
y(n)=\sum_{q=0}^{Q-1}b_qx(n-1)-\sum_{p=1}^{P-1}a_py(n-p)
$$
这里使用了有限数量的和。

#### 1类
第一类数字滤波器, $a_p$都为零,FIR, finite impulse response, 有限冲激响应,又被称为moving average filter, MA, 移动平均滤波器, 输出为输入的加权平均值。
$$
y(n)=\sum_{q=0}^{Q-1}b_qx(n-q)
$$

FIR滤波器的系数，就是冲击响应的序列值,


#### 2类
第二类为IIR, infinite impulse response, 无限冲激响应滤波器, AR, auto regressive filters, ARMA filters,
$$
y(n)=x(n)-\sum_{p=1}^{P-1}a_py(n-p)
$$

需要注意stability问题，稳定性问题, 


#### FIR
设计方法

1. use of the DFT on the sampled frequency response
2. Optimal mini-max approximation using linear programming techniques, Remez exchange algorithm, Parks-McClellan program, **REMEZ.c**

FIR的频率响应

$$
H(z)=\frac{Y(z)} {X(z)}=\frac {\sum_{q=0}^{Q-1}b_qz^{-q}} {1+ \sum_{p=1}^{P-1}a_pz^{-p}}
$$

对于FIR
$$
H(z)=\sum_{q=0}^{Q-1}b_qz^{-q}
$$

有一类FIR滤波器的多项式可以分解因式为
$$
H(z)=\prod_{m=0}^{M-1}(z^{-2}+\alpha_mz^{-1} + \beta_m)\prod_{n=0}^{N-1}(z^{-1}+\gamma_n)
$$
可以方便的求0，

#### FIR linear phase
$b_0=b_{Q-1}, b_1=b_{Q-2}$

#### 1.3.5 滤波器参数

* passband ripple, $2\delta$
* Stopband attenuation, $1/\lambda$
* Transition start and stop frequencies, $f_p$ and $f_s$
* Cutoff frequency, $f_{p^{'}}$, 1dB, 3dB

#### 1.3.6 滤波器的形式
直接形式，串联形式，并联形式



