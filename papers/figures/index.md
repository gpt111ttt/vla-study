# 图表索引

来源 `paper.pdf`（17 页）：图 14 张、表 1 张。全部裁剪拼在 `figures/_contact.png`，一次看完。

> 讲到哪张图就把那个 PNG 发给用户；讲之前自己先看一眼——caption 不会告诉你图是怎么排的。
> 裁得不对：`crop.py paper.pdf --page P --grid` 看带刻度的整页，再 `crop.py paper.pdf --page P x0 y0 x1 y1 -o figures/fig-NN.png` 重裁（坐标是页面比例 0–1）。

## 图 1 · 第 1 页 · `figures/fig-01.png`
**caption**：Fig. 1: Our generalist robot policy uses a pre-trained vision-language model (VLM) backbone, as well as a diverse cross- embodiment dataset with a variety of dexterous manipulation tasks. The model is adapted to robot control by adding a separate action expert that produces continuous actions via flow matching, enabling precise and fluent manipulation skills. The model can then be used directly to perform tasks based on a prompt, or fine-tuned on high-quality data to enable complex multi-stage tasks, such as folding multiple articles of laundry or assembling a box.
· paper.tex L23 · 源文件 `figures/teaser_fig.pdf`

## 图 2 · 第 2 页 · `figures/fig-02.png`
**caption**：Fig. 2: π0 controls a mobile manipulator to fold laundry. Our model is pre-trained on diverse data from 7 distinct robot configurations and 68 tasks, and can then either be prompted directly or fine-tuned to complex downstream tasks, as in the case of this laundry folding policy, which fetches laundry from a dryer, packs it into a hamper, brings the hamper to a folding table, and then folds each article of clothing.
· label `fig:filmstrip` · paper.tex L92 · 源文件 `figures/fig2_final.jpeg` · 正文引用：§1 Introduction (L112)

## 图 3 · 第 4 页 · `figures/fig-03.png`
**caption**：Fig. 3: Overview of our framework. We start with a pre-training mixture, which consists of both our own dexterous manipulation datasets and open-source data. We use this mixture to train our flow matching VLA model, which consists of a larger VLM backbone and a smaller action expert for processing robot states and actions. The VLM backbone weights are initialized from PaliGemma [5], providing representations learned from large-scale Internet pre-training. The resulting π0 model can be used to control multiple robot embodiments with differing action spaces to accomplish a wide variety of tasks.
· label `fig:overview` · paper.tex L117 · 源文件 `figures/overview.pdf` · 正文引用：§3 Overview (L135)；§4 The π0 Model (L142)

## 图 4 · 第 5 页 · `figures/fig-04.png`
**caption**：Fig. 4: Overview of our dataset: The pre-training mixture consists of a subset of OXE [10] and the π dataset. We use a subset of OXE, which we refer to as OXE Magic Soup [24]. The right figure illustrates the weight of the different datasets in the pre-training mixture. The left figure illustrates their relative sizes as measured by the number of steps.
· label `fig:datastats` · paper.tex L171 · 源文件 `figures/combined-robot-allocation-chart.png` · 正文引用：§5.1 Pre-training and post-training (L179)；§5.3 Robot system details (L216)

## 图 5 · 第 6 页 · `figures/fig-05.png`
**caption**：Fig. 5: The robots used in our experiments. These include single and dual-arm manipulators with 6-DoF and 7-DoF arms, as well as holonomic and nonholonomic mobile manipulators. π0 is trained jointly on all of these platforms.
· label `fig:robot` · paper.tex L193 · 源文件 `figures/robots_compressed.pdf` · 正文引用：§5.3 Robot system details (L200)；§6.4 Mastering complex multi-stage tasks (L341)

## 图 6 · 第 7 页 · `figures/fig-06.png`
**caption**：Fig. 6: Out-of-box evaluation tasks: To evaluate our base model, we run it after pre-training on five tasks: shirt folding, bussing easy, bussing hard, grocery bagging, and toast out of toaster. The tasks require a combination of dexterous manipulation, multi-stage behaviors, and semantic recognition.
· label `fig:pre-train-eval` · paper.tex L233 · 源文件 `figures/pretrain_filmstrip_compressed.pdf` · 正文引用：§6.1 Evaluating the base model (L240)

## 图 7 · 第 8 页 · `figures/fig-07.png`
**caption**：Fig. 7: Out-of-box evaluation results: We evaluate π0 trained for the full 700k steps, a version trained for 160k steps that matches the number of updates for baseline models, π0-small, and three baselines: OpenVLA and Octo trained on all of our data, and OpenVLA trained only on the UR5e tasks (which we found to work better on UR5e tasks). Across all tasks and all comparisons, even the “parity” version of our model outperforms all baselines, and the full version of our model achieves the best results by a large margin.
· label `fig:pre-train-results` · paper.tex L254 · 源文件 `figures/pretrain_tasks.pdf` · 正文引用：§6.1 Evaluating the base model (L261)

## 图 8 · 第 8 页 · `figures/fig-08.png`
**caption**：Fig. 8: The tasks in our language evaluation. We evaluate our model on 3 different language-conditioned tasks, each of which requires following a sequence of intermediate language commands. The tasks involve bussing a table (top) to put dishes in a bin and garbage in a trash bin, setting a table (middle) by taking items out of a bin, and packing a shopping bag (bottom).
· label `fig:eval-language` · paper.tex L273 · 源文件 `figures/language_guided_filmstrip_compressed.pdf` · 正文引用：§6.2 Following language commands (L279)

## 图 9 · 第 9 页 · `figures/fig-09.png`
**caption**：Fig. 9: Language evaluation. We compare “flat” versions of our policies, −flat, which receive only the overall task com- mand (e.g., “bag the groceries”) with a method that receives intermediate commands from a human expert, −human, or a high-level VLM policy, −HL. We also compare our model to a small non-VLM variant under the “expert” condition, π0 and π0-small, in terms of language following accuracy. The results show a significant improvement with π0 from intermediate language commands provided by a human expert and to a lesser degree by an autonomous high-level policy. Notably, due to π0-small’s limited language following ability, overall it does not gain with the addition of a high-level expert.
· label `fig:eval-language-results` · paper.tex L281 · 源文件 `figures/language_tasks.png` · 正文引用：§6.2 Following language commands (L287)

## 图 10 · 第 9 页 · `figures/fig-10.png`
**caption**：Fig. 10: Fine-tuning evaluation tasks: We fine-tune our model to a variety of downstream tasks that are distinct from the tasks seen in pre-training. Our tasks represent a range of similarity from the pre-training tasks, with tasks that are most similar to pre-training (stack bowls and towel folding), a task that introduces an unseen new element (a microwave), and tasks that require new motions and new object types (Franka items in drawer and paper towel replacement).
· label `fig:fine-tuning-eval` · paper.tex L295 · 源文件 `figures/learning_dexterous_tasks_filmstrip_compressed.pdf` · 正文引用：§6.3 Learning new dexterous tasks (L291)

## 图 11 · 第 10 页 · `figures/fig-11.png`
**caption**：Fig. 11: Fine-tuning with varying amounts of data. π0 can learn some easier tasks even with smaller amounts of data, and the pre-trained model often attains a larger improvement over the model trained from scratch.
· label `fig:fine-tuning-sweep` · paper.tex L310 · 源文件 `figures/finetune_tasks_over_time.pdf` · 正文引用：§6.3 Learning new dexterous tasks (L319)

## 图 12 · 第 11 页 · `figures/fig-12.png`
**caption**：Fig. 12: We evaluate a range of complex and temporally extended tasks. This includes: folding laundry from a bin with a stationary (a) or mobile (b) robot, bussing a real lunch table (c), assembling a box (d), packing eggs into a carton (e), and packing food into a to-go box (f). These tasks require combining dozens of individual behaviors, such as grasping, stacking, folding, and flattening, generalization to a huge variety of object configurations, and complex physical properties, such as deformable objects or flexible cardboard.
· label `fig:post-training` · paper.tex L323 · 源文件 `figures/multi_stage_filmstrip_compressed.pdf` · 正文引用：§6.4 Mastering complex multi-stage tasks (L330)

## 图 13 · 第 11 页 · `figures/fig-13.png`
**caption**：Fig. 13: Post-training results on complex tasks in terms of average scores over 10 trials. The full pre-trained π0 model attains more than 50% of the maximum score across all of the tasks, and typically outperforms the ablations, with especially significant improvements on the hardest tasks.
· label `fig:post-training-results` · paper.tex L332 · 源文件 `figures/complex_finetune.png` · 正文引用：§6.4 Mastering complex multi-stage tasks (L353)

## 图 14 · 第 16 页 · `figures/fig-14.png`
**caption**：Fig. 14: Flow matching timestep sampling distribution. We sample τ from a shifted beta distribution that emphasizes lower timesteps (corresponding to noisier actions), and does not sample timesteps at all above a cutoff value s. We use s = 0.999 in our experiments.
· label `fig:timestep-sampling` · paper.tex L408 · 源文件 `figures/timestep_sampling.pdf` · 正文引用：§A.2 Model Architecture Details (L407)

## 表 I · 第 16 页 · `figures/tab-I.png`
**caption**：TABLE I: Inference time of our model on an NVIDIA GeForce RTX 4090 GPU.
· label `tab:inference_time` · paper.tex L427 · 正文引用：§A.4 Inference (L424)
