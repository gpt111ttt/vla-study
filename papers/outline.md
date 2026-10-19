# 大纲 · π0: A Vision-Language-Action Flow Model for General Robot Control

行号指 `paper.tex`。读某一节：`sed -n '起,止p' paper.tex`（或用 Read 的 offset/limit）。

- L82 摘要
- L88–113 1 Introduction
- L114–131 2 Related Work
- L132–138 3 Overview
- L139–162 4 The π0 Model
- L163–217 5 Data Collection and Training Recipe
  - L168–184 5.1 Pre-training and post-training
  - L185–189 5.2 Language and high-level policies
  - L190–217 5.3 Robot system details
- L218–354 6 Experimental Evaluation
  - L231–262 6.1 Evaluating the base model
  - L263–288 6.2 Following language commands
  - L289–320 6.3 Learning new dexterous tasks
  - L321–354 6.4 Mastering complex multi-stage tasks
- L355–362 7 Discussion, Limitations, and Future Work
- L363–368 Acknowledgements
- L367 —— 附录 ——
- L369–498 A （无标题，多半是附录开头）
  - L371–393 A.1 Contributions
  - L394–414 A.2 Model Architecture Details
  - L415–420 A.3 Non-VLM Baseline Architecture
  - L421–445 A.4 Inference
  - L446–498 A.5 Evaluation Details

## 公式（2 个，按出现顺序；L 后面是所在小节）

- L148 §4 The π0 Model：L^\tau(\theta) &= \E_{p(\bA_t | \bo_t), q(\bA_t^\tau | \bA_t)} || \bv_\theta(\bA_t^\tau, \bo_t) - \bu(\bA_t^\t…
- L154 §4 The π0 Model：\bA_{t}^{\tau + \delta} = \bA_{t}^{\tau} + \delta \bv_\theta(\bA_t^\tau, \bo_t),

图表的页码、caption、在哪节被引用：见 `figures/index.md`。
