# veizik

**An independent, native AI inference engine.**

veizik runs language, video and image models locally, on your own GPU.
It is vertically integrated: its own LIM compiler, GPU kernels and memory system,
shipped as sealed, model-specific engine packages.

There is no cloud at inference time.
Prompts and outputs stay on your machine.

It reads standard published checkpoints that you download yourself (for example from Hugging Face),
and runs them in place, with no converted copy.
Activation is bound to the device, and generation runs on the device.

## Models

| Platform | Available now | In preparation |
| --- | --- | --- |
| NVIDIA (CUDA) | Qwen3.5 and Qwen3.6 language models (image and video input on 35B-A3B through the package launcher); Wan 2.1 and Wan 2.2 video | FLUX.1-dev and Stable Diffusion 3.5 images (not in a download yet) |
| Apple Silicon (Metal) | Qwen2.5 and Qwen3 language models ([veizik-metal](https://github.com/veizikhq/veizik-metal)) | |

## Requirements

**NVIDIA / Linux**

- An NVIDIA GPU of compute capability 8.0 or newer.
- An NVIDIA driver that provides `libcuda.so.1`.
  No CUDA toolkit and no Python are needed, only the driver.
- Linux x86-64, running natively (WSL is not supported).
- One build covers both the CUDA 12 and CUDA 13 driver series.
  There is no separate "CUDA 12" or "CUDA 13" download.
- GPU code ships as precompiled per-architecture sets:
  sm_80, sm_86, sm_89, sm_90a, sm_100a and sm_120a.

**Apple / macOS**

- Apple Silicon (M1 or newer).
- macOS 13 or later.
  macOS 13 is the minimum, not a fixed version; newer releases work.

**No bundled dependencies**

The engine is a single binary.
It embeds no Python, framework, numeric library or CUDA toolkit.
Its only external dependency is the system GPU driver (NVIDIA `libcuda.so.1`) or Apple Metal,
and nothing inside the engine ties it to a specific toolkit or OS version.

## Install

The `veizik` command-line tool is fetched from the GitHub releases and installs each model package:

```
curl -fsSL https://veizik.com/install.sh | sh      # the veizik command (Linux x86-64 / aarch64, macOS arm64)
veizik install qwen        # or: wan
veizik activate            # once per device
```

Installation and usage instructions: https://veizik.com

## Licence

Licensing is per device.
One activation covers every published model on that machine.

Personal, educational, research and evaluation use is at no charge.
Commercial use requires a separate licence; contact support@veizik.com.
Publishing benchmarks is allowed.
Model weights remain under their publishers' licences.

## Provenance and benchmarks

Every generated image and video carries a provenance mark.

Benchmarks are our own measured figures, published together with the method used:
https://veizik.com/benchmarks

[veizik.com](https://veizik.com) · [X @veizikhq](https://x.com/veizikhq) · [Bluesky @veizik.com](https://bsky.app/profile/veizik.com) · support@veizik.com
