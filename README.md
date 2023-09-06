English | [中文版](README_zh.md)



# TLB
This is a tool-learning datasets.


## Data Describetion

We have noticed that there are many high-quality datasets in the field of tool learning, such as [Tool-Bench](https://github.com/OpenBMB/ToolBench)、[Api-Bank](https://github.com/AlibabaResearch/DAMO-ConvAI/blob/main/api-bank/data/all_apis.csv)、[Tool-Alpaca](https://github.com/tangqiaoyu/ToolAlpaca/blob/main/data/train_data.json), etc. 

However, different tool learning datasets do not have a unified data format or evaluation standards for assessing the performance of large models on tool usage. 

Consequently, we collected the aforementioned datasets and performed the following data processing tasks, including aligning the data formats, extracting parser keys, and constructing question-answer pairs. 

Additionally, we have open-sourced a Chinese API-based tool dataset for research and learning purposes in tool learning.


### Data Overview

| DataseName    | language  | ToolRetrieval | Tool Filler  | Tool Parser|
|:--------------|:----------|:--------------|:-------------|:-----------|
|  ToolBench-g1 | en        |  423734/484   |  -           |  -         |
|  ToolBench    | en        |  423734/484   |  44939/484   |  19354/215 |
|  APIBank      | en        |  429/79       |  429/79      |  429/79    |
|  ToolAlpaca   | en        |  5911/198     |  5911/198    |  5803/198  |
|  ToolLuban    | zh        |  10239/234    |  10239/234   |  5605/185  |

- Tool Retrieval：
  - data structure：<query, api_name, api_desc>
- Tool Filler：
  - data structure：<query, api_spec, api_param>
- Tool Parser：
  - data structure：<query, api_spec, response, select_keys

A/B：A/train_data_size + B/test_data_size


### Metrics

- Tool Retrieval：
  - metric：Recall Top@1、Top@3、Top@5, to assess the retrieval effectiveness of the tool dataset
- Tool Filler
  - metric：Accuracy, to assess the ability of tool filler.
- Tool Parser
  - metric：Accuracy, to assess the ability of tool parser.


## Citing & Authors
If you find this dataset helpful, feel free to cite:
```bibtex 
@software{TLB,
  author = {luban},
  title = {Tool Learning Benchmark},
  year = {2023},
  url = {https://huggingface.co/toollearning/tool_benchmark},
}
