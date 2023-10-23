# YNet

![teaser](resources/pipeline.png)

This repository will provide the code for the following paper:

**YNet: **<br>


Our code is based on MMSegmentaion (version 0.16.0).

## Installation
### Create a conda virtual environment and activate it (conda is optional)
```
conda create -n isdnet python=3.8 -y
conda activate isdnet
```
### Install dependencies
```
# Install pytorch firstly, the cudatoolkit version should be same in your system.
conda install pytorch==1.6.0 torchvision==0.7.0 cudatoolkit=10.1 -c pytorch

# Or you can install via pip
pip install torch==1.6.0 torchvision==0.7.0

# Install
python setup.py develop
```
## Datasets
We follow [FCtL](https://github.com/liqiokkk/FCtL) to split dataset.

Create folder named 'root_path', its structure is  
```
    root_path/
    ├── img_dir
       ├── train
          ├── xxx.jpg
          ├── ...
       ├── val
       ├── test
    ├── rgb2id
      ├── train
          ├── mask.png(0-num_class)
          ├── ...
      ├── val
      ├── test
```


### Training
DeepGlobe
`./tools/dist_train.sh configs/isdnet/isdnet_r18-d8_1224x1224_80k_DeepGlobe.py 4`

Inria Aerial
`./tools/dist_train.sh configs/isdnet/isdnet_r18-d8_2500x2500_40k_InriaAerial.py 4`

### Evaluation
Accuracy:
`python tools/test.py config_file checkpoints_file --eval mIoU`

*Please download following pretrianed-model [here](https://drive.google.com/file/d/1FfG-qRlGy-2BsVjN2ZcKTEG9wZeo3sdW/view?usp=sharing)*

FPS:
`python tools/fps_test.py config_file --height height of the test image --width width of the test image`


## Results
### DeepGLobe
| Class | urban | agriculture | rangeland |forest | water | barren | unknown |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
 IoU | 79.55 |88.21 |42.48 | 79.82 | 84.58 | 65.20 | - |

### Inria Aerial
| Class |  building  | background |
| :---: | :---: | :---: |
| IoU | 74.39 | 97.58 |


## Citation
If you use this code and our results for your research, please cite our paper.
```


