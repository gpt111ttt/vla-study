# 后续写笔记的固定流程 


### 后续写笔记的固定流程

```bash
cd ~/vla-study
nano notes/02-xxx.md      # 写新笔记
git add .
git commit -m "添加 xxx 笔记"
git push
```

### 继续读代码

你之前准备读的几个文件还没看，建议顺序：

1. `prismatic/vla/action_tokenizer.py` —— 配合你刚写的笔记对照
2. `prismatic/models/vlms/prismatic.py` —— VLM 骨架
3. `prismatic/models/load.py` —— 模型加载
4. `vla-scripts/deploy.py` 剩余部分 —— 推理服务

每读完一个，就在 `notes/` 里加一篇。读代码 + 写笔记 + Git 提交，这个循环本身就是最好的练习。

---

继续读 `action_tokenizer.py`，把代码或疑问发过来，我帮你逐段解释。
