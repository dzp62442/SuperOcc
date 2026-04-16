## Environment
1. Create a conda virtual environment and activate
```bash
conda create -n superocc python=3.8
conda activate superocc
```

2. Install PyTorch and torchvision following the official instructions
```bash
pip install torch==2.0.0 torchvision==0.15.1 torchaudio==2.0.1 --index-url https://download.pytorch.org/whl/cu118
```

3. Install other dependencies:
```bash
pip install openmim
mim install mmcv-full==1.6.0
mim install mmdet==2.28.2
mim install mmsegmentation==0.30.0
mim install mmdet3d==1.0.0rc6
pip install setuptools==59.5.0
pip install numpy==1.23.5
pip install pillow==8.4.0
pip install kornia
pip install yapf==0.40.1
```

4. Compile CUDA extensions:
```bash
cd projects
python setup.py develop
```

5. Clone the MMDetection3D source tree at the matching version:
```bash
# This repository's config files use `_base_` paths like `../../../mmdetection3d/configs/...`, 
# so keeping a local `mmdetection3d` source tree in the project root avoids missing-file errors when loading configs.
cd ..
git clone -b v1.0.0rc6 https://github.com/open-mmlab/mmdetection3d.git
```
