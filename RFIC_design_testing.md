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
