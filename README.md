# ⭐️ RTX 5000 Wheels

![Python 3.12](https://img.shields.io/badge/Python-3.12-blue)
![CUDA 12.8](https://img.shields.io/badge/CUDA-12.8-green)
![Linux](https://img.shields.io/badge/OS-Linux-important)
![GPU   RTX 5000 Series](https://img.shields.io/badge/GPU-RTX%205000%20Series-orange)

> **Unofficial, performance‑tuned Python wheels for NVIDIA RTX 50‑series GPUs (Blackwell architecture, compute capability 9.0+).**  
> Built and tested on Ubuntu 24.04 LTS with Python 3.12 and CUDA 12.8.

---

## 📦 Why does this repo exist?

Have you been pulling every single hair out of your head trying to use some 3D / AI libraries with the new RTX 5000 GPUs these last few months? So have we with my friend https://github.com/dickoah. So we brought out the big guns, built every single wheel that we lacked, and decided to share them with the community!

NVIDIA’s cutting‑edge RTX 50‑series GPUs expose new compute capabilities (`sm_90`) that are not always available in upstream pre‑built Python wheels released by popular ML/DL frameworks. Rebuilding these packages locally is doable but time‑consuming and error‑prone.  **This repository provides drop‑in wheels so you can start coding immediately** without having to:

1. Clone gigantic source trees.
2. Patch build scripts for Blackwell GPUs.
3. Wait hours for compilation.

If you have an RTX 5090/5080/5070 (or any "RTX 5000" SKU), these wheels should “just work”.

> **Disclaimer:** These builds are **unofficial** and **not** endorsed by the original package authors or NVIDIA. Use at your own risk.

---

## 🚀 Quick installation

```bash
# 1. Clone this repository (or download the wheels directory)
$ git clone https://github.com/maepopi/rtx5000wheels.git
$ cd rtx5000wheels

# 2. (Recommended) Create a fresh virtual environment
$ python3.12 -m venv .venv
$ source .venv/bin/activate

# 3. Install any wheel(s) you need
$ pip install --no-index --find-links ./wheels torch torchvision torchaudio

# 4. Verify that CUDA sees your GPU
$ python - <<'PY'
import torch, platform, subprocess, json, os
print("Torch CUDA available:", torch.cuda.is_available())
print("GPU name:", torch.cuda.get_device_name(0))
print("CUDA version:", torch.version.cuda)
PY
```

If you only need a single wheel, you can install directly from the file:

```bash
pip install wheels/torch-2.3.0+cu128-cp312-cp312-linux_x86_64.whl
```

---

For the really big libraries such as Torch or Flash Attention, I've uploaded them here :
- Download [Flash Attention](https://drive.google.com/file/d/1JPdDaVI7WAjL1ZmLwaCYTKGQ2armTdzY/view?usp=drive_link)
- Download [Torch](https://drive.google.com/file/d/17itz_wyvDjL2RwL_OO323T13F5RE5sYO/view?usp=drive_link)




## ✨ Acknowledgements

* NVIDIA for CUDA and the amazing RTX 50‑series hardware.
* Made by [Maelys](https://github.com/maepopi) & [Ali](https://github.com/dickoah)

---
