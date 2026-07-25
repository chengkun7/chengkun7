# 👋 你好，我是蔡承坤

> 大模型 AI Infrastructure 方向学习者 | 深度学习框架研发实习生
> 北京理工大学 硕士在读 | 寒武纪 Cambricon 框架研发部实习

## 🎯 核心方向
专注**大模型全栈 AI 基础设施**优化，覆盖从单卡算子编译、多卡分布式训练到端到端推理服务的完整技术链路：
- 深度学习编译器与高性能计算：TorchInductor 编译链、CNTLASS 高性能算子接入、动态 Shape 编译优化
- 大模型分布式训练：Megatron-LM / FSDP 训练框架、通信计算 Overlap、显存优化与通信库适配
- LLM 推理引擎：vLLM 推理服务显存治理、Attention 优化、低精度推理加速
- 跨硬件 AI 框架适配：MLU 硬件架构下的 PyTorch 生态建设

## 💻 当前正在推进
### 1. TorchInductor 高性能计算后端与编译链优化
面向大模型训练与推理场景，在 MLU 平台建设 TorchInductor CNTLASS 高性能计算后端：
- 打通 CNTLASS 代码生成、AOT 编译运行、autotune 性能选型全链路，完成 PyTorch 主线版本兼容性交付
- 接入 GEMM / GroupGemm / scaled_mm 等核心矩阵计算算子，覆盖 fp32/fp16/bf16/fp8 多精度
- 实现动态 Shape 编译复用、分桶调度与算子融合优化，降低重复编译开销与性能波动
- 通过真实大模型 Workload 验证端到端性能收益，建设标准化 Benchmark 与性能回归体系

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

## 🚀 开源参与
- **[Relax](https://github.com/redai-infra/Relax)**：小红书大模型 Infra 团队开源的多模态大模型 RL 后训练框架，参与框架性能优化与生态共建
- 持续关注 PyTorch、vLLM、Megatron-LM 等开源社区前沿技术，参与 AI 框架与大模型基础设施相关的开源贡献

## 🛠️ 技术栈
| 领域 | 技术栈 |
|------|--------|
| 编程语言 | C/C++、Python、高性能算子开发 |
| AI 框架 | PyTorch、TorchInductor、Megatron-LM、vLLM |
| 高性能计算 | CNTLASS、GEMM/GroupGemm、算子融合、低精度计算 |
| 分布式系统 | FSDP、TP/PP/EP、CNCL/NCCL、通信计算 Overlap |
| 工具链 | Profiler、Git、CMake、Docker、Ray |
| 硬件平台 | MLU、GPU、端侧嵌入式芯片 |

## 📫 联系我
- 邮箱：3220240409@bit.edu.cn
- 期待与同行交流 AI Infra、深度学习框架、高性能计算相关技术与工作机会
