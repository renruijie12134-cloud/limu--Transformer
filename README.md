# Transformer from Scratch (PyTorch)

> 从零实现 Transformer（基于 PyTorch），深入理解 Attention、Mask 机制以及 Seq2Seq 训练与推理流程
## 📖 项目简介
本项目基于 PyTorch 从零实现 Transformer 模型，目标是深入理解其核心结构与训练机制，而非仅调用现成框架。
在实现过程中，完整覆盖了 Transformer 的关键组件，包括：
- 多头注意力机制（Multi-Head Attention）
- 位置编码（Positional Encoding）
- 前馈神经网络（FFN）
- 残差连接与层归一化（Residual + LayerNorm）
- 编码器-解码器结构（Encoder-Decoder）
- Mask 机制（Padding Mask + Causal Mask）
- 自回归推理（Inference）

同时，项目在一个英法翻译（Seq2Seq）任务上完成训练与推理闭环，并对训练与推理不一致问题进行了详细调试与分析。  
## ✨ 项目亮点
- ✅ 从零实现 Transformer（无 d2l / huggingface 依赖）
- ✅ 手动实现 Mask 机制（解决训练与推理不一致问题）
- ✅ 完整实现 Seq2Seq 训练 + 自回归推理流程
- ✅ 深入分析 KV Cache 与 causal mask 的作用
- ✅ 通过过拟合小数据验证模型正确性（工程验证）
- ✅ 系统调试并解决 Decoder 推理错误问题（核心难点）

## 📂 项目结构
.  
├── notebook/  
│   └── 手写transformer.ipynb   # 主实现代码（模型 + 训练 + 推理）  
├── images/                     # README 与 notebook 用图  
├── data/  
│   └── fra-eng.zip             # 英法翻译数据集  
├── README.md  

## ⚙️ 环境依赖

- Python 3.9+
- PyTorch 2.x
- NumPy
- Matplotlib（可选）

安装依赖：

```bash
pip install torch numpy matplotlib

## 🧪 实验结果
在小规模数据上训练后，模型能够完成基本翻译任务：  
Input:  i didn't know you had company .  
Output: j'ignorais que tu avais de la compagnie .  
但在未见数据上，模型存在语义偏移现象，说明：  
- 数据规模不足
- 词表覆盖有限
- 模型容量受限
## 🔮 后续工作
