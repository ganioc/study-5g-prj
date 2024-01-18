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

