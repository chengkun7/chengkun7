# 👋 你好，我是蔡承坤

> 北京理工大学硕士研究生  
> 寒武纪深度学习框架研发实习生  
> 方向：AI Infrastructure / 深度学习框架 / AI 编译器 / 大模型训练系统

目前主要参与 **PyTorch/MLU 深度学习框架、TorchInductor 编译链、高性能计算后端及研发效能基础设施**相关工作。

我的长期方向是 **AI Infrastructure**，希望持续深入模型、框架、编译器、运行时与硬件之间的完整技术链路。

## 🎯 核心方向

- **深度学习编译器与高性能计算**
  - PyTorch、TorchInductor、FX、AOTAutograd
  - 编译后端、代码生成、Autotune、AOT 部署
  - GEMM、GroupGemm、低精度矩阵计算

- **大模型训练系统**
  - Megatron-LM、FSDP/HSDP
  - 分布式通信、显存分析、通信计算重叠
  - 多卡训练性能与稳定性优化

- **大模型推理系统**
  - vLLM、推理显存管理
  - Prefill/Decode 性能分析
  - Attention 与低精度推理优化

- **torch_mlu 框架**
  - 基于 AI Agent 的代码评审与研发流程自动化
  - C++ API/ABI 兼容性分析与版本发布质量门禁
  - PyTorch 主线演进下的框架补丁漂移检测
  - CI 自动化工程优化与框架长期可维护性建设

## 💻 项目经历

### 1. TorchInductor 高性能计算后端与编译链优化
面向大模型训练与推理场景，参与 TorchInductor 高性能计算后端建设：
- 打通 CNTLASS 代码生成、AOT 编译运行、autotune 性能选型全链路，完成 PyTorch 兼容性交付
- 建设基于 MLU Event 的 `MLUInductorBenchmarker`，支持候选 Kernel 的设备侧性能测量 
- 接入 GEMM / GroupGemm / scaled_mm 等核心矩阵计算算子，覆盖 fp32/fp16/bf16/fp8 多精度
- 实现动态 Shape 编译复用、分桶调度与算子融合优化，降低重复编译开销与性能波动

### 2. 大模型分布式训练吞吐、通信与显存优化
针对 Qwen / Llama 等大模型多机多卡训练场景，开展全链路性能与显存优化：
- 定位并修复分布式训练中通信算子内存泄漏、显存冗余等底层问题，支撑大模型长周期稳定训练
- 适配 CNCL 非阻塞通信接口，实现通信计算 Overlap 优化，提升多卡线性加速比
- 基于 Megatron-LM / TorchTitan 训练框架，开展 FSDP / HSDP 等并行策略的适配与调优
- 结合 Profiler 工具链分析训练瓶颈，输出 tokens/s、step time、峰值显存等核心指标的优化方案

### 3. LLM 推理引擎显存与服务性能优化
面向 vLLM / TGI 等推理服务场景，聚焦显存治理与服务性能提升：
- 优化权重加载阶段的内存分配策略，降低显存碎片与冗余占用，提升单卡模型部署规格
- 治理 Prefill 阶段显存碎片问题，优化 BlockAllocator 分配与回收机制，提升最大并发 Batch 能力
- 打通 scaled_mm / SDPA 等低精度计算路径，适配 GQA / FlashAttention 等推理优化技术
- 定位并修复推理服务随机崩溃、异步拷贝异常等稳定性问题，保障线上服务可用性

### 4. AI Agent 与 torch_mlu 研发效能平台建设
面向 PyTorch/torch_mlu 框架研发与版本演进，参与建设研发自动化平台：
- 设计并落地 GitLab MR 触发的 Codex Review 服务，支持多任务并发调度、评审规则解耦、结果自动回写与重复任务去重
- 建设 torch_mlu C++ API/ABI 自动兼容性检查流程，支持公共接口变更识别、差异报告生成与版本发布质量门禁
- 建设框架版本演进下的 Gorilla monkey patch 与 inherited override 补丁适配检测，输出结构化问题原因、代码差异和修复建议

## 🌱  开源参与
- **[Relax](https://github.com/redai-infra/Relax)**：小红书大模型 Infra 团队开源的多模态大模型 RL 后训练框架，参与框架性能优化与生态共建
- 持续关注 PyTorch、vLLM、Megatron-LM 等开源社区前沿技术，参与 AI 框架与大模型基础设施相关的开源贡献

## 🛠️ 技术方向与知识栈

### 编程语言
`C语言` `C++` `Python` `Shell` `linux`

### 深度学习框架
`PyTorch` `torch_mlu` `Autograd` `Dispatcher` `ATen` `Custom Operators`

### AI 编译器
`torch.compile` `TorchDynamo` `FX` `AOTAutograd` `TorchInductor` `Graph Optimization` `Lowering` `Codegen`

### 高性能计算
`GEMM` `GroupGemm` `Attention` `算子融合` `低精度计算` `Kernel Autotune` `性能分析`

### 分布式训练与训练框架
`Megatron-LM` `FSDP/HSDP` `TP/PP/DP/EP` `Collective Communication` `通信计算重叠` `训练显存优化`

### 推理框架与推理优化
`vLLM` `Continuous Batching` `KV Cache` `Prefill/Decode` `Attention Optimization` `量化与低精度推理`

### AI 加速芯片与异构计算
`Cambricon MLU` `MLU Architecture` `CNToolkit` `CNCL` `设备内存管理` `异构后端适配` `多卡互联`

## 📫 联系我
- 邮箱：3220240409@bit.edu.cn
- 期待与同行交流 PyTorch、TorchInductor、AI 编译器、大模型训练与推理系统相关技术!
