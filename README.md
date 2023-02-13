# STVGBert使用说明

## 1. 环境依赖

CUDA版本: 11.7
其他依赖库的安装命令如下：

```bash
conda install pytorch torchvision torchaudio pytorch-cuda=11.7 -c pytorch -c nvidia
```

## 2. 下载安装

可使用如下命令下载安装算法包：
```bash
pip install -U mmkg-stvg-bert
```

## 3. 使用示例及运行参数说明

```python
from mmkg_stvg_bert import detector_factory, opts

image_path = "path/to/image"
opt = opts().init()
opt.load_model = "path/to/model"
Detector = detector_factory[opt.task]
detector = Detector(opt)
ret = detector.run(image_path)
```
