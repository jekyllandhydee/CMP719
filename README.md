# Comprehensive Study of Infrared Small Target Detection on NUDT-SIRST

This repository provides the implementation and benchmarking results of the cmp719 project:  

---

## 📘 Overview

This study presents a **systematic benchmark** of five state-of-the-art infrared small target detection (IRSTD) methods on the **NUDT-SIRST** dataset.  
It aims to provide fair, reproducible, and insightful comparisons across different design paradigms in IRSTD.

| Compared Methods |
|------------------|
| ACMNet (AAAI 2020) |
| ALCNet (TGRS 2021) |
| DNANet (CVPR 2022) |
| LESPS (TIP 2024) |
| MSHNet (PR 2023) |

---

##  Benchmark Dataset

I use the **NUDT-SIRST** dataset, which offers:
- ✔️ 10,000 training and 100 test images
- ✔️ Pixel-level annotations
- ✔️ Cluttered and heterogeneous IR scenes

>  Dataset can be downloaded from: [YeRen123455/Infrared-Small-Target-Detection](https://github.com/YeRen123455/Infrared-Small-Target-Detection)

---

##  Evaluation Metrics

My evaluation covers:
- **IoU (Intersection over Union)**
- **Precision**
- **Recall**
- **F1-score**
- **Pd (Probability of Detection)**
- **Fa (False Alarm Rate)**

You can reproduce the metrics via the provided scripts in the `evaluation/` directory.

---

##  Requirements

Python 3
pytorch (1.2.0), torchvision (0.4.0) or higher
numpy, PIL

##  Train

python train.py --model_names DNANet ALCNet ACM --dataset_names SIRST3 --label_type 'centroid'

python train.py --model_names DNANet ALCNet ACM --dataset_names SIRST3 --label_type 'coarse'

python train_full.py --model_names DNANet ALCNet ACM --dataset_names SIRST3 --label_type 'full'

##  Test

python test.py --model_names DNANet ALCNet ACM --pth_dirs None --dataset_names SIRST NUDT-SIRST IRSTD-1K

python test.py --model_names DNANet ALCNet ACM --pth_dirs SIRST3/DNANet_full.pth.tar SIRST3/DNANet_LESPS_centroid.pth.tar SIRST3/DNANet_LESPS_coarse.pth.tar SIRST3/ALCNet_full.pth.tar SIRST3/ALCNet_LESPS_centroid.pth.tar SIRST3/ALCNet_LESPS_coarse.pth.tar SIRST3/ACM_full.pth.tar SIRST3/ACM_LESPS_centroid.pth.tar SIRST3/ACM_LESPS_coarse.pth.tar --dataset_names SIRST NUDT-SIRST IRSTD-1K




