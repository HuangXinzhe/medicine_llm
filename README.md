# medicine_llm

智源行业数据应用大模型挑战赛——医学数据赛道（开发者组）  

参赛过程笔记仓库

## 目录结构
- prompt：利用原模型，对prompt进行修改，使用比赛结果优化
    - glm_test.ipynb：使用glm4-9b-chat模型
- fine-tune：模型微调
    - llm_sft_lora_modelscope.ipynb
- dataset_analysis_modelscope.ipynb：对数据进行分析

## 想法
1. 比赛结果分为两类：一类是医学问答题的回答，一类是医学选择题的回答（选择题回答仅需生成正确选项即可）。
2. 在使用微调数据对模型微调时出现的问题：因为选择题的答案很短，导致微调后模型对医学问答题的回答效果变差（大段的几个字几个字的不断重复）
3. 直接使用模型不做微调，仅对提示词进行修改，可以提升模型的效果。
4. 尝试了THUDM/glm-4-9b-chat和Qwen/Qwen2.5-7B-Instruct两个模型，发现THUDM/glm-4-9b-chat在指令遵循上的效果更佳（比如：指定医学选择题仅输出正确选择，THUDM/glm-4-9b-chat可以完成的很好，但是Qwen/Qwen2.5-7B-Instruct没有办法做好）
