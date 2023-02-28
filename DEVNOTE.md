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

```bash
export CUDA_VISIBLE_DEVICES=7 && python gradio_scribble2image_interactive.py
```