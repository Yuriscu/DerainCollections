Deep Convolutional Network in Single Image Derain
==================================

## Overview
Restoring rain images is important for many computer vision applications in outdoor scenes since rain streaks can severely degrade the visibility causing many current computer vision algorithms fails to work.

In recent years, various methods mainly based on CNNs have been proposed to address this problem.

This repo records some papers with implementation and finally make comparison between them.

## Important Papers and Implementations

1. DID-MDN(<u>*SOTA*</u>)

    - Paper
    
         [Density-aware Single Image De-raining using a Multi-stream Dense Network, He Zhang, Vishal M. Patel, 2018](https://arxiv.org/pdf/1802.07412.pdf)
    
    - Github
    
        [DID-MDN](https://github.com/hezhangsprinter/DID-MDN)
        
    - [Notes](./Notes/DID-MDN.md)
2. Current JORDAR

    - Paper
    
         [Deep Joint Rain Detection and Removal from a Single Image, Wenhan Yang, Robby T. Tan et al, 2017](https://arxiv.org/pdf/1609.07769.pdf)
    
    - Github
    
        [Joint Rain Detection and Removal from a Single Image](https://github.com/ZhangXinNan/RainDetectionAndRemoval)
        
    - [Notes](./Notes/CJORDAR.md) 

3. RESCAN

    - Paper
    
         [Recurrent Squeeze-and-Excitation Context Aggregation Net for Single Image Deraining, Xia Li, Jianlong Wu et al, 2018](https://arxiv.org/pdf/1807.05698.pdf)
    
    - Github
    
        [RESCAN: Recurrent Squeeze-and-Excitation Context Aggregation Net](https://github.com/XiaLiPKU/RESCAN)
        
    - [Notes](./Notes/RESCAN.md) 

4. Attentive-GAN for Raindrop Removal

    - Paper
        
        [Attentive Generative Adversarial Network for Raindrop Removal from A Single Image,Rui Qian, Robby T. Tan et al, 2017](https://arxiv.org/pdf/1711.10098.pdf)
        
    - [Notes](./Notes/Att-GAN.md)
    
    
## Implementations of above in pytorch

### Prerequisite
- Python>=3.6
- Pytorch>=1.0.0
- Opencv>=3.1.0
- visdom

```bash
    pip install -r requirements.txt
``` 

### Project Structure
- checkpoints : holds checkpoints
- datasets : 
- losses: losses like ssim and psnr
- models: holds model for training or testing
- pretrained_models: holds pretrained model for fine-ture
- settings : holds seperate setting config for model
- utils : practical tools 

### Datasets
- RESCAN : [Rain800](https://drive.google.com/drive/folders/0Bw2e6Q0nQQvGbi1xV1Yxd09rY2s)
- JORDER : [Rain100H,Rain100L](http://www.icst.pku.edu.cn/struct/Projects/joint_rain_removal.html)
- DID-MDN : [DID-MDN](https://drive.google.com/file/d/1cMXWICiblTsRl1zjN8FizF5hXOpVOJz4/view?usp=sharing)
### Training
Two parameters:
-c, --config : each networks configuration files which contains the parameter about model and training details.
-t, --type : denote the model structure fully connected network or generative adversarial networks
```bash
    python train.py -c ./configs/didmdn_didmdn_rain.yaml -t 'fcn'
``` 
### Testing
```bash
python test.py  -c ./configs/didmdn_didmdn_rain.yaml -t 'fcn'
```


    
    
