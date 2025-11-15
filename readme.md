# Multi-Frequency Feature Collaborative Network for Low-Light Image Enhancement


**Abstract**:Low-light image degradation typically appears as the loss of high-frequency details (e.g., edge blurring) and distortions in low-frequency structures (e.g.,
color deviations). Thus, existing methods often adopt encoder-decoder frameworks to restore normal-light images, where shallow layers primarily capture
high-frequency features and deeper layers focus on low-frequency components. However, this hierarchical separation results in a disjointed treatment
of frequency components, limiting the model’s ability to capture their intrinsic relationships and ultimately hindering further performance gains. To this
end, we propose a multi-frequency feature collaborative network for low-light
image enhancement. We begin by introducing a multi-frequency collaborative learning strategy that leverages multiple distinct filters to extract prior
information associated with specific frequency components to compensate for
the loss of frequency information at each level of the network. Then we propose a collaborative fusion module to efficiently integrate these transformed
priors with their corresponding hierarchical network features. This design
captures interactive patterns among complementary frequency components
across different network layers, thereby enhancing the modeling of complex
mappings between low-light and normal-light images. Furthermore, we propose a channel-correlation correction loss, which anchors one color channel
while constraining pixel differences across channels. This constraint captures subtle inter-pixel relationships within latent color channels, promoting
more accurate color restoration. Finally, we validate the effectiveness of our
method on multiple datasets, achieving state-of-the-art performance.



![fig11](https://github.com/user-attachments/assets/d06898d0-1586-46dd-aa96-d3d986c7e485)



## 📖 Overview

This repository contains the official **PyTorch** implementation of our proposed **Multi-Frequency Feature Collaborative Network** for low-light image enhancement. The model effectively captures and collaborates multi-frequency features to restore natural illumination, suppress noise, and preserve structural details in extremely dark scenes.


---
### 1. Basic Environment Configuration
 
 
 Install the core dependencies for the project:

```bash
pip install argparse==1.1
pip install torch==1.2.0 torchvision==0.2.1
pip install numpy==1.18.1
pip install imageio==2.8.0
pip install opencv-python==4.2.0.32
pip install tensorboardX
pip install timm=1.0.15
pip install scikit-image= 0.25.2
pip install PyYAML=6.0.1
pip install numpy==1.26.4
pip install scipy==1.12.0
```
---
### 2. Mamba Installation


We have prepared the two required source code dependencies for Mamba. Please Follow the commands below to install them：
```bash
cd causal-conv1d
pip install -e .
cd mamba-1p1p1
pip install -e .
```

## Dataset preparation
 - [Low-Light dataset (LOLv1)](https://daooshee.github.io/BMVC2018website/)  Low-Light dataset (LOLv1)
 - [LOLv2-synthesis](https://ieeexplore.ieee.org/document/9328179)  Synthetic low-light dataset
 - [LSRW-Huawei and LSRW-NIKON ](https://github.com/JianghaiSCU/R2RNet) Huawei mobile dataset and Nikon camera dataset

 


## Train
```bash
python train.py -opt config_path --local_rank 0
```

## Test
```bash
python cs_LOLv1_v2_real.py -opt config_path
```
## Quantitative Evaluation


### Quantitative results on the four datasets: LOLv1, LOLv2-synthesis, LSRW-Huawei, and LSRW-NIKON.

<img width="1236" height="516" alt="image" src="https://github.com/user-attachments/assets/11d68804-e839-42e7-a25c-2e475468f413" />


### Qualitative results on the two datasets: LOLv1 and LOLv2-synthesis.
<img width="1014" height="595" alt="image" src="https://github.com/user-attachments/assets/7da5be25-a425-4357-a28c-7047c06eccc5" />

### Qualitative results on the two datasets: LSRW-Huawei and LSRW-Nikon.
<img width="988" height="426" alt="image" src="https://github.com/user-attachments/assets/4d100c34-6d9b-4874-b91d-47a3b7bf96a7" />








