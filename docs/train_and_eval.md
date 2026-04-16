## Training

支持全自动恢复训练

Train SuperOcc with 4 GPUs:
```bash
bash tools/dist_train.sh projects/configs/superocc/superocc-t_r50_704_seq_nui_48e.py 4 --work-dir work_dirs/superocc-t/default
```

Train SuperOcc on a single GPU with the SurroundOcc `s` config (`bs=1`):
```bash
bash tools/dist_train.sh projects/configs/superocc_surroundocc/superocc-s_r50_704_seq_nui_24e_1gpu_bs1.py 1 --work-dir work_dirs/superocc-surroundocc-s-1gpu-bs1
```

## Evaluation
```bash
bash tools/dist_test.sh projects/configs/superocc/superocc-t_r50_704_seq_nui_48e.py work_dirs/superocc-t/default/iter_168768.pth 4 --eval map
```

Evaluate the single-GPU SurroundOcc `s` config:
```bash
bash tools/dist_test.sh projects/configs/superocc_surroundocc/superocc-s_r50_704_seq_nui_24e_1gpu_bs1.py work_dirs/superocc-surroundocc-s-1gpu-bs1/latest.pth 1 --eval map
```
