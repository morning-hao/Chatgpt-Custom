# 项目根据各位大佬们整合而成，参考链接如下

> 0. 清华官方参考: https://github.com/THUDM/ChatGLM-6B
> 1. LoRA代码参考: https://github.com/mymusise/ChatGLM-Tuning
> 2. 中文数据参考: https://github.com/LC1332/Luotuo-Chinese-LLM

# 一,根据自己的信息修改数据
[trans_chinese_alpaca_data.json](data%2Ftrans_chinese_alpaca_data.json)

一条数据格式如下:

```json
 {
    "instruction": "你身份是什么？",
    "input": "",
    "output": "我叫ChatGLM-6B-custom，是一个由上海的算法工程师eat-or-eat于2023年独立训练和开发的人工智能助手。我的主要目标是协助用户解决问题和满足他们的需求。"
  }
```


# 二,安装环境

pip install -r requirements.txt 

# 三,训练
[finetune.ipynb](finetune.ipynb)

# 四,使用
[infer.ipynb](infer.ipynb)

