# TriLiteNet

	
[![PWC](https://img.shields.io/endpoint.svg?url=https://paperswithcode.com/badge/trilitenet-lightweight-model-for-multi-task/traffic-object-detection-on-bdd100k-val)](https://paperswithcode.com/sota/traffic-object-detection-on-bdd100k-val?p=trilitenet-lightweight-model-for-multi-task)
[![PWC](https://img.shields.io/endpoint.svg?url=https://paperswithcode.com/badge/trilitenet-lightweight-model-for-multi-task/drivable-area-detection-on-bdd100k-val)](https://paperswithcode.com/sota/drivable-area-detection-on-bdd100k-val?p=trilitenet-lightweight-model-for-multi-task)
[![PWC](https://img.shields.io/endpoint.svg?url=https://paperswithcode.com/badge/trilitenet-lightweight-model-for-multi-task/lane-detection-on-bdd100k-val)](https://paperswithcode.com/sota/lane-detection-on-bdd100k-val?p=trilitenet-lightweight-model-for-multi-task)

## Paper

* If you find our work useful, please cite this paper: **TwinLiteNetPlus: A Stronger Model for Real-time Drivable Area and Lane Segmentation.** [![IEEE Access](https://img.shields.io/badge/IEEAccess)]([https://arxiv.org/abs/2403.16958](https://ieeexplore.ieee.org/document/10930421))

<img width="1161" alt="Ảnh màn hình 2025-04-27 lúc 05 00 57" src="https://github.com/user-attachments/assets/b57d9590-b57d-475d-a93f-cfef960f9669" />


## Requirement

This codebase has been developed with python version 3.8, PyTorch 1.8.0 and torchvision 0.9.0

```setup
pip install -r requirements.txt
```



## Pre-trained Model
You can get the pre-trained model from <a href="https://drive.google.com/drive/folders/1wLZqemCxxzwiFeFUGY1zMaqcKoQLHFyK?usp=sharing">here</a>.


## Dataset
- Download the images from [images](https://bdd-data.berkeley.edu/).
- Download the annotations of detection from [det_annotations](https://drive.google.com/file/d/1Ge-R8NTxG1eqd4zbryFo-1Uonuh0Nxyl/view?usp=sharing). 
- Download the annotations of drivable area segmentation from [da_seg_annotations](https://drive.google.com/file/d/1xy_DhUZRHR8yrZG3OwTQAHhYTnXn7URv/view?usp=sharing). 
- Download the annotations of lane line segmentation from [ll_seg_annotations](https://drive.google.com/file/d/1lDNTPIQj_YLNZVkksKM25CvCHuquJ8AP/view?usp=sharing). 

We recommend the dataset directory structure to be the following:

```
# The id represent the correspondence relation
├─dataset root
│ ├─images
│ │ ├─train
│ │ ├─val
│ ├─det_annotations
│ │ ├─train
│ │ ├─val
│ ├─da_seg_annotations
│ │ ├─train
│ │ ├─val
│ ├─ll_seg_annotations
│ │ ├─train
│ │ ├─val
```

Update the your dataset path in the `lib/config/default.py`.

## Training

```shell
python tools/train.py --config 'weights/{tiny/small/base}'
```
## Evaluation

```shell
python tools/test.py --config '{tiny/small/base}' --weights 'weights/{tiny/small/base}.pth'
```
## Demo

```shell
python tools/demo.py --config '{tiny/small/base}' --weights 'weights/{tiny/small/base}.pth' --source 'inference/videos/1.mp4' or 'inference/images'
```


## Acknowledgements

This work would not have been possible without the valuable contributions of the following authors.


* [YOLOP](https://github.com/hustvl/YOLOP)
* [TwinLiteNet](https://github.com/chequanghuy/TwinLiteNet)
* [TwinLiteNetPlus](https://github.com/chequanghuy/TwinLiteNetPlus)
* [Partial Class Activation Attention for Semantic Segmentation](https://github.com/lsa1997/PCAA)
* [ESPNet](https://github.com/sacmehta/ESPNet)

## Citation

```BibTeX
@ARTICLE{trilitenet,
  author={Che, Quang-Huy and Lam, Duc-Khai},
  journal={IEEE Access}, 
  title={TriLiteNet: Lightweight Model for Multi-Task Visual Perception}, 
  year={2025},
  volume={13},
  number={},
  pages={50152-50166},
  doi={10.1109/ACCESS.2025.3552088}}

```

