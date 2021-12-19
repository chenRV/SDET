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

## Pre-Trained Model
Download Trained models [Baidu Drive](https://pan.baidu.com/s/1vxcdpOswTK6MxJyPIJlBkA) (download code: p6u3)

## Datasets
The root of the dataset directory can be ```SDET/datasets/```.

An example of the path of test images: 
```
  datasets/total_text/train_images
  datasets/total_text/train_gts
  datasets/total_text/train_list.txt
  datasets/total_text/test_images
  datasets/total_text/test_gts
  datasets/total_text/test_list.txt
```

Download the converted ground-truth and data list [Baidu Drive](https://pan.baidu.com/s/1BPYxcZnLXN87rQKmz9PFYA) (download code: mz0a).


## Evaluate

ICDAR 2015
only train on ICDAR2015 dataset

```
CUDA_VISIBLE_DEVICES=0 python eval.py
```

The results should be as follows:

|        Model       	| P 	| R 	| F 	| 
|:------------------:	|:---------:	|:------:	|:---------:	|
| ic15-resnet18  |    87.7   	|  77.5  	|    82.3   	|       
| ic15-resnet50 (1152)|    90.7   	|  84.0  	|    87.2   	|

   
