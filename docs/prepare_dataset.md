# Prepare Dataset

## Nuscenes
1. Download nuScenes from [https://www.nuscenes.org/nuscenes](https://www.nuscenes.org/nuscenes) and put it in `data/nuscenes`.
2. (Optional) Download Occ3d-nuScenes from [link](https://tsinghua-mars-lab.github.io/Occ3D/) and place it in `data/nuscenes/gts`
3. (Optional) Download SurroundOcc from [link](https://github.com/weiyithu/SurroundOcc) and place it in `data/nuscenes/surround_occ`.
4. Prepare data with scripts provided by mmdet3d:
```bash
# 这里不要直接用 `mim run`，因为本仓库也有本地 `tools/` 目录，容易和 mmdet3d 安装包里的 `tools` 导入冲突。
MIM_ROOT=$(python -c "import os,mmdet3d; print(os.path.join(os.path.dirname(mmdet3d.__file__), '.mim'))")
PYTHONPATH=$MIM_ROOT python $MIM_ROOT/tools/create_data.py nuscenes --root-path ./data/nuscenes --out-dir ./data/nuscenes --extra-tag nuscenes
```
5. Perform data preparation for SupeOcc:
```bash
python tools/create_data_nusc.py
```
6. Folder structure:
```text
data/nuscenes
├── maps
├── nuscenes_infos_test.pkl
├── nuscenes_infos_train.pkl
├── nuscenes_infos_val.pkl
├── nuscenes_infos_train_sweep.pkl
├── nuscenes_infos_val_sweep.pkl
├── samples
├── sweeps
├── gts
├── surround_occ
├── v1.0-test
└── v1.0-trainval
```
