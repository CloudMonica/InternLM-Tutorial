# LMDeploy大模型量化部署
## 大模型部署背景
### 大模型特点
#### 内存开销巨大
- 参数量庞大，7B大概要14G+内存（16bit半精度=2字节）
- 采用自回归生成token（即token by token生成，需要缓存前面的token内容），需要缓存Attention的k/v，带来巨大的内存开销
#### 动态shape
- 请求数不固定
- Token逐个生成，数量不固定
#### 相对视觉模型，LLM结构简单
- Transformers结构，大部分是decoder-only

### 大模型部署挑战
#### 设备
- 如何应对巨大的存储问题？消费级显卡，手机如何部署
#### 推理
- 如何加速token生成速度
- 如何解决动态shape，让推理不间断
- 如何有效管理和利用内存
#### 服务
- 如何提升系统整体吞吐量？
- 对于个体用户，如何降低响应时间？

### 大模型部署方案
#### 技术方案
- 模型并行
- 低比特量化
- Page Attention
- transformer计算和访存优化
- Continous Batch

#### 方案
- 云端：Imdeploy，vllm，tensort-llm，deepspeed
- 移动端：llama.cpp，mlc-llm

### LMdeploy核心功能
- 量化
- 推理引擎TurboMind
- 推理服务api server
