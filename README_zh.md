[English](README.md) | 中文版

# TLB
这是一份关于tool learning的`tool use`数据集


## Data Describetion

我们注意到在tool-learning方向存在很多优质的数据集，诸如[Tool-Bench](https://github.com/OpenBMB/ToolBench)、[Api-Bank](https://github.com/AlibabaResearch/DAMO-ConvAI/blob/main/api-bank/data/all_apis.csv)、[Tool-Alpaca](https://github.com/tangqiaoyu/ToolAlpaca/blob/main/data/train_data.json)等，但是不同的tool-learning数据集并没有一个统一的数据格式，以及对大模型在tool使用能力上的评估标准。

于是我们搜集了以上数据集，并做了以下的数据处理工作（数据格式对齐、parser-key提取、QA对构建），同时开源了一份基于中文api的tool数据集，用于tool learning的学习研究。


### Data Overview

| DataseName    | language  | ToolRetrieval | Tool Filler  | Tool Parser|
|:--------------|:----------|:--------------|:-------------|:-----------|
|  ToolBench-g1 | en        |  423734/484   |  -           |  -         |
|  ToolBench    | en        |  423734/484   |  44939/484   |  19354/215 |
|  APIBank      | en        |  429/79       |  429/79      |  429/79    |
|  ToolAlpaca   | en        |  5911/198     |  5911/198    |  5803/198  |
|  ToolLuban    | zh        |  10239/234    |  10239/234   |  5605/185  |

- Tool Retrieval：
  - 数据基本结构：<query, api_name, api_desc>
- Tool Filler：
  - 数据基本结构：<query, api_spec, api_param>
- Tool Parser：
  - 数据基本结构：<query, api_spec, response, select_keys>

A/B 数据：A/训练数据量 + B/测试数据量


### Metrics

- Tool Retrieval：
  - metric：Recall Top@1、Top@3、Top@5 来判断其检索有效性
- Tool Filler：
  - metric：Accuracy，直接判断结果是否准确即可
- Tool Parser：
  - metric：Accuracy，根据select_keys来判断结果是否正确


## Citing & Authors
```bibtex 
@software{TLB,
  author = {luban},
  title = {Tool Learning Benchmark},
  year = {2023},
  url = {https://huggingface.co/toollearning/tool_benchmark},
}
