# OSTB

[![Under review]()]()  

> This repository contains the official implementation of the     paper:  
> **"One Stone, Three Birds: Self-adaptive Optimal Transport for VLM Adaptation, Selection, and Ensembling"**  

---

 
## 🚀 Installation

Clone the repository and install required packages.

```bash  
cd
```

## 📂 Datasets

Datasets Features: BaiduCloud: https://pan.baidu.com/s/1U8oLdSIy1bLIBcI2mhMFMQ?pwd=qakt   (It is recommended to use BaiduPCS-go for downloading.)

It should be noted that the visual features have not been normalized. Universal dataset splits have been provided for natural image data and some medical pathology data. For the remaining data, we split it into training and testing sets at a ratio of 7:3. All splitting details can be found in dataset_splits. Due to the large size of the ImageNet dataset, We uploaded it in pieces, and the corresponding merging script also needs to be downloaded.

## Dataset Statistics

### Natural Images

| Dataset | Classes | Total | Train | Val | Test | Description |
|---|---:|---:|---:|---:|---:|---|
| ImageNet | 1000 | 1,331,167 | 1,281,167 | - | 50,000 | Natural image benchmark |
| SUN397 | 397 | 39,700 | 15,880 | 3,970 | 19,850 | Scene classification |
| FGVC Aircraft | 100 | 10,000 | 3,334 | 3,333 | 3,333 | Fine-grained aircraft classification |
| EuroSAT | 10 | 27,000 | 13,500 | 5,400 | 8,100 | Satellite land cover classification |
| Stanford Cars | 196 | 16,185 | 6,509 | 1,635 | 8,041 | Vehicle classification |
| Food101 | 101 | 101,000 | 50,500 | 20,200 | 30,300 | Food classification |
| Oxford Pets | 37 | 7,349 | 2,944 | 736 | 3,669 | Pet classification |
| Oxford Flowers | 102 | 8,189 | 4,093 | 1,633 | 2,463 | Flower classification |
| Caltech101 | 100 | 8,242 | 4,128 | 1,649 | 2,465 | Object classification, excluding BACKGROUND_Google and Faces_easy |
| DTD | 47 | 5,640 | 2,820 | 1,128 | 1,692 | Texture classification |
| UCF101 | 101 | 13,320 | 7,639 | 1,898 | 3,783 | Action recognition |
| CIFAR-10 | 10 | 60,000 | 40,000 | 10,000 | 10,000 | Image classification |
| CIFAR-100 | 100 | 60,000 | 40,000 | 10,000 | 10,000 | Image classification |
| CUB-200-2011 | 200 | 11,788 | 4,794 | 1,200 | 5,794 | Fine-grained bird classification |

### Medical Pathology

| Dataset | Classes | Total | Train | Val | Test | Description |
|---|---:|---:|---:|---:|---:|---|
| SICAP-MIL | 4 | 1,501 | 1,050 | - | 451 | Prostate cancer pathology |
| PCam | 2 | 327,680 | 262,144 | 32,768 | 32,768 | Tumor detection |
| Osteosarcoma | 3 | 1,144 | 800 | - | 344 | Osteosarcoma histology |
| BACH | 4 | 400 | 280 | - | 120 | Breast cancer histology |
| BreakHis | 8 | 7,909 | 5,536 | - | 2,373 | Breast cancer histology |
| SkinCancer | 16 | 129,364 | 88,971 | 12,354 | 28,039 | Skin pathology |
| SkinTumor | 4 | 42,416 | 29,419 | 4,146 | 8,851 | Skin tumor subset |
| LC25000 Lung | 3 | 15,000 | 10,500 | - | 4,500 | Lung tissue histology |
| LC25000 Colon | 2 | 10,000 | 7,000 | - | 3,000 | Colon tissue histology |
| NCT-CRC | 9 | 107,180 | 50,000 | 50,000 | 7,180 | Colorectal cancer histology |
| WSSS4LUAD | 2 | 10,091 | 7,063 | - | 3,028 | Lung adenocarcinoma |
| PanNuke | 2 | 6,234 | 4,346 | - | 1,888 | Binary pathology subset |

### Remote Sensing

| Dataset | Classes | Total | Train | Val | Test | Description |
|---|---:|---:|---:|---:|---:|---|
| AID | 30 | 10,000 | 7,000 | - | 3,000 | Aerial scene classification |
| EuroSAT | 10 | 27,000 | 18,900 | - | 8,100 | Land cover classification |
| MLRSNet | 46 | 109,161 | 76,410 | - | 32,751 | Multi-label remote sensing |
| OPTIMAL31 | 31 | 1,860 | 1,302 | - | 558 | Scene classification |
| PatternNet | 38 | 30,400 | 21,280 | - | 9,120 | High-resolution scene classification |
| RESISC45 | 45 | 31,500 | 22,050 | - | 9,450 | Scene classification |
| RSC11 | 11 | 1,232 | 862 | - | 370 | Scene classification |
| RSICB128 | 45 | 36,707 | 25,696 | - | 11,011 | Land cover classification at 128 scale |
| RSICB256 | 35 | 24,747 | 17,323 | - | 7,424 | Land cover classification at 256 scale |
| WHURS19 | 19 | 1,005 | 703 | - | 302 | Scene classification |


---

## 📊 Experimental Results


### Natural Images

| Model | ImageNet | SUN397 | Aircraft | EuroSAT | StanfordCars | Food101 | Pets | Flower102 | Caltech101 | DTD | UCF101 | CIFAR-10 | CIFAR-100 | CUB | Avg |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| [CLIP-B/32](https://github.com/openai/CLIP) | 62.01 | 62.06 | 19.17 | 45.27 | 60.09 | 80.39 | 87.44 | 66.67 | 91.40 | 42.85 | 63.44 | 88.32 | 64.37 | 52.66 | 63.30 |
| [CLIP-B/16](https://github.com/openai/CLIP) | 66.74 | 62.59 | 24.69 | 48.36 | 65.55 | 85.87 | 89.10 | 70.69 | 93.31 | 43.32 | 67.49 | 90.08 | 68.30 | 54.99 | 66.51 |
| [ALIGN](https://github.com/kakaobrain/coyo-align) | 65.26 | 70.11 | 11.31 | 32.69 | 72.38 | 79.91 | 84.30 | 60.29 | 94.77 | 58.16 | 64.79 | 75.61 | 52.16 | 38.25 | 61.43 |
| [SLIP-B/16](https://github.com/facebookresearch/SLIP) | 42.22 | 49.05 | 7.98 | 17.14 | 8.63 | 61.07 | 34.86 | 65.65 | 81.91 | 25.59 | 38.75 | 77.42 | 46.75 | 36.78 | 42.41 |
| [OpenCLIP-B/16](https://github.com/mlfoundations/open_clip) | 72.98 | 69.88 | 29.73 | 56.37 | 89.90 | 87.52 | 92.83 | 75.44 | 96.67 | 58.33 | 67.46 | 96.27 | 81.99 | 77.53 | 75.21 |
| [DeCLIP-B/32](https://github.com/Sense-GVT/DeCLIP) | 39.45 | 47.77 | 2.70 | 24.20 | 3.58 | 46.79 | 34.89 | 62.32 | 77.57 | 25.41 | 36.32 | 80.88 | 49.94 | 34.98 | 40.49 |
| [FLAVA](https://huggingface.co/facebook/flava-full) | 54.89 | 59.10 | 12.09 | 37.43 | 27.48 | 74.74 | 68.85 | 58.83 | 90.67 | 38.71 | 52.42 | 89.90 | 64.45 | 46.53 | 55.44 |
| [CoCa-B/32](https://github.com/mlfoundations/open_clip) | 63.43 | 66.59 | 18.06 | 45.43 | 86.42 | 75.44 | 89.13 | 65.20 | 94.52 | 52.48 | 62.25 | 93.55 | 73.85 | 60.27 | 67.62 |
| [EVA-CLIP-B/16](https://github.com/baaivision/EVA/tree/master/EVA-CLIP) | 74.47 | 70.81 | 24.69 | 58.17 | 79.13 | 86.55 | 92.20 | 75.80 | 97.16 | 50.35 | 69.12 | 98.26 | 87.84 | 61.94 | 73.32 |
| [MetaCLIP-B/16](https://github.com/facebookresearch/MetaCLIP) | 69.97 | 68.81 | 28.62 | 55.20 | 74.69 | 84.07 | 90.49 | 73.81 | 96.11 | 51.77 | 68.04 | 89.87 | 64.95 | 68.29 | 70.34 |
| [JinaCLIPv2](https://huggingface.co/jinaai/jina-clip-v2) | 66.23 | 65.58 | 16.47 | 51.53 | 77.69 | 84.18 | 80.08 | 68.53 | 92.01 | 50.30 | 56.44 | 95.73 | 77.65 | 32.43 | 65.35 |
| [SigLIP2-B/16](https://github.com/google-research/big_vision/blob/main/big_vision/configs/proj/image_text/README_siglip2.md) | 76.79 | 72.64 | 40.35 | 45.35 | 92.99 | 90.01 | 94.71 | 84.53 | 97.53 | 62.94 | 73.09 | 94.05 | 72.95 | 50.19 | 74.87 |
| [PE-Core-B/16](https://huggingface.co/facebook/pe_core_base_patch16_224_timm) | 78.38 | 73.93 | 57.07 | 61.74 | 93.43 | 89.83 | 94.66 | 87.01 | 97.48 | 64.42 | 79.17 | 97.14 | 82.96 | 84.10 | 81.52 |
| [MobileCLIP2-B](https://github.com/apple/ml-mobileclip) | 77.80 | 73.26 | 28.92 | 36.02 | 93.66 | 88.31 | 93.38 | 84.61 | 97.85 | 61.11 | 68.68 | 92.79 | 72.11 | 80.13 | 74.90 |
| **[OSTB Ensemble](https://github.com/Afleve/OSTB)** | **80.36** | **79.03** | **51.91** | **86.90** | **94.76** | **90.26** | **95.12** | **86.52** | **96.35** | **69.74** | **80.33** | **98.18** | **88.28** | **84.05** | **84.41** |

### Remote Sensing

| Model | AID | EuroSAT | MLRSNet | OPTIMAL31 | PatternNet | RESISC45 | RSC11 | RSICB128 | RSICB256 | WHURS19 | Avg |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| [CLIP-B/16](https://github.com/openai/CLIP) | 67.47 | 53.04 | 56.74 | 75.45 | 65.35 | 64.01 | 61.35 | 28.40 | 38.04 | 81.79 | 59.16 |
| [CLIP-B/32](https://github.com/openai/CLIP) | 65.63 | 49.65 | 51.05 | 74.73 | 59.23 | 60.69 | 57.03 | 27.12 | 41.11 | 82.12 | 56.84 |
| [GeoRSCLIP-B/32](https://github.com/om-ai-lab/RS5M) | 70.77 | 47.06 | 64.90 | 79.03 | 75.98 | 68.49 | 68.65 | 28.84 | 46.27 | 87.09 | 63.71 |
| [RemoteCLIP-B/32](https://github.com/ChenDelong1999/RemoteCLIP) | 91.43 | 36.69 | 56.97 | 77.60 | 59.30 | 68.04 | 60.81 | 25.90 | 41.24 | 93.38 | 61.14 |
| [SkyCLIP50-B/32](https://github.com/wangzhecheng/SkyScript) | 70.40 | 55.22 | 63.30 | 79.57 | 74.20 | 66.57 | 62.43 | 39.40 | 47.64 | 91.39 | 65.01 |
| [RS-M-CLIP](https://github.com/DannielSilva/RS-M-CLIP) | 92.60 | 33.15 | 63.96 | 98.39 | 52.20 | 95.82 | 64.59 | 33.83 | 44.64 | 95.70 | 67.49 |
| [RSDiX-CLIP-B/16](https://github.com/NeuRoNeLab/RSDiX-CLIP) | 94.23 | 55.16 | 73.48 | 98.75 | 67.34 | 97.83 | 80.81 | 35.84 | 49.42 | 98.34 | 75.12 |
| [RSDiX-CLIP-B/32](https://github.com/NeuRoNeLab/RSDiX-CLIP) | 92.03 | 49.56 | 67.02 | 96.95 | 60.67 | 97.04 | 80.27 | 32.97 | 46.94 | 96.03 | 71.95 |
| [StreetCLIP](https://huggingface.co/geolocal/StreetCLIP) | 71.77 | 56.91 | 63.54 | 81.90 | 74.45 | 69.61 | 65.68 | 35.46 | 45.27 | 84.11 | 64.87 |
| **[OSTB Ensemble](https://github.com/Afleve/OSTB)** | **98.70** | **89.11** | **84.13** | **99.28** | **96.97** | **98.55** | **88.65** | **51.65** | **59.29** | **99.67** | **86.60** |

### Medical Pathology

| Model | SICAP-MIL | SKINCANCER | SKINTUMOR | LC-LUNG | LC-COLON | Osteo | NCT-CRC | WSSS4LUAD | PanNuke | PCam | BACH | BREAKHIS | Avg |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| [CLIP-B/32](https://github.com/openai/CLIP) | 34.59 | 2.70 | 17.23 | 43.60 | 51.07 | 59.01 | 24.14 | 64.89 | 62.13 | 54.77 | 25.00 | 18.16 | 38.11 |
| [CLIP-B/16](https://github.com/openai/CLIP) | 29.71 | 3.54 | 14.52 | 30.98 | 50.43 | 48.84 | 24.28 | 64.89 | 49.58 | 47.13 | 40.83 | 7.71 | 34.37 |
| [BiomedCLIP](https://huggingface.co/microsoft/BiomedCLIP-PubMedBERT_256-vit_base_patch16_224) | 44.12 | 16.98 | 46.04 | 67.67 | 78.60 | 71.22 | 42.92 | 77.01 | 58.69 | 61.14 | 49.17 | 18.58 | 52.68 |
| [PLIP](https://github.com/PathologyFoundation/plip) | 47.67 | 22.35 | 61.36 | 85.44 | 70.83 | 56.40 | 62.99 | 73.12 | 58.47 | 55.19 | 35.00 | 13.91 | 53.56 |
| [QuiltNet-B/16](https://huggingface.co/wisdomik/QuiltNet-B-16) | 39.69 | 15.98 | 49.18 | 45.49 | 79.53 | 63.37 | 28.38 | 76.25 | 50.16 | 63.92 | 35.83 | 18.71 | 47.21 |
| [QuiltNet-B/32](https://huggingface.co/wisdomik/QuiltNet-B-32) | 29.71 | 38.70 | 60.30 | 78.40 | 87.90 | 41.57 | 51.95 | 75.86 | 48.52 | 58.31 | 36.67 | 19.60 | 52.29 |
| [CONCH](https://github.com/mahmoodlab/CONCH) | 26.61 | 53.73 | 64.83 | 89.51 | 97.23 | 77.03 | 61.31 | 82.20 | 70.44 | 69.95 | 64.17 | 30.34 | 65.61 |
| [UniMed-CLIP](https://github.com/mbzuai-oryx/UniMed-CLIP) | 38.58 | 24.43 | 57.00 | 78.22 | 91.07 | 60.76 | 45.46 | 66.88 | 66.31 | 50.77 | 49.17 | 31.31 | 55.00 |
| [KEEP](https://github.com/MAGIC-AI4Med/KEEP) | 32.37 | 71.27 | 86.53 | 94.07 | 93.90 | 62.50 | 84.99 | 83.49 | 62.18 | 65.68 | 68.33 | 32.24 | 69.80 |
| [PMC-CLIP](https://github.com/WeixiongLin/PMC-CLIP) | 23.73 | 18.19 | 46.31 | 74.64 | 63.63 | 47.97 | 51.62 | 75.79 | 59.48 | 50.90 | 46.67 | 17.99 | 48.08 |
| [PathGen-CLIP](https://huggingface.co/jamessyx/PathGen-CLIP) | 37.25 | 42.94 | 66.87 | 85.02 | 96.63 | 66.86 | 57.23 | 81.54 | 74.36 | 64.89 | 60.83 | 33.84 | 64.02 |
| [MUSK](https://github.com/lilab-stanford/MUSK) | 37.47 | 59.58 | 72.39 | 92.93 | 99.23 | 66.57 | 66.91 | 75.43 | 82.73 | 66.00 | 59.17 | 39.36 | 68.15 |
| **[OSTB Ensemble](https://github.com/Afleve/OSTB)** | **59.42** | **80.43** | **85.12** | **97.76** | **99.60** | **87.79** | **94.71** | **91.51** | **82.10** | 52.96 | **70.00** | 33.54 | **77.91** |





```bibtex


