🐣 Please follow me for new updates https://twitter.com/camenduru <br />
🔥 Please join our discord server https://discord.gg/k5BwmmvJJU

# 🚦 WIP 🚦

## 🦒 Colab

| Colab | Info
| --- | --- |
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/camenduru/vid2avatar-colab/blob/main/vid2avatar_colab.ipynb) | vid2avatar_colab (>16GB VRAM 🦒 Pro Colab)

## Training
Before training, make sure that the `metaninfo` in the data config file `/code/confs/dataset/video.yaml` does match the expected training video. You can also continue the training by changing the flag `is_continue` in the model config file `code/confs/model/model_w_bg`. And then run:
```
cd code
python train.py
```

## Main Repo
https://github.com/MoyGcc/vid2avatar

## Page
https://moygcc.github.io/vid2avatar/

## Paper
https://arxiv.org/abs/2302.11566

## License

## Output

For python 3.8 (lambdalabs, runpod ...)
```py
%cd /home/ubuntu
!pip install chumpy hydra-core wandb aitviewer trimesh simple-romp pytorch-lightning==1.6.5 #1.8.6

!pip install -q https://huggingface.co/camenduru/pytorch3d-build/resolve/main/pytorch3d-0.7.4-cp38-cp38-linux_x86_64.whl
from pytorch3d import ops
!pip install -q https://huggingface.co/camenduru/pytorch3d-build/resolve/main/kaolin-0.14.0a0-cp38-cp38-linux_x86_64.whl
import kaolin

!git clone -b dev https://github.com/camenduru/vid2avatar
%cd /home/ubuntu/vid2avatar

!wget https://huggingface.co/camenduru/vid2avatar/resolve/main/parkinglot.zip
!unzip -y parkinglot.zip -d /home/ubuntu/vid2avatar/data

!mkdir /home/ubuntu/vid2avatar/code/lib/smpl/smpl_model
!wget https://huggingface.co/camenduru/vid2avatar/resolve/main/models/SMPL_FEMALE.pkl -O /home/ubuntu/vid2avatar/code/lib/smpl/smpl_model/SMPL_FEMALE.pkl
!wget https://huggingface.co/camenduru/vid2avatar/resolve/main/models/SMPL_MALE.pkl -O /home/ubuntu/vid2avatar/code/lib/smpl/smpl_model/SMPL_MALE.pkl

%cd /home/ubuntu/vid2avatar/code
!sudo python setup.py develop

%cd /home/ubuntu/vid2avatar/code
!python test.py
```
