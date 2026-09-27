# Action Tokenizer 笔记

## 核心作用
把连续动作 `[0.1, -0.3, ...]` 离散成 token id，
让语言模型能像生成文字一样生成机器人动作。

## 关键方法
- `encode` / `__call__`：动作 → token id
- `decode_token_ids_to_actions`：token id → 连续动作

## 我的理解
OpenVLA 把机器人动作当成一种"语言"，
VLM 生成动作 token，再由 tokenizer 解码成真实动作向量。

## 待解决的问题
- 256 个 bin 是怎么划分的？
- `unnorm_key` 在反归一化里起什么作用？
