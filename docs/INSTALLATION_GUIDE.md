# ![Screenshot 2025-04-21 102643](https://github.com/user-attachments/assets/f322d9cc-1adf-45d4-a38d-4764f62cf7bd) MLT Stock Image Automation Assistant
# Installation Documentation

## Your AI-Powered Visual Ideation Companion

Design smarter, not harder. Whether you're a designer, content creator, or visual storyteller—this tool helps you go from concept to visual faster than ever. No more blank canvas anxiety.

---

# Quick links:
- [🏠 Home](../README.md)
- [🎯 Use Cases](case.md)
- [👀 Sample Outcome](../sample/sample.md)
- [📚 Documentation](Documentation.md)
- [🛠 Installation](INSTALLATION_GUIDE.md)

  
---

## Dependency Checker & Installation Guide: Provided in App
![Screenshot 2025-04-21 100314](https://github.com/user-attachments/assets/c74dfaf8-1fca-44cb-acef-bee0e45411ea)

---

# 🛠 INSTALLATION GUIDE

This guide helps you install **Ollama**, **ComfyUI**, required **custom nodes**, and set up your **folder structure** for the MLT Stock Image Automation Tool. 

[**Windows PowerShell** is used for all the command code installation]

---

## 1. ✅ Ollama Installation

Install Ollama from the official website:

👉 [Download Ollama](https://ollama.com/download)

Steps:
1. Download and install.
2. After installation, run this in PowerShell or terminal:

```bash
ollama run mistral
```

This pulls and prepares the Mistral model used for prompt generation.

---

## 2. 🧰 ComfyUI Installation

You can install ComfyUI anywhere. Here we use your `Documents` folder.

Replace `xxx` with your PC username:

```bash
cd C:\Users\xxx\Documents\
git clone https://github.com/comfyanonymous/ComfyUI.git
```

Resulting folder structure:
```
C:\Users\xxx\Documents\ComfyUI\
```

---

## 3. 🔌 Install Custom Nodes & Models

### A. WAS Node Suite

```bash
cd C:\Users\xxx\Documents\ComfyUI\custom_nodes
git clone https://github.com/WASasquatch/was-node-suite-comfyui.git
```

### B. KSamplerAdvanced (Optional but Recommended)

```bash
cd C:\Users\xxx\Documents\ComfyUI\custom_nodes
git clone https://github.com/Kosinkadink/ComfyUI-Advanced-ControlNet.git
```

---

### C. SDXL Base & Refiner (EASIEST METHOD ✅)

Instead of manually downloading from HuggingFace:

1. Run ComfyUI:
   ```bash
   cd C:\Users\xxx\Documents\ComfyUI\
   python main.py
   ```

2. In the ComfyUI UI:
   - Top left menu → **Workflow** → **Browse templates** → **SDXL → SDXL Simple**

3. A popup will appear to **auto-download** the required base + refiner models.
   - You may be prompted to visit HuggingFace to agree to terms.
   - Once you do that, ComfyUI will download:
     - `sd_xl_base_1.0.safetensors`
     - `sd_xl_refiner_1.0.safetensors`
   - These are automatically placed in `models/checkpoints/`

✅ **Recommended for beginners.**

---

### D. Real-ESRGAN Upscaler

1. Download the model manually:

📦 [Download RealESRGAN_x4plus.pth](https://github.com/xinntao/Real-ESRGAN/blob/master/weights/RealESRGAN_x4plus.pth?raw=true)

2. Place the file into:

```
C:\Users\xxx\Documents\ComfyUI\models\upscale_models\
```

> The "Upscale by Model" node is included in the WAS Node Suite. No extra steps needed.

---

## 4. 🗂 Folder Mapping

Folder locations are flexible. You can set your own paths in the Settings panel.

| Folder Name      | Purpose                                                                 |
|------------------|-------------------------------------------------------------------------|
| `PROMPTS_DIR`    | Temporary prompt file (`prompts.txt`). It gets overwritten each run.   |
| `OUTPUT_JPG`     | Clean final images with metadata (for upload to stock platforms).       |
| `OUTPUT_PNG`     | PNGs with detailed metadata (used for regenerating images).             |

### 📸 Example from Settings Panel

![Screenshot 2025-04-21 100818](https://github.com/user-attachments/assets/d7c74574-67f0-41ea-994a-9fdc7e710c51)

---

## ✅ Final Checklist

- [x] Ollama installed and `mistral` model downloaded
- [x] ComfyUI cloned to `Documents`
- [x] WAS nodes and optional KSampler installed
- [x] SDXL models downloaded via ComfyUI template
- [x] Real-ESRGAN model placed in correct folder
- [x] Folder mapping configured in the GUI settings

---

## 🧪 Test It All Works

Run ComfyUI to verify your setup:

```bash
cd C:\Users\xxx\Documents\ComfyUI\
python main.py
```

- Load the **SDXL Simple** workflow.
- Test image generation and upscaling.

---

Let me know if you need a PDF version or a visual flowchart!
```

---

Would you like this saved and pushed into your GitHub repo automatically (with README link update), or should I generate a downloadable `.md` file?
