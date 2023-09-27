# RFIC design and testing for Wireless Communication

For engineers who plan work on RFIC but did not have training in that area, those who work on ICdesign and wish to sharpen their understanding of modern RFIC design and test methods, and engineering managers.

Specific topics include semiconductor technologies for RF circuits used in a wireless communication system：
* basic characteristics of RF devices,
  * linearity
  * noise figure
  * gain
* RF front-end design
  * LNA
  * mixer
* Frequency synthesizer design
  * PLL, Phase Locked Loop,
  * VCO, voltage controlled oscillator,
* concepts of analog, mixed signal ,
  * RF testing
  * built-in self-test,
* distortion theory, 
  * measurement
  * test
* noise theory,measuremnt , test
* RFIC SOC, and testing,

## outline
- 介绍RF通讯中使用的VLSI器件
  - SoC and SIP
  - functional components
  - 技术
- 设计概念
- 测试概念
  - 基本RF测量
  - 失真特性
  - 噪声
  - SoC测试和built-in self-test(BIST), 内置自检


super heterodyne transceiver,

zero IF transceiver,

RF- Baseband(ADC, DAC, demodulator, modulator) - DSP,

## 射频系统的部件
- Radio Frequency
    - Duplexer, 双工器, 
      - TDD, RF switch, PIN or GaAs FET,
        - 低插损，1dB
      - FDD,
        - Tx to Rx coupling, -50dB,
        - more loss than TDD, 3dB,
        - Adjacent channel leakage
    - LNA, 低噪放
      - 放大收到的RF信号
      - 典型的特性
        - Noise Figure, 噪声系数, 2dB
        - IP3, -10dBm
        - Gain, 15dB
        - 输入输出阻抗， 50ohm
        - 反向隔离度，20dB
        - stability factor, 稳定因子，> 1,
      - 技术，
        - Bipolar
        - CMOS,
    - PA,功率放大器
      - 放大RF信号输入给天线，发送出去
      - 典型特性
        - 输出功率，20~30dBm
        - 效率，30~60%
        - IMD, -30dBc
        - Gain,增益，20~30 dBm
        - 输出谐波，-50~-70 dBc,
        - 功率控制, power control, on-off或1-dB steps
        - stability factor, > 1,
      - 技术
        - GaAs
        - SiGe,
    - RF mixer, 混频器
      - 典型特性
        - 噪声系数，Noise Figure, 12dB
        - IP3, 5dBm,
        - Gain, 10dB
        - input impedance, 50欧姆
        - port to port isolation,端口隔离度, 10~20dB
      - 技术，
        - Bipolar,
        - MOS,
      - 有源混频器
      - 无源混频器，
    - LO, 本振
      - 给混频器提供上变频和下变频的参考信号
      - 实现
        - tuned feedback amplifier,可调反馈放大器
        - Ring oscillator,
        - PLL
        - DDS, Direct digital synthesizer,
      - Phase Splitter,
        - 将输入信号分成两个相差为90度的信号
        - Used for image rejection, 镜像抑制,
    - Filter，滤波器
- 中频
  - VGA，可调增益放大器
  - Modulator,调制器
  - Demodulator, 解调器
  - Filter, 滤波器 
- Mixed-signal,混合信号部分
  - ADC, 模数转换器
  - DAC, 数模转换器
- Digital部分
  - 数字信号处理，DSP,

SOC: System on a Chip
- 所有的系统的部件都在同一个VLSI chip上实现
- 所有的器件都用同一种技术实现，通常是CMOS
- 无法实现SOC的器件，
    - 天线，Antenna,
    - PA, 功率放大器
  
**SIP**, System in Package,
- 在一个封装里包含多个chip或SoC,
- SIP中的走线可以是在半导体的基底上实现的
- Rf通讯系统可以包含
  - SIP, 包含了
    - SOC
      - CMOS 数字和混合信号器件，DSP, ADC, DAC,
      - CMOS LNA和混频器
      - CMOS DDS,
      - 滤波器
    - PA
    - Antenna, 天线
  
## 第2讲 RF Design 射频设计
### Frequency synthesizer design, 
* N is an integer, minimum step size = $f_r$, to get a smaller step size, the reference frequency must be made smaller
* N must be higher in order to generate the same $f_0$
* larger phase noise, in-band noise magnified $20logN$ times by the loop, N指越大，相位噪声越大

### fractional-N频综
* $N=K/F$,
* minimum step size = $f_r/F$, 可以获得小的step size, 在不改变参考频率的情况下
* loop divisor $N$可以小一些，带来较小的相位噪声
* Dual-modulus divider, P/P+1, toggling between the 2 integer division rations, a fractional division ratio, by time-averaging the divider output. average divsion ratio, 可以获得分数比,

$$
f_0=\frac{f_r}{R}[\frac{(P+1)K + P(F-K)}{F}]=\frac{f_r}{R}[P+\frac{K}{F}] \\[0.5em]
StepSize = \frac{f_r}{R\cdot F}
$$

* Fractional-N Frequency Synthesizer with a Multi-Modulus Divider
$$
N_{NMD} = P_1 + 2^1 P_2 + \dotsi + 2^{n-2}P_{n-1} + 2^{n-1}P_n + 2^n \\
f_0 = \frac{f_r}{R}[I + \frac{K}{F}]
$$

任何在时域的重复的模式，都会在频域产生杂散tones, 产生谐波，multiple of the carryout frequency $f_r(K/F)$, step size 的谐波, 

### PLL Frequency Synthesizer
PFD, 鉴相器
$$
v_e(s) = K_{PD}({\theta}_R - {\theta}_0)  \\
i_d = K_{CP} K_{PD} (\theta_R - \theta_0) \\
$$

Loop Filter, 环路滤波器
$$
v_c =\frac{K_{PD}K_{CP}({\theta}_R - {\theta}_0)(1+ sC_1R)}{s(C_1 + C_2)(1+sC_sR)} \\[0.5em]
C_s = \frac{C_1C_2}{C_1 + C_2}
$$
幅度频率响应在$\frac{1}{RC_1}, \frac{1}{RC_s}$之间

$$
\theta_{0} = \frac{1}{N} \cdot \frac{K_{VCO}}{s} \\
$$

$C_2$ about $C_1/10$添加了一个高频的pole, to clean up high frequency ripple on the control line. 

### 开环、闭环传输函数
* natural frequency
* damping constant, > 1, < 1时会有跳变
* tri-state PFD circuit, 
* PFD dead zone, in-band noise, VCO noise, thermal noise floor
* Differential Charge Pump Circuitry

$2^{nd}$ Order Passive Loop Filters,二阶滤波器时最高阶的可以不串联电阻，在charge pump和VCO tune line之间的滤波器电路,

$3^{rd}$ Order Passive Loop Filter, 

PLL Phase Noise and Spurs,

Spectrum analyzer basic block diagram,
Getting the best sensitivity 
- narrowest resolution bandwidht
- minimum RF attenuation
- sufficient video filter to smooth noise(VBW < 0.01 Resolution bandwidh)

相位噪声的源头:
* LP, 来自频率参考源，in band noise
  * refrence ,
  * phase detector
  * LPF,
  * dividers, 20LogN dB, N越小，越好
* NTF, 环路滤波器，
* HP, out of band noise, 带外的噪声
  * VCO的相位噪声, 
  * Flicker $1/f$ noise, 
  * $Q_L$, loaded Q of the 谐振回路, 5~20 on chip resonator, 40~80 for off-chip tank,
  * F, oscillator effective noise factor,

仿真后的相位噪声, 0.1kHz -80dBc/Hz, 100kHz, -90dBc/Hz, ${0.5}\degree rms$


## 第3章 射频设计II
振荡器的相位噪声指标
$$
PN=P_0/N_0
$$
载波与噪声之比,

添加负阻抗、给震荡单元，克服损耗，维持震荡,并联，串联

VCO output spectral purity,

## 第4章 Power and Gain Measurement, 功率和增益测量
测试和verification不同，
* production testing,
  * 对每个生产出的器件都要进行测试，
  * 主要考虑，减少测试费用，减少单位测试时间
  * 最大化质量，减少不良率，定义为不良器件通过测试的比率
* characterization testing,

ATE（自动测试设备, Automatic Test Equipment）系统

```c
User Interface, Test Program,
Test Computer, 
    DSP
    RF sources
    Signal Generators
```

Handler(Feed robotics, Binning)
```c
DUTs
Contactors
Probe Cards
Load Boards
```

Production ATE features:
- Binning, 
  - Passsing the entire test
  - Failing any of the tests
  - Failing because of dc test
  - Failing because of RF Test
  - Failing speed test (maximum clock frequency)
- Multisite testing,
  - 并行、同时测试多个器件，以节省测试费用
- Test time for a typical device, 1~2 seconds
- Testing cost of a device: 3~5 cents,

**characterization testing**
- 在生产阶段的开始，进行的测试
- 目标: 验证设计、可生产性和测试程序
- 方法
  - 几乎没有器件测试会完全顺利
  - 诊断故障
  - 比生产测试的项目更加的详细
  - 测试时间、测试项目、测试费用并不是问题
  - 测试程序需要验证和修改
  - ATE系统，和附加的实验室装置需要使用

**射频测试**
- 基本测试
  - 散射参数，S-参数
    - RF功能作为一个两端口器件，
    - S11, S12, S21,S22
    - $20*log|S_{ij}|$
    - 使用网络分析仪，Network Analyzer,
    - 方向耦合器, Directional Coupler,
  - 频率和增益测量
    - Gain, $S_21$, Gain Flatness, 
  - 功率测试
    - 接收机
      - minimum detectable RF power
      - Maximum allowed input power
      - Power levels of interfering tones,
    - 发射机
      - Maximum RF power output,
      - Changes in RF power when automatic gain control used
      - RF power distribution over a frequency band
      - Power-Added efficiency
    - Power Unit: dbm, relative to 1mW
    - 
  - 功率效率测试
    - PAE, power added efficiency
      - $PAE=\frac{P_{RF}(output)-P_{RF}(input)}{V_{supply}*I_{supply}}$
      - PAE测量放大器产生的热
      - 在mobile phone, PA consumes most of the power
  - Automatic Gain Control Flatness(SoC DUT)
    - 测量自动增益控制,
    - 测试步骤
      - 设置输入信号的频率和功率级别
      - 设置输出测量设备的动态范围
      - 编程Soc AGC to 1st gain level, trigger receiver
        - Cycle SoC AGC to next level
        - Wait long enough to capture relevant data
        - Cycle to next gain level and repeat through all levels
    - 将时域数据传给主机计算机进行处理
      - gain level -> power
      - 可能会出现missing gain step的情况，由于非线性
        - overshoot等情况
        - Gain errors and missing levels
        - overshoot and undershoot, settling time
        - Finite transition times(non zero time)
        - Varying gain steps -nonlinearity
        - DNL, differential nonlinearity, INL, integral nonlinearity similar to ADC and DAC,
- 失真测试
  - Power Spectrum Measurements
    - Spur测量
      - 在射频输出的范围内，不需要的杂散发射的频率
      - leakage of reference frequency in phase detector of PLL
      - spur会超出通讯系统的信道干扰的标准
      - 完整的频谱测试在初始测试完成，以确定杂散的范围
    - harmonic measurement
      - 载波频率的整数倍点上
      - 半导体器件的非线性、功放的clipping/饱和引起
      - 谐波会和其他的信号交叉调制产生新的频率信号，必须进行测试
    - Adjacent channel interference, 
      - ACPR, Adjacent Channel Power Ratio,
      - ACLR, 
      - 测量发射机性能
- 噪声测试


一些**RF通讯标准**
* 802.11b, 22MHz, 11Mbps, CCK
* 802.11a/g, 16.8MHz, 54Mbps, OFDM, 52 subcarriers, 4 pilots, 48 data channels,
* 802.16a(Wimax), 1.25~20MHz, 75Mbps, OFDM, 256subcarriers, 200 used, 192 data channels
* 802.15(UWB), 528MHz, 53.3~480Mbps, OFDM
* GSM, 0.2MHz, 0.27Mbps, GMSK
* CDMA2000, 1.25MHz, 0.06~0.1Mbps, CDMA
* Bluetooth, 1MHz, FSK,

## 第5章 失真的测试
**失真和线性**
- unwanted change in the signal behavior, referred to as distortion,失真
- 源头是半导体器件，diodes和transistor
- linearity线性
  - 线性的函数, $f(x)=ax + b$
  - 定义，满足加法和乘法结合律

**转移函数**
- 电路的转移函数一般情况下是一个非线性的函数
- 可以表示为一个多项式
  - $v_0 = a_0 + a_1v_1 + a_2v_2$
  - $a_0$为直流分量，可以通过一个电容或高通滤波器移除
  - 对于一个线性电路来说，$a_2=a_3=\dotsi=0$

**非线性对频率产物的影响**
二次方，三次方带来了其它频率的产物，假设输入为$v_i=A \cos{wt}$
$$
cos^{2}wt = (1+\cos{2wt})/2 \\
cos^{3}wt = (3 \cos{wt} + \cos{3wt})/4
$$

**diode二极管的特性**
$I=I_s(e^{\alpha V} -1)$
where $V=V_0 + V_{in}$, $V_0$是直流偏置电压，$V_{in}$是小信号交流信号，$I_s$是饱和电流，$\alpha$是一个常量，与温度和二极管的设计参数有关

使用Taylor serives expansion,泰勒级数展开，用$V_{in}$作为参数用多项式来表示二极管的电流

**线性和非线性电路和系统**
- 线性器件
  - 器件的输出的所有频率的信号都与输入信号的强度有关，成正比
  - 输入没有的频率信号不会出现在输出
- 非线性器件
  - 绝大多数的器件是非线性的
  - 放大器的非线性是不受欢迎的，会带来信号的畸变
  - 混频器的非线性是需要的，频率搬移

**失真的类型和测试**
- 失真的类型
  - harmonic distortion, single tone test
    - 带来谐波，N times the 基频, $N_{th}$ harmonic
    - harmonic会浪费能量、功率
    - 带来干扰
    - 测量方法
      - 输入单频率的信号
      - 基频和谐波频率的信号幅度，进行测量
        - Total harmonic distortion, THD,总谐波失真, for RF
        - Signal, Noise, Distortion, SINAD, for baseband signal
          - $SINAD = 10 log_{10}[\frac{(S+N+D)}{(N+D)}]$
  - gain compression, single tone test
  - intermodulation distortion: 2 tones or multitone test
    - SIMD, Source Intermodulation Distortion
    - Cross Modulation
- 测试方法: 输出频谱测试

**Gain Compression增益压缩**
- 由于非线性产生的功率，造成了基频信号输出的减少，也就是压缩
- 当输入功率增加时，非线性会带来更大的增益压缩
- 标准的测量增益压缩的参数是1dB压缩点
  - $P_{1dB}$对于输入指的是接收机
  - 对于输出来说，值的是发射机
- 测量方法
  - 加入一个频点的信号
  - 测量输出直到gain小于正常值的$1 dB$

**交叉调制 Intermodulation Distortion**
器件对多个频点信号的响应
考虑输入信号有两个频率，$V_i=A\cos{w_1t} + B\cos{w_2t}$
信号输出为
$$
\begin{aligned}
v_0 &= a_0 + a_1(A\cos{w_1t} + B \cos{w_2 t})  DC and fundamental \\
&= + a_2(A\cos{w_1t} + B \cos{w_2 t})^{2} 2nd order terms \\
&= + a_3(A\cos{w_1t} + B \cos{w_2 t})^{3} 3rd order terms \\
\end{aligned}
$$
Hint, use the identity
$$
\cos{\alpha} \cos{\beta} = [\cos{(\alpha + \beta)} \cos{(\alpha - \beta)}]/2
$$

2阶交调产物: $2f1, 2f2, f1+f2, f1-f2$
3阶交调产物: $3f1, 3f2, 2f1\pm f2, 2f2 \pm f1$

**IP3**
测试
- 选择两个频点$f_1$, $f_2$, equal magnitude to the DUT input
- 增大输入信号功率$P_0(dBm)$直到3阶产物在噪底以上
- 测量基频输出功率$P_1$,3阶交调产物$P_3$
- 输出IP3,$OIP3 = P_1 + (P_1 - P_3)/2$
- 输入IP3,$IIP3 = OIP3 - G$
- 基频增长的斜率是1
- IP3增长的斜率是3,

**SIMD**
- 测试DUT的输入已经包含了多个tones时，输入已经包含的交调失真，称为SIMD
- 产生的源头是两个输入源之间的隔离度不够，combiner的非线性
- SIMD必须低于预计的DUT的交调失真的30dBc以下

**Cross Modulation交调**
- 在同样的通带内，多个载波之间产生的交叉调制失真称为交调
- 例子
  - 在有线电视, cable TV, 同样的放大器要放大多个信道
  - OFDM, same amplifier放大带宽内的多个载波
- 测量
  - 打开所有的tones/carriers除了一个信道
  - 测量没有打开的信道上的功率产物
- 参考文献, "A Nightmare for CDMA RF Receiver"

## 第6章 噪声的测试
什么是噪声?
- 射频系统里的噪声，带来有用信号的随机起伏
- 噪声的影响
  - 干扰有用信号
  - 改变信号，带来信息传输的误码
  - 有时，噪声会成为一个错误信号的来源
- 所有的通讯系统的设计和操作必须要克服噪声的影响
- 热噪声
  - white noise, uniform PSD over all frequencies
  - Mean square open circuit noise voltage,
  - $-174dBm/Hz$
- 信噪比, Signal to Noise Ratio,
  - $F=\frac{(S_i/N_i)}{S_o/N-o}$,噪声系数, $F>1$
  - 噪声指数, $NF=10 \log{F} dB$

级联系统噪声系数
$$
F_{sys} = F_1 + \frac{F_2 - 1}{G_1} + \frac{F_3 -1}{G_1G_2} + \dotsi + \frac{F_n -1}{G_1G_2\dotsi G_n}
$$
测量：
- Example
    SoC receiver with large gain so noise output is measurable, 是可以测量的。噪声功率必须必测量设备的噪底要高
- Gain之前测量过了
- Noise factor, $F=\frac{N_0}{kT_0BG}$
  - $N_0$是输出的噪声功率
  - B是测量的带宽
  - 290K, $kT_0= -174dBm/Hz$
- Noise figure, 
  $$
    NF = 10 log(F)
  $$
- This measurement is also done using S-parameters

**Y-Factor**
Y-Factor是hot state的输出噪声与cold state时的输出噪声的比值
$$
Y = N_h/N_c = N_h/N_0 \\
Consider, N_h = kT_hBG, N_c = kT_0 BG \\
Then, N_h - N_c = kBG(T_h - T_0) \\
kBG = (N_h - N_c)/(T_h - T_0) \\
Noise factor, \\
F = N_h/(kT_0BG) \\
    = (N_h/T_0)/(kBG) \\
    = (N_h/T_0)(T_h - T_0)/(N_h - N_c) \\
    = ENR/(Y-1)
$$

**测量Y-Factor的方法**
- Calibration
- 加DUT,不加DUT，测试Y-Factor,
- 根据噪声系数计算公式解一个方程即可
$$
F_1 = F_{12} - \frac{F_2 -1 }{G1}
$$

**Phase Noise**
In time-domain, phase noise is referred to as *jitter*

**Effects of Phase Noise**
- 与随机信号调相类似,
- 2种类型
  - Long term phase variation, 叫做frequency drift,频率漂移
  - Short term phase variation, 叫做相位噪声,
- 定义: 相位噪声是一个正弦载波信号对载波功率之比的傅里叶变换频谱, (power spectral density)
  $$
    L(f) = P_n/P_c(as \space ratio)
  $$

**相位噪声的分析**
$$
[V + \delta(t)]\sin{[wt + \varphi(t)]} = [V + \delta(t)][\sin{wt} \cos{\varphi(t)} + \cos{wt} \sin{\varphi(t)}] \\
\approx [V + \delta(t)]\sin{wt} + [V+ \delta(t)]\varphi(t)\cos{wt}
$$

- In-phase carrier frequency with amplitude noise, white noise $\delta(t)$ corresponds to noise floor. 
- Quadrature-phase carrier frequency with amplitude and phase noise at the same time, 短期相位噪声对应于相位噪声谱

**相位噪声的测量**
测量需要一个低噪声接收机(放大器)和频谱仪
- 接收机的噪底必须比信号的噪底低
- 接收机的本振的相位噪声也要比信号的香味噪声低
- 输入一个Pure tone input (carrier)
- 接入DUT,进行测试，

$$
\begin{aligned}
phase noise, L(f) &= P_offset -P_carrier - 10logRBW \\
&= -73.16 - （-5.30） -10log100 \\
&= -87.86 dBc/Hz
\end{aligned}
$$

**ATE, Automatic Test Equipment**
ATE提供了测试装置
* Digital and memory devices
* Analog devices (analog instrumentation) 模拟设备
* RF器件
  * AWG- Arbitrary waveform generators, 
  * LNA,
  * noise source
  * RF sources,
  * filters,
  * PMU - Power measurement units
  * Spectrum analyzer
  * Test fixtures,夹具, load-boards, handlers
  * 测试成本，chip, 3~5 cents/second

减少测试费用，提高测试效率
* Ping-pong testing, 使用同一套测试设备测试多个handlers
* Multisite testing, 同时测试多个芯片chip,
* Built-in self-test, (BIST), Applicable to SoC and SIP devices
* 使用low-cost testers

使用内置的自测试，显然是一个很好的方法
- BIST for a SoC ZIF transceiver
    在发port,和收port之间增加一个TA(测试放大器)，这样可以自发自收。
  - Test implemented at baseband
  - Loopback between A/D and D/A converters
  - DSP implemented with digital BIST
  - Test amplifier(TA) implemented on chip, is disabled during normal operation
  - A test procedure:
    - Test DSP using digital BIST,
    - Apply RF BIST,
      - Pseudorandom bit sequence generated by DSP
      - Upconverted by transmitter chain and applied to receiver through TA
      - Down converted signal compared to input bit sequence by DSP to analyze bit error rate (BER)
      - BER correlated to relevant characteristics of SoC components
  - Advantage: Low tester cost
  - Disadvantage: Poor diagnosis

**Low-Cost Tester for Wideband RF Parameters**
Tester
- Arbitrary waveform generator(AWG) -> 产生I/Q信号
- RF generator, modulation source -> 产生RF信号
- DUT，待测芯片, SoC或SIP,
- DUT输出到Filter
- RF detector, and buffer amplifier, 
- Digital pin or digitizer, 
- Computer, 对信号进行分析,

**参考文献**
- BiST model for IC RF-Transceiver Front-End
- RF-BIST: Loopback spectral signature analysis
- BIST for power amplifier
  - On-chip test mechanism for Transceiver Power amplifier and Oscillator Frequency
- Low-Cost testing
  - Innovative Technique for Testing Wide Bandwidth Frequency Response,

## 第8章 RF BIST
使用DDS, direct digital synthesizer来实现BIST, 混合信号系统的模拟电路的功能测试，
提供BIST-based测量
    amplifier linearity(IP3)
    Gain, frequency response
Implemented in hardware,
    IP3, gain, frequency response

- Overview of DDS
  - DDS=> deterministic communication carrier/reference signals in discrete time using digital hardware
  - 再使用DAC转换为模拟信号
  - 优点
    - 可以生成多种信号波形，waveforms
    - High precision,精度高, sub-Hz
    - Digital circuitry
      - 体积小，是模拟synthesizer体积的几分之一
      - 成本低
      - 易于实现
- 3rd order intgermodulatoin product, IP3
  - 3阶交调与基频很靠近，所以很关键
  - 2 tone test pattern generator,
    - DA converter, low pass filter, 产生一个2-tone波形,
- BIST architecture
  - Test pattern generator
  - Output response analyzer
    - multiplier/accumulator-based ORA,
    - multiply the output response by a frequency
    - Accumulate the multiplication result
    - average by # of clock cycles of accumulation
      - Gives DC value proportional to power of signal at that frequency
    - Advantage
      - easy to implement
      - low area overhead
      - exact frequency control
      - more efficient than FFT, 
- Experimental results
  - Implementation in hardware
  - IP3 Measurements


**BIST architecture**
- BIST based IP3 measurement
  - Reduce circuit by repeating test sequence at DC2
- BIST-based Gain & Frequency Response is subset
- Test Pattern Generator
- Output Response Analyzer,
- 3 8-bit DDSs, and 2 17-bit ORA accumulators
- Implementation in Verilog
- Synthesized into Xilinx Spartan 2S50 FPGA,
- Amplifier device under test implemented in FPAA
- DAC-ADC PCB












