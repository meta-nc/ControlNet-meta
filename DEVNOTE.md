# DEVNOTE

## Environment
- pyenv
- conda (miniconda3)

```bash
(control) leeminxji@am04:~/repos/ControlNet$ which python
/home/leeminxji/miniconda3/envs/control/bin/python
(control) leeminxji@am04:~/repos/ControlNet$ conda -V
conda 23.1.0
```

## Development

[README.md#production-ready-pretrained-models](README.md#production-ready-pretrained-models) 참고

### Step 1

```bash
conda env create -f environment.yaml
conda activate control
```

### Step 2

모델/설정 파일 다운로드

> 리모트 서버에서도 쉽고 빠르게 Hugging Face 파일을 다운받는 방법
> - https://huggingface.co/docs/huggingface_hub/how-to-downstream#download-and-store-a-file-from-the-hub

```bash
minx@g501:~/repos/ControlNet-meta$ python
Python 3.8.5 (default, Sep  4 2020, 07:30:14)
[GCC 7.3.0] :: Anaconda, Inc. on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> from huggingface_hub import hf_hub_download
>>> hf_hub_download(repo_id="lllyasviel/ControlNet", filename="models/control_sd15_scribble.pth")
Downloading (…)_sd15_scribble.pth";: 100%|█████████████████████████████████████████████████████| 5.71G/5.71G [00:26<00:00, 218MB/s]'/home/minx/.cache/huggingface/hub/models--lllyasviel--ControlNet/snapshots/e78a8c4a5052a238198043ee5c0cb44e22abb9f7/models/control_sd15_scribble.pth'
```

```
minx@g501:~/repos/ControlNet-meta$ cp /home/minx/.cache/huggingface/hub/models--lllyasviel--ControlNet/snapshots/e78a8c4a5052a238198043ee5c0cb44e22abb9f7/models/control_sd15_scribble.pth models/control_sd15_scribble.pth
```

### Step 3

```bash
python gradio_scribble2image_interactive.py
# export CUDA_VISIBLE_DEVICES=7 && python gradio_scribble2image_interactive.py
```
