# HDNet: A Hybrid Domain Network with Multi-Scale High-Frequency Information Enhancement for Infrared Small Target Detection

> **Official PyTorch implementation of the TGRS 2025 paper "HDNet: A Hybrid Domain Network with Multi-Scale High-Frequency Information Enhancement for Infrared Small Target Detection".**

## Authors

**Mingzhu Xu**<sup>1</sup>, **Chenglong Yu**<sup>1</sup>, **Zexuan Li**<sup>1</sup>, **Haoyu Tang**<sup>1</sup>, **Yupeng Hu**<sup>1</sup>\*, **Liqiang Nie**<sup>1</sup>

<sup>1</sup> `Shandong University`  
\* Corresponding author

## Links

- **Paper**: [`IEEE Xplore`](https://ieeexplore.ieee.org/document/11017756)
- **Code Repository**: [`GitHub`](https://github.com/iLearn-Lab/HDNet)

---

## Table of Contents

- [Introduction](#introduction)
- [Highlights](#highlights)
- [Method / Framework](#method--framework)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Dataset](#dataset)
- [Usage](#usage)
- [Quantitative Results](#quantitative-results)
- [Citation](#citation)
- [Acknowledgement](#acknowledgement)
- [License](#license)
---

## Introduction

This project is the official implementation of the paper **"HDNet: A Hybrid Domain Network with Multi-Scale High-Frequency Information Enhancement for Infrared Small Target Detection"**.

HDNet proposes an innovative hybrid-domain network that significantly enhances the contrast of infrared small targets and suppresses background interference by integrating frequency-domain features with traditional spatial-domain CNN features:

- **Spatial Branch**: Introduces a **Multi-scale Atrous Convolution (MAC)** module to enhance the perception of small targets at different scales.  
- **Frequency Branch**: Designs a **Dynamic High-Pass Filter (DHPF)** module to dynamically remove low-frequency background interference while preserving high-frequency target details.  
- **Experimental Performance**: Outperforms 26 state-of-the-art methods on three benchmark datasets: IRSTD-1K, NUAA-SIRST, and NUDT-SIRST.  

### Example Description

We present **HDNet**, a framework for **Infrared Small Target Detection (IRSTD)**.  
Our method addresses **background interference and low contrast** by introducing **hybrid domain feature fusion** and **dynamic high-pass filtering**.  
This repository provides the official implementation, pretrained weights, and evaluation scripts.

---

## Highlights

- Proposes a **Hybrid-Domain Network (HDNet)** that combines spatial multi-scale perception and frequency-domain background suppression.  
- Introduces the **MAC module**, improving contrast between small targets and complex backgrounds.  
- Introduces the **DHPF module**, dynamically suppressing low-frequency background noise.  
- Provides complete evaluation results on three public benchmark datasets.  

---

## Method / Framework

The HDNet architecture illustrates a dual-branch collaboration between spatial and frequency domains.

### Framework Figure

![Framework](./Fig/Structure.png)

**Figure 1.** Overall framework of HDNet.

---

## Project Structure

```text
.
├── Fig/                   # Architecture diagrams and visualization results
├── datasets/              # Datasets (IRSTD-1K, NUAA-SIRST, NUDT-SIRST)
├── weight/                # Pretrained weights (.pkl)
├── main.py                # Main entry script
├── README.md
└── requirements.txt
````

-----

## Installation

### 1\. Clone the repository

```bash
git clone [https://github.com/iLearn-Lab/HDNet.git](https://github.com/iLearn-Lab/HDNet.git)
cd HDNet
```

### 2\. Prerequisites

This project was developed under Ubuntu 22.04. Recommended environment:

  - Python 3.10
  - PyTorch 2.1.0
  - CUDA 12.1

<!-- end list -->

```bash
pip install -r requirements.txt
```

-----

## Dataset

Please download the following datasets and place them in the ./datasets directory:

  - [IRSTD-1k](https://github.com/RuiZhang97/ISNet)
  - [NUAA-SIRST](https://github.com/YimianDai/sirst)
  - [NUDT-SIRST](https://github.com/YeRen123455/Infrared-Small-Target-Detection)

-----

## Usage

### Training

```bash
python main.py --dataset-dir './dataset/IRSTD-1k' --batch-size 4 --epochs 800 --mode 'train'
```

### Testing

```bash
python main.py --dataset-dir './dataset/IRSTD-1k' --batch-size 4 --mode 'test' --weight-path './weight/irstd.pkl'
```

-----

## Quantitative Results

| Dataset | mIoU (x10⁻²) | Pd (x10⁻²) | Fa (x10⁻⁶) | Weights |
| :--- | :---: | :---: | :---: | :---: |
| IRSTD-1k | 70.26 | 94.56 | 4.33 | [Download](https://drive.google.com/file/d/1WjKkkfIRlI7aNlu4xTglmVxwtDqlu4Gu/view?usp=drive_link) |
| NUAA-SIRST | 79.17 | 100 | 0.53 | [Download](https://drive.google.com/file/d/1GoCaiAEodUop5EPyDWu5LEfJ71D1kOz2/view?usp=drive_link) |
| NUDT-SIRST | 85.17 | 98.52 | 2.78 | [Download](https://drive.google.com/file/d/1we0dE2L47z509-EW4_Bj4Y828oPSkNAe/view?usp=drive_link) |

Visualization results can be found here：[HDNet\_Visual\_Result](https://www.google.com/search?q=https://drive.google.drive/folders/1RfoxhoHpjfbRMZHBOvISrJSB5lpoz40t%3Fusp%3Ddrive_link)

-----

## Citation

If you use this code in your research, please cite our paper:

```bibtex
@ARTICLE{11017756,
  author={Xu, Mingzhu and Yu, Chenglong and Li, Zexuan and Tang, Haoyu and Hu, Yupeng and Nie, Liqiang},
  journal={IEEE Transactions on Geoscience and Remote Sensing}, 
  title={HDNet: A Hybrid Domain Network With Multiscale High-Frequency Information Enhancement for Infrared Small-Target Detection}, 
  year={2025},
  volume={63},
  number={},
  pages={1-15},
  doi={10.1109/TGRS.2025.3574962}
}
```

-----

## Acknowledgement

  - HDNet adopts the SLS loss function and builds upon the architecture of[MSHNet](https://github.com/Lliu666/MSHNet). Special thanks to the work of Qiankun Liu.

-----

## License

This project is released under the Apache License 2.0.
