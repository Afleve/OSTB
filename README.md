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

### Natural Images

| Dataset | Classes | Description |
|---------|---------|-------------|
| ImageNet | 1000 | Natural image benchmark |
| SUN397 | 397 | Scene classification |
| FGVC | 100 | Fine-grained aircraft classification |
| EuroSAT | 10 | Satellite land cover classification |
| Stanford Cars | 196 | Vehicle classification |
| Food101 | 101 | Food classification |
| Oxford Pets | 37 | Pet classification |
| Oxford Flowers | 102 | Flower classification |
| Caltech101 | 100 | Object classification (excluding BACKGROUND_Google and Faces_easy) |
| DTD | 47 | Texture classification |
| UCF101 | 101 | Action recognition |
| CIFAR-10 | 10 | Image classification |
| CIFAR-100 | 100 | Image classification |
| CUB-200-2011 | 200 | Fine-grained bird classification |

### Medical Pathology

| Dataset | Classes | Train | Val | Test | Description |
|---------|---------|-------|-----|------|-------------|
| SICAP-MIL | 4 | - | - | 1501 | Prostate cancer WSIs |
| PCam | 2 | 262144 | 32768 | 32768 | Tumor detection |
| Osteosarcoma | 3 | 800 | - | 344 | Osteosarcoma histology |
| BACH | 4 | 280 | - | 120 | Breast cancer |
| BreakHis | 8 | 5536 | - | 2373 | Breast cancer |
| SkinCancer | 16 | 88971 | 12354 | 28039 | Skin pathology |
| SkinTumor | 4 | 29419 | 4146 | 8851 | Skin tumor |
| LC25000 Lung | 3 | 10500 | - | 4500 | Lung tissue histology |
| LC25000 Colon | 2 | 7000 | - | 3000 | Colon tissue histology |
| NCT-CRC | 9 | 50000 | - | 7180 | Colorectal cancer |
| WSSS4LUAD | 2 | 7063 | - | 3028 | Lung adenocarcinoma |
| PanNuke | 2 | 4346 | - | 1888 | Multi-organ pathology |

### Remote Sensing

| Dataset | Classes | Total | Train | Test | Description |
|---------|---------|-------|-------|------|-------------|
| AID | 30 | 10000 | 7000 | 3000 | Aerial scene classification |
| EuroSAT | 10 | 27000 | 18900 | 8100 | Land cover classification |
| MLRSNet | 46 | 109161 | 76410 | 32751 | Multi-label remote sensing |
| OPTIMAL31 | 31 | 1860 | 1302 | 558 | Scene classification |
| PatternNet | 38 | 30400 | 21280 | 9120 | High-resolution scene |
| RESISC45 | 45 | 31500 | 22050 | 9450 | Scene classification |
| RSC11 | 11 | 1232 | 862 | 370 | Scene classification |
| RSICB128 | 45 | 36707 | 25696 | 11011 | Land cover 128 scale |
| RSICB256 | 35 | 24747 | 17323 | 7424 | Land cover 256 scale |
| WHURS19 | 19 | 1005 | 703 | 302 | Scene classification |


---

## 🙏 Models

### General Purpose VLMs
- [CLIP](https://github.com/openai/CLIP)
- [OpenCLIP](https://github.com/mlfoundations/open_clip)
- [EVA-CLIP](https://github.com/BA-Transform/EVA-CLIP)
- [MetaCLIP](https://github.com/facebookresearch/MetaCLIP)
- [SigLIP 2](https://github.com/google-research/big_vision)
- [ALIGN](https://github.com/tensorflow/models/tree/main/research/optimization)
- [PE-Core](https://github.com/PeaKObject/PE-Core)
- [DeCLIP](https://github.com/sAILab/DeCLIP)
- [FLAVA](https://github.com/facebookresearch/multimodal)
- [SLIP](https://github.com/facebookresearch/SLIP)
- [CoCa](https://github.com/google-research/big_vision)
- [MobileCLIP](https://github.com/Qualcomm-AI-research/MobileCLIP)
- [JinaCLIPv2](https://github.com/jinaai/jina-clip)

### Remote Sensing VLMs
- [CLIP](https://github.com/openai/CLIP)
- [RSDiX-CLIP](https://github.com/NeuRoNeLab/RSDiX-CLIP.git)
- [RS-M-CLIP](https://github.com/DannielSilva/RS-M-CLIP)
- [RemoteCLIP](https://github.com/ChenDelong1999/RemoteCLIP)
- [GeoRSCLIP](https://github.com/AIML-I2R/GeoRSCLIP)
- [SkyCLIP](https://github.com/BMII-CLab/SkyCLIP)
- [StreetCLIP](https://github.com/Alibaba-MIIL/StreetCLIP)

### Medical VLMs
- [CLIP](https://github.com/openai/CLIP)
- [BiomedCLIP](https://github.com/BiomedSciAI/multimodal-biomedical-language-model)
- [PLIP](https://github.com/huangliang12/PLIP)
- [CONCH](https://github.com/MahmoodLab/CONCH)
- [QuiltNet](https://github.com/GeneralAI/QuiltNet)
- [KEEP](https://github.com/ML-AIM/KEED)
- [MUSK](https://github.com/ML-AIM/MUSK)
- [PMC-CLIP](https://github.com/weillmsl/pmc_clip)
- [PathGen-CLIP](https://github.com/PathGenAI/PathGen-CLIP)
- [UniMed-CLIP](https://github.com/mu-cao/UniMed-CLIP)



```bibtex


