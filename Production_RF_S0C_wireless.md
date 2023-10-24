# Productoin Testing of RF and System-on-a-Chip Devices for Wireless Communications

混合信号器件的测试,mixed-signal devices,


**Pick-and-Place**
Using suction, 移动DUT从传送tray到load board contactor socket,
使用步进电机来实现精确控制。
vacuum solenoids, 真空螺线管,
**Index time**
将DUT放入bin(容器、箱子)的时间,一般情况下0.4~0.75秒,

对于RF和Soc测试，4-site 是最佳的测试方法。多于4个的测试场景，一般用来进行数字测试或者BIST, self-testing, memroy devices, 存储器件

环境测试, $-60^\degree \thicksim 160^\degree$, thermal soaking, 使用液氮或者冷冻水, 压缩空气,冷却剂混合物

### 1.7.2 Load Boards
一个印刷电路板，将tester资源汇聚到一起提供给DUT做测试。作为DIB,(DUT Interface Board). 包含
* dc power supply,
* digital control,
* mixed signal line
* RF signal line

另外一个容易忽视的方面是阻抗匹配和调试, 

### 1.7.3 Contactor Sockets,
接触插座, DUT和load board连接的接口, 需求
* 经受高功率
* 对高频信号的失真最小

RF高功率信号, 大电流，特殊的接触材料，大面积的heat sink, 散热片,
低接触阻抗，感抗，容抗，

### 1.7.4 Production RF and SoC Wafer Probing
使用wafer-probing euipment, 使芯片生产厂商可以在封装前对芯片进行测试, 对小型的射频芯片在封装后再进行测试，封装带来的感抗需要CSP(Chip-scale packages)或者flip-chip assemblies. KGD(Known-good-die)

昂贵的MCUM multichip modules封装需要KGD 生产中挑选在微波频率上。此时需要进行wafer级别的探测。Wireless communication die testing,

控制寄生参数，控制阻抗在设计一个探头的时候. RF probe card, limited to blade needel cards,同轴线缆探测，membrane-style probe,薄膜探测, 

探头和测试仪的连接方式有
* Cabling from the tester to the probe card, 使用同轴电缆
* 使用probe interface board, PIB,
* 直接连接

使用wafer probing的射频测试
* ADjacent channel power
* complex demodulation
* digital input-threashold voltage,
* digital output levels,
* power-added efficiency
* frequency accuracy,
* frequency versus time
* gain, gain compression,
* harmonic distortion
* digital modulation quality
* isolation
* sensitivity
* mixer conversion gain or loss,
* mixer leakage
* noise figure,
* intermodulation products,
* phase noise,
* power pulsed power,
* s-parameters,
* suprious signals,
* switching speed,
* VCO frequency
* VSWR,

## 1.8 Calibration 校准
获取到的测量值需要依据校准后的测量，校准的步骤和目的
* common calibration basis point, 对于绝大多数tester, 基本的是NIST, National Institutte of Standards and Technology, 
* 校准功率测量, 
* de-embedding, for packaged-parttesting, 
  * short,
  * open,
  * 50-ohm
  * through连接
* periodic maintenance, 定期校准, 

## 1.9 Test Floor and Test Cell
测试房间，去除静电的影响, shielding enclosure on the load board, a screen room 屏蔽房

## 1.10 Test House,

## 1.11 Accuracy, Repeatability, Correlation,

## 1.12 DFT
Design for Testing, 可测试性设计, 
通过RSSI来验证RF信号的接收，因为无法测量到RF信号,

## Built-in Self-test
BIST, in highly complex digital devices and memory devices,

# chap 2 RF and SoC devices
SOC device的分类
* RF/RF
* RF/IF
* RF/baseband, 
  * 在WLAN modem里面非常常见, 从输入滤波器，LNA, 直到I/Q输出
* RF/digital
  * 在Bluetooth产品里面常见, 架构比较简单, Bluetooth modem,
  * 属于mixed-signal devices, 

SOC frontend也会提供一些数字信号，比如RSSI, AGC, 

LNA

Amplifier,
PA, large gain, fast response,这些需求，需要PA的制造工艺是不同的, GaAs, SiGe, 

Mixer,
* single ended mixer
* double balanced mixer, excellent isolation, 
* image-rejection mixer, 2个$90^{\degree}$相移的信号,

RF Switch,
* absorptive switches,
* reflective switches, 
* 使用的技术有两种
  * PIN, p-type silicon/insulator/n-type , diode switches,
    * us 级别开关时间，大功率,
  * GaAs field effect transistor FET based switches,
    * ns 级别的开关时间, good frequency response to DC,

VGA,
可变增益放大器, 

Modulator,
or I/Q modulator, 现在通常是在SOC上实现的, 
* phase splitter, 90 degree difference, 
  * 影响接收机的误码率，发射机的EVM, 
* mixer不应该影响信号的幅度和相位信息
* Carrier and sidband suppression测试，查看影响, 

Demodulator,
与调制器类似，方向相反, 
* single-ended demodulator,
* differential-ended demodulator, 
  * noise-reduction properties, 
* I/Q信号等幅，相位正交，差90度，需要进行测试,

Transmitter,
测量inband频谱，和带外频谱，locate spurs, 

Receiver,
I/Q信号输入给ADC, 由基带/DSP进行处理, baseband processor,
* 灵敏度指标，也就是noise figure, 
* 输出模拟I/Q, 数字I/Q,

Transceiver,
同时工作，或者分时工作，

## 2.12 Wireless Radio 架构

Superheterodyne,

ZIF,
主要问题是
- dc offset,
  - LO leakage, self-mixes, 在信号通路上产生一个直流偏移,
  - 使用补偿方案来克服,类似于noise cancellation, 跟踪背景噪声，将噪声从信号中减去，提高了信噪比, 
- flicker noise,$1/f$noise, 
- LO pulling, 
  - pulling of the LO by the power amplifier output,功放的输出和LO频率相同，会影响LO, distrub or pull the VCO, 

PLL,
Phase Locked Loop, 产生本振信号,
* synthesizer lock time,
* Free running
* Captured,
* Phase Locked,

系统级别的测试
* BER
* EVM

SoC器件级别的测试
- VSWR
- REturn Loss
- Insertion Loss
- Gain
- Gaint flatness
- Isolation
- Linearity
- Noise figure
- Dynamic range
- Power Compression
- 3rd order intermodulation,
- Third order intecept point, TOI
- Harmonic Distortion
- conversion loss/gain
- Intermodulation distortion,
- switching speed
- bandwidth
- power-added efficiency,
- spurious output
- RF-LO rejection,
- ACPR, ACLR,
- Phase Noise,
- I/Q offset,
- IQ amplitude match
- IQ phase match,
- Output power
- Carrier suppression,
- Error Vector Magnitude, EVM
- 

# chap 3 Cost of Test
## 3.2 Wafer processing improves Cost of Test,
之前测试费用<1%, 后来wafer面积增大，数量级地降低了晶片成本, 
- $6^{''}$ wafer, 152.44mm
- $8^{''}$ wafer, 203.2mm
- $12^{''}$ wafer, 300mm

目前测试的成本占总成本的3~30%, 

# chap 4 measuring voltage VS measuring power,
Tansmission Line Theory VS Lumped-Element Analysis,


## 4.10 average power
$$
P_{AVG} = \frac{1}{nT_i}\int_0^{nTi}V(t) \times I(t) dt
$$
$T_i$是最低频率的周期

## 4.11 Pulse Power
$$
P_{pulse} = \frac{1}{\tau}\int_{0}^{\tau}V(t) \times I(t)dt \\
P_{pulse} = \frac{P_AVG}{Duty cycle}
$$

## 4.12 Modulated Power
For signal shapes that have high peak-to-average ratios, the term *crest factor* is introduced：
$$
\xi = \frac{peak \space value}{rms \space value}
$$
对于正弦信号来说
$$
\xi_{sine} = \sqrt{2}
$$
对于脉冲信号来说
$$
\xi_{pulse} \approx \sqrt{\frac{1}{Duty \space cycle}}
$$

## 4.13 RMS Power
The energy of a dc voltage across a resistor is :
$$
W_s = \int_{t_0}^{t_0 + T}\frac{V^2}{R}dt
$$
If V is a constant dc voltage
$$
W_s = \frac{V^2}{R}T
$$
The energy of a sinusoidal voltage across the same resistor is:
$$
W_s = \int_{t_0}^{t_0 + T}\frac{V_0^2}{R}dt
$$
上两式如果相等的话，我们可以算出等效的电压来
$$
V_{eff} = \sqrt{\frac{1}{T}\int_{t_0}^{t_0 + T}V_0^2(t)dt}
$$
找到式子的均方根,将$V_{eff}$代入功率的计算公式
$$
P = \frac{V_{eff}^2}{R}
$$

## 4.14 Gain
增益
$$
G = P_{out} - P_{in}
$$
变频后的增益叫做conversion gain, 转换增益,因为前后测量的频率不同

下变频的RF mixer,或一个SOC接收机:
$$
G_{receiver} = P_{out} |_{baseband} - P_{in}|_{RF}
$$
上变频的RX mixer或SoC发射机:
$$
G_{transmitter} = P_{out}|_{RF} - P_{in}|_{baseband}
$$
AWG, Arbitray Waveform Generator, 

## 4.15 Gain flatness
$$
Gain\space flatness|_{dB} = G_{max} - G_{min}
$$
带内最大的减最小的增益,

### 4.15.2 Automatic Gain Control Flatness
gain *vs* time frequency sweep is required. 

Ideal AGC device的特性:
* gain-level changes from one level to the next instantaneous
* no overshoot or undershoot directly after the gain-level change
* gain-level changes are linear with the control voltage

An actual AGC device:
* overshoot, undershot occur during a gain transition
* Rise and fall time are not instantaneous
* Varying gain step size,

DNL(differential nonlinearity)

INL(integral nonlinearity), are common for mixed-signal ADCs and DACs

Gain settling time:
* transition time from one gain state to another, operate in the microseconds
* settling time, or bouncing of each gain state, gain settling time should be within the specification

为了使power-vs-time, gain-vs-time, frequency-vs-time transition-type 测量， 测试系统必须可以被触发时域的测量,

测试过程:
- 将输入信号设置为合适的频率和power level
- 将输出测量设备设置为触发状态
- 编程SOC AGC为第一个gain level, 触发接收机捕获输出信号
  - cycle the AGC to the next gain level
  - Wait long enough to capture the relevant data
  - Cycle to the next gain level and repeat until the last gain level has been captured
- 将时域的数据发送给主机进行处理

## 4.16 Power Added Efficiency
$$
PAE(\%) =(\frac{P_{RFOUT}}{P_{RFIN} + P_{dc}})\times 100 \%
$$
$P_dc$是RF power打开时器件的工作电流
$$
P_{dc} = V_{supply} I_{operating}
$$

## 4.17 Transfer Function for RF Devices
大多数的RF器件，都是基于diodes, transistors的，
二极管的曲线
$$
I = I_s(e^{\alpha V_{tot}} - 1)
$$
$I_s$是饱和电流
$\alpha$是一个常数，和温度与二极管、晶体管的结构特性有关
$V_{tot}$是二极管上的直流、交流电压之和
$$
V_{tot} = V_0 + V_{in}
$$
$V_{in}$是一个小信号，小交流信号。可以采用泰勒展开, 

$$
f(x) = f(x_0) + f^{'}(x_0)(x-x_0) + f^{''}(x_0)(x-x_0)^2 + \dotsi  
$$

$$
\begin{aligned}
I &=I_s(e^{\alpha V_{tot}} - 1) \\
&= I_0 + V_{in}\frac{dI}{dV} + \frac{1}{2}V_{in}^2\frac{d^2I}{dV^2} + \dotsi
\end{aligned}
$$
根据欧姆定律，两边乘以$R$,我们得到
$$
V_{out}=\alpha_{0} + \alpha_{1}V_{in} + \alpha_{2}V_{in}^2 + \alpha_{3}V_{in}^3 + \dotsi
$$
所以输出的电压的产物里面存在二次方，三次方的值。

## 4.18 Power Compression
功率压缩, 1-dB压缩点,

## 4.19 Mixer Conversion Compression
RF in输入增加时，输出也应该增加。当输出不再增加的时候，比预期的小1dB时，这就是压缩点

## 4.20 Harmonic and Intermodulation Distortion
harmonic distortion,
测量谐波失真的参数是THD(Total Harmonic Distortion), $\sqrt{\frac{D}{S}}$

SINAD(Signal, Noise, and Distortion)用来衡量接收到的信号的质量。
$$
SINAD(dB) = 10 \log_{10}(\frac{S+N+D}{N+D})
$$


intermodulation distortion,交调失真,
IP3, IM3, IP, 
IP3 point will intercept the linear curve before the IP2 point.
$$
IP3 = P_{fundamenal} + \frac{P_{3rd}}{2}
$$

### 4.21.2 Measuring ACPR
测量方法，将RF下变频到中频，数字采样复数时间电压值，FFT on complex time array, 获得最后的结果。

## 4.22 Filter测试

## 4.23 S-Parameters
Coupler, 
* Directional in nature
* low loss
* good isolation,
* Narrowband and poorer performance at lower frequencies

# Chapt 5 Production Testing of SOC Devices
Wireless SOC devices, functional testing, 

## 5.2 SOC integration levels
radio由2个部分组成, TX, RX, SOC器件的配置

Case 1: RF-to-RF 配置
RF SOC, 包含了各个模块在一个single die上，amplifier mixer, filter,RF based,不需要知道digital, baseband signal testing, Modulator or amplifier mixer combination就是一个很好的例子

Case 2: RF-to-Analog(Baseband)配置
测试系统需要有一路或者多路的模数转换来捕捉模拟信号，RF/mixed-signal SOC, 主要在WLAN SOC配置中发现

Case 3: RF-to-Digital 配置
在Bluetooth中较多，还包含了baseband decoder, 将baseband信号转换为数字的1和0,测试系统必须有数字的能力.RF的知识，数字的知识，包括:clocking, bit rates, digital thresholds, digital compare, digital capture.

一个典型的Bluetooth radio modem包含3大块:
* TX
* RX
* PLL,
  
## 5.15 Synthesizer Settling Time
定义为
- synthesizer收到指令切换信道的时间
- 制定信道的输出功率目标值的10%以内,

testing phase noise, 使用digitizing receiver ,a FFT来获得某个频率上的相位噪声, 
- power versus time
  - 取样频率$f_s=300kHz, T_s=3.33us$,测量精度为$T_s/2$
- differential phase versus time

## 5.19 Digital Control of an SOC
大多数SOC器件使用SPI来编程芯片的不同的模式，功率级别，信道参数等。SPI总线包括clock, data, enable. 

SPI data, 通常是16-bit,或32-bit的串行word,
SPI clock, 1~10MHz, 50% duty cycle, 

## 5.20 发射机测试
parametric measurements, 对于一个SOC来说测试项有4项
- Transmit output spectrum
- Modulation characteristics
- Initial carrier frequency tolerance
- Carrier frequency drift,

不同的测试，需要的payload data是不一样的, 

device 便成为工作在某个信道上，modulator respond to the pseudorandom pattern to produce a modulated RF output, 

测试20dB带宽，必须 < 1MHz,

为了保持测试的精确性，使用FFT, 2-MHz的采样带宽, desired frequency resolution , 频率分辨率为1 kHz, 那么需要的FFT的点数为:
$$
N=\frac{BW}{Freq\space Resolution_{desired}}=\frac{2e^6}{1e^3}= 2,000
$$
取2048个点, 这样的测试会快得多,

### 5.20.2 Modulation characteristics
调制特性, 测试modulator,和本振的稳定性, frequency deviation, pulling effect on the VCO from the power supply, which pulls the carrier frequency from its normal position.

测试系统必须有vector siganl analyzer capabilities, phase和symbol信息都要进行计算。

### 5.20.3 Initial carrier frequency tolerance,
发射载波的频率精确度, ICFT 必须 < 75 kHz, 测量preamble的最初4bit, ICFT test使用了标准的DH1 packet with PRBS 9 data, 1010, 捕获的信号进行频率解调，每个preamble bit的频率偏移进行平均, 

### 5.20.4 Carrier Frequency Drift
蓝牙标准要求symbol timing accuracy of +/- 20ppm, baseband crystal 必须be accurate across all operating conditions, temperatures, and life of the product. 

a worst-case phase error be calculated from the longest packet(DH5), 5 slot long, 2870 us, 
相位误差小于a symbol period的$1/8$, one time slot is +/- 25kHz, 3 time slot is +/- 40kHz, 最大drift rate 必须小于400Hz/s.

### 5.20.5 VCO Drift
直接测试VCO的频率漂移

## 5.20.6 Frequency pulling and PUshing,
Power supply的变化，会带来频率的漂移, 

## 5.21 Receiver Tests
以一个多频段WLAN器件为例

### 5.21.1 Bit Error Rate,
BER
$$
BER\% = \frac{Total \space number\space of \space bad \space bits}{Total \space number \space of \space transmitted \space bits} \times 100
$$

### 5.21.2 Bit Error Rate Methods,

## 5.22 BER Receiver Measurements
* Sensitivity BER
* Carrier-to-interference BER
* Blocking BER
* Intermodulation BER
* Maximum input level BER

## 5.23 EVM Introduction
A time-domain analysis of a modulated signal, 

### 5.23.1 I/Q Diagrams,
Viewing a simple voltage-over-time graph, 

# Chapt 6 Fundamentals of Analog and Mixed-Signal Testing
RF microchip的发展方向就是集成度越来越高了。每一代的芯片看起来都越来越复杂，包含越来越多的模块。RF收发机、混合信号技术都被集成到了一起。

## 6.2 Sampling Basics and Conventions
采样技术基础，

DC offset, 

peak-to-peak voltage, 

假定ATE测试系统的digitizer的输入电压范围为
$$
\plusmn 2V, \plusmn 1V, \plusmn 250mV,
$$
采样的最小分辨率，位数
$$
LSB = \frac{MaxRange}{2^{bits} - 1}
$$
12 bit digitizer, input range $\plusmn 250mV$, step size 为$244 uV$

## 6.3 傅里叶变换和FFT
混合信号工程师，在频域内分析问题, 

傅里叶级数, 所有的周期性信号$x(t)$都可以用正弦函数里的叠加来表示
$$
x(t) = a_0 + \sum_{n=1}^{\infin}(a_n\cos{(nw_0t)} + b_n\sin{(nw_0t)})
$$
$a_0$为直流分量

### 6.3.2 傅里叶变换
傅里叶理解了所有的信号的运行时间都是有限的，因此他接下来试图描述非周期信号的时频对应关系。
$$
X(f) = \int_{-\infin}^{\infin}x(t)e^{-j2\pi ft}dt \\
x(t) = \int_{-\infin}^{\infin}X(f)e^{j2\pi ft}df
$$

### 6.3.3 DFT
离散傅里叶变换
$$
X_d(k) = \sum_{n=0}^{N-1}x(n)e^{-\frac{j2\pi kn}{N}} \\
x(n) = \frac{1}{N}\sum_{k=0}^{N-1}X_d(k)e^{\frac{j2\pi kn}{N}}
$$
A 1024-point sampled time-domain signal, $N^2$计算，为了快速计算，使用快速傅里叶转换算法

算法利用了频域的对称性,冲用了一些seed terms, 提供positive frequency spectrum with fewer calculations. FFT requires only $N\ln{(N)}$步骤的算法，只要N是2的次方数。计算量下降了147倍。

### 6.7.2 INL/DNL for AWGs and Digitizers
如果设备包含12-bits, 4095, or $2^{n-1}$, conversion codes need to be tested. 

For the case of a digitizer , a ramp is programmed into the ATE's AWG. The range of voltage is called the full scale range (FSR),

output pin $-FSR/2$ to $FSR/2$. The ATE then digitizes this ramp and analyzes the results. Called a static measurement because it does not matter how quickly the ramp rises, it just matters that the ATE and DUT are synchronized.

DNL(Differential nonlinearity)
这是第一个static measuremnt, After the conversion, detailed calculations are made that compute the difference between the actual step size and the ideal step size. Once this array is complete, the worst-case or largest DNL is recorded.

INL(Integral nonlinearity)
Can be calculated from the same resultant array as the DNL, The starting and ending points are recorded, and an ideal straight line is made through these points. For each sample, the deviation from this straight line is recorded . the worst-case deviation isrecorded. 

## 6.8 Real Signals and Their Representations.










