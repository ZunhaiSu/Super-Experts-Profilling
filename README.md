# Installation
```bash
conda create -n Super_Experts python==3.12 -y
conda activate Super_Experts
conda install pytorch==2.5.1 torchvision==0.20.1 torchaudio==2.5.1 pytorch-cuda=11.8 -c pytorch -c nvidia
pip install -r requirements.txt
```
# Quick start 
## Profiling Down_proj Outliers of Qwen3-30B-A3B
```shell
CUDA_VISIBLE_DEVICES=0 python3 run.py \
--model_name Your Model Path \
--save_path ./output/Qwen3-30B-A3B \
--profile_outliers \
--vis_outliers_heatmap
```
## Profiling Super Experts of Qwen3-30B-A3B
```shell
CUDA_VISIBLE_DEVICES=0 python3 run.py \
--model_name Your Model Path \
--save_path ./output/Qwen3-30B-A3B \
--profile_super_experts \
--vis_super_experts_line_plot
```
## PPL test of Original Qwen3-30B-A3B
```shell
CUDA_VISIBLE_DEVICES=0 python3 run.py \
--model_name Your Model Path \
--save_path ./output/Qwen3-30B-A3B \
--dataset_name wikitext2 \
--eval_ppl
```
## PPL Test of Qwen3-30B-A3B After Prune Super Experts
```shell
CUDA_VISIBLE_DEVICES=0 python3 run.py \
--model_name Your Model Path \
--save_path ./output/Qwen3-30B-A3B \
--eval_ppl \
--dataset wikitext2 \
--prune_super_experts
```

