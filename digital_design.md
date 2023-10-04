# <Digital Design>
推荐书籍
* Foundations of Analog and Digtial Electrtonic Circuits
* LVC and LV Low Voltage CMOS Logic Data Book
* The designer's guide to VHDL
* The student's guide to VHDL
* The Verilog Hardware descirption language
* A verilog HDL Primer, 3rd edition,
* System Verilog for Design: A guide to using SystemVerilog for Hardware design and modeling
* SystemC: From the ground up
* The electronic Design Automation handbook
* Reuse Methodology manual for System-On-A-Chop designs
* comprehensive functional verification: The complete industry cycle
* Surviving the SOC revolution
* Computers as Components: Priciples of embedded computing system design
* 

### 1.2 Binary Representation and Circuit Elements
基本逻辑类型
* and
* or
* inverter, 反相
* multiplexer, 选择器

D flip-flop, D触发器

#### 1.3.1 integrated circuits 集成电路
silicon chip, 

minimum feature size,
digital logic IC families, TTL transistor-transistor logic
- use bipolar junction transistors connected to form logic gates,
CMOS complementary metal-oxide semiconductor circuits,
- use field-effect transistors, FET
- 使用n-channel,或者p-channel MOSFET,

#### 1.3.2 Logic Levels
fanout: number of inputs driven by a given output,
small leakage currents: between 2 terminals,
- cause static power consumption,
charging and discharging of load capacitance, 当输出switch between logic levels, 0,1
- dynamic power consumption
上述两种功耗, 
silicon wafer,
P41,
使用HDL， Hardware description language， 以编程语言的形式。

Functional models, 功能模型, 也可以以数学表达式来表达。
- Boolean equations,
- finite state machine notations, 

Structural models, 结构模型,
- 用原理图的方式来表达, 使用模块，模型的连接来表示,

Behavioral models, 行为模型
- assign, 使用数学公式，逻辑公式来表达

EDA, CAD tools, 来设计，使用HDL语言,

Verilog, company called Gateway Design Automation, 被Cadence Design Systems收购


另一种语言是VHDL, 当前还有, SystemVerilog, SystemC, extension of the C++编程语言。

- port
  - output
  - input
- wire,nets,
- instances, 
- components
  - not
  - or
  - mux2, 

verificaiton,验证
- functional verification,
  - 使用模拟仿真，simulation, 
  - formal verification, 
  - model checker, analysis of the model , and proof of the properties is performed by a CAD tool,
- timing verification,
- power verification, 满足功率要求，耗电要求
- manufacturability verification,
- test verification, 

synthesis, 
- automatic refinement and optimization of a model,at a higher level of abstraction into a structural model at a lower level of abstraction
- RTL, register transfer level, 表达行为使用赋值和表达式的方法
- 将RTL model转换成优化过的gate level model,

思考的对象
- digital components
- digital circuits,
- verilog models,描述上述部件的,

### 1.5 design methodolog，设计方法论
设计的系统步骤、过程，
- design,
- verification,
- preparation for manufacture of a product,

设计和验证的分层步骤
- architecture design, 分层设计
- Unit design，单元设计
- Unit verification, 单元验证
- Integration verification, 集成验证

抽象，top-down design, 设计子系统, 将子系统集成在一起, 

FPGA
- mapping,
- palcement and routing,

tapeout for ASIC design,

设计，hardware/software codesign, processor core, or customized hardware, 

combinationalcircuits
- 只与当前输入的状态有关，组合逻辑

Sequential circuits
- 与当前、过去的输入状态有关，包括了存储部件

## chap 2 组合逻辑基础







