## Description
This is a PyToch implementation of "A Self-Distillation Approach via Entropy Transfer for Scene Text Detection". 

Some codes refer to [MhLiao/DB](https://github.com/MhLiao/DB) and [WenmuZhou/DBNet.pytorch](https://github.com/WenmuZhou/DBNet.pytorch) .

## Requirements:
- Python 3.6.8
- PyTorch 1.4.0
- torchvision 0.5.0

```bash
  conda create --name SDET python=3.6.8
  conda activate SDET
  pip install -r requirement.txt
  conda install pytorch==1.4.0 torchvision==0.5.0 cudatoolkit=10.1 -c pytorch
```

## Models
Download the trained models [Baidu Drive](https://pan.baidu.com) (access code: xxx) and put them in ```SDET/pretrain_model/```.

For example:
```
  pretrain_model/ic15_mv3_et_p0.865_r0.739_f0.797
  pretrain_model/ic15_r50_et_p0.903_r0.821_f0.860
```

## Datasets

The icdar2015 datasets can be downloaded from [Baidu Drive](https://pan.baidu.com) (access code: xxxx).

The paths are as follows: 
```
  datasets/icdar2015/train_images
  datasets/icdar2015/train_gts
  datasets/icdar2015/train_list.txt
  datasets/icdar2015/test_images
  datasets/icdar2015/test_gts
  datasets/icdar2015/test_list.txt
```



## Predict

Detect a single image.

```CUDA_VISIBLE_DEVICES=0 python predict.py --config ic15_r50 --image_path datasets/img_328.jpg --visualize```

The result is saved in `workspace` by default.


## Evaluate


```
CUDA_VISIBLE_DEVICES=0 python eval.py --config ic15_mv3
CUDA_VISIBLE_DEVICES=0 python eval.py --config ic15_r50
```

The results should be as follows:

|        Model       	| P 	| R 	| F 	| 
|:------------------:	|:---------:	|:------:	|:---------:	|
| ic15-mv3-sdet  |    86.5   	|  73.9  	|    79.7   	|       
| ic15-resnet50-sdet|    90.3  	|  82.1  	|    86.0   	|

only train on ICDAR2015 dataset

   
