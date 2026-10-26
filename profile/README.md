# veizik

**An independent, native AI inference engine.**

veizik is vertically integrated: its own LIM compiler, GPU kernels and memory system, shipped as one signed binary. There is no Python runtime, no deep-learning framework, no CUDA toolkit and no cuBLAS or cuDNN to install. On NVIDIA, the GPU driver is the only prerequisite.

It runs standard published checkpoints in place, with no converted copy. Activation is bound to the device, and generation runs on the device.

## Models

| Platform | Available now | Coming |
| --- | --- | --- |
| NVIDIA (CUDA) | Qwen3.5 and Qwen3.6 language models (image and video input on 35B-A3B); Wan 2.1 and Wan 2.2 video; Stable Diffusion 3.5 image | FLUX.1 |
| Apple Silicon (Metal) | Qwen language models ([veizik-metal](https://github.com/veizikhq/veizik-metal)) | |

## Install

The `veizik` command-line tool is fetched from the GitHub releases and installs each model package:

```
veizik install qwen
```

Installation and usage instructions: https://veizik.com

## Licence

Licensing is per device. One activation covers every published model on that machine. It is free for individual and non-commercial use. Enterprise and commercial use requires a separate licence; contact support@veizik.com. Model weights remain under their own licences.

## Provenance and benchmarks

Every generated image and video carries a provenance mark.

Benchmarks are our own measured figures, published together with the method used: https://veizik.com/benchmarks

[veizik.com](https://veizik.com) · [X @veizikhq](https://x.com/veizikhq) · support@veizik.com
