# SUNet

![teaser](pic/net.png)

## Requirements
### conda virtual environment 
```
python=3.8 
pytorch==1.10.0
cuda==11.3 
mmcv==1.4.0
```
## Datasets
Create folder named 'root_path', its structure is  
```
    root_path/
    ├── image
       ├── train
          ├── xxx.jpg
          ├── ...
       ├── val
       ├── test
    ├── mask
      ├── train
          ├── mask.png(0-num_class)
          ├── ...
      ├── val
      ├── test
```

### Training
`python  tools/train.py   config/path  --work-dir   save/path `
### Evaluation
Accuracy:
`python tools/test.py config_file checkpoints_file   --eval mIoU  `
### Speed
FPS:
`python tools/fps.py config_file   --height /   --width  /`


pic/net.png
