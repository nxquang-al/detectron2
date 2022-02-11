This is a merge between [Detectron2 (version 0.6)](https://github.com/facebookresearch/detectron2) and [BCNet](https://github.com/lkeab/BCNet).

## Quick Install guide

This is a quickstart for people already familiar with Detectron2.  If you are not familar then you will want to reference to the Detectron2 guides.

This assumes you have a fresh virtual environment with python 3.8

1) PIP install the correct version of Pytorch based on your OS and CUDA versions: https://pytorch.org/get-started/locally/

For example with CUDA 11.3+
```
pip install torch==1.10.2+cu113 torchvision==0.11.3+cu113 torchaudio==0.10.2+cu113 -f https://download.pytorch.org/whl/cu113/torch_stable.html
```

2) Install packages (setuptools version matters):

```
pip install scikit-image opencv-python setuptools==59.5.0 
```

3) Clone repo and install:
```
git clone https://github.com/shadercloud/detectron2
python -m pip install -e detectron2
```

## Next Steps

Note that for BCNet you will need to run your normal COCO json annotation files through the `process_data.py` script which will generate an updated annotation file with additional segmentation data.  If you do not do this and try to run regular COCO json through the trainer it will just give you errors.

```
python -m detectron2.data.datasets.process_dataset datasets/coco/annotations/instances_train2017.json datasets/coco/train2017 coco_2017_train
```

There new JSON file is output to `detectron2/data/datasets/anno.json`

For all license into or help please see the Detectron2 and BCNet github repos:

- https://github.com/facebookresearch/detectron2

- https://github.com/lkeab/BCNet