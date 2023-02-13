# STVGBert使用说明
## 1. 算法描述

空间-时间视频定位（Spatial-Temporal Video Grounding, STVG）旨在根据查一个查询句子，对未修剪的视频中的目标物体进行时空定位。STVGBert使用一个基于视觉-语言Transformer的单阶段的的框架，它可以同时在空间和时间两个域对目标对象进行定位。
STVGBert是第一个单阶段方法，它可以在不依赖任何预先训练的目标检测器的情况下处理STVG任务。

## 2. 环境依赖

CUDA版本: 11.7
其他依赖库的安装命令如下：

```bash
conda install pytorch torchvision torchaudio pytorch-cuda=11.7 -c pytorch -c nvidia
```

## 3. 下载安装

可使用如下命令下载安装算法包：
```bash
pip install -U mmkg-stvg-bert
```

## 4. 使用示例及运行参数说明

```python
from mmkg_stvg_bert import detector_factory, opts

image_path = "path/to/image"
opt = opts().init()
opt.load_model = "path/to/model"
Detector = detector_factory[opt.task]
detector = Detector(opt)
ret = detector.run(image_path)
```
