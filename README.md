# Transformer



## 📰 项目介绍

- 本项目手工实现了完整的 **Encoder-Decoder Transformer** 架构，基于 IWSLT2017 数据集完成英语→德语的机器翻译任务。核心目标是深入理解 Transformer 的底层原理（多头注意力、位置编码、残差连接等），并验证模型在小规模序列到序列任务上的性能。

- 完整复现 Transformer 原论文核心模块（多头注意力、FFN、位置编码、残差连接 + 层归一化）

  ✅ 支持多 GPU 并行训练（适配单 / 多卡环境，已在双 RTX 4090 上验证）

  ✅ 实现带重复惩罚的束搜索解码，提升翻译流畅度

  ✅ 包含完整的数据预处理流程（词汇表构建、序列截断 / 填充、掩码生成）

  ✅ 训练日志可视化（损失曲线）+ 可复现实验配置

  ✅ 支持消融实验（可快速关闭位置编码、多头注意力等组件验证作用）

## 环境配置

```python
conda create -n transformer python=3.9.12
conda activate transformer
pip install -r requirements.txt
```

##  数据集
### 1. Data Preparation
##### 使用IWSLT2017英德翻译数据集，下载流程如下：

1.下载数据集：IWSLT2017en-de数据集

2.解压后将所有文件放入项目目录：./iwslt17_data/

3.数据集结构要求如下：

```bash
./iwslt17_data/
└── train.tags.en-de.en
├── train.tags.en-de.de
├── IWSLT17.TED.dev2010.en-de.en.xml
├── IWSLT17.TED.dev2010.en-de.de.xml
├── IWSLT17.TED.tst2010.en-de.en.xml
└── IWSLT17.TED.tst2010.en-de.de.xml
```

### 2. Training

```
python transformer.py
```


### 3. Evaluation


##### pre-trained model

```
通过网盘分享的文件：transformer_iwslt_en_de_4090.pth
链接: https://pan.baidu.com/s/1JRC4e32VfxbEDk6ZDUIeaQ?pwd=246f 提取码: 246f
```

# 致谢
基于 Vaswani et al. (2017)《Attention Is All You Need》原论文实现
数据集来源于 IWSLT2017 机器翻译任务官方数据集
部分实现参考 PyTorch 官方文档与开源社区最佳实践

