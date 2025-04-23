# ![Screenshot 2025-04-21 102643](https://github.com/user-attachments/assets/f322d9cc-1adf-45d4-a38d-4764f62cf7bd) MLT Stock Idea Assistant
# Installation Documentation

## “Your private AI-powered visual assistant that goes from spark to stock-ready.”
Designers, marketers, and solopreneurs — this is your fast lane from idea to income.

---

# Quick links:
- [🏠 Home](../README.md)
- [🎯 Use Cases](case.md)
- [👀 Sample Outcome](../sample/sample.md)
- [📚 Documentation & Usage Guide](Documentation.md)
- [🛠 Installation](INSTALLATION_GUIDE.md)

  
---

# MLT Stock Image Assistant Installation & 🗂 Folder Mapping
1. Just double click to install the exe installer.
2. Folder locations are flexible. You can set your own paths in the Settings panel.

| Folder Name      | Purpose                                                                 |
|------------------|-------------------------------------------------------------------------|
| `PROMPTS_DIR`    | Temporary prompt file (`prompts.txt`). It gets overwritten each run.   |
| `OUTPUT_JPG`     | Clean final images with metadata (for upload to stock platforms).       |
| `OUTPUT_PNG`     | PNGs with detailed metadata (used for regenerating images).             |

### 📸 Example from Settings Panel

![Screenshot 2025-04-21 100818](https://github.com/user-attachments/assets/d7c74574-67f0-41ea-994a-9fdc7e710c51)

---

# Dependency Checker [Click the second button on the left]
![Screenshot 2025-04-21 100314](https://github.com/user-attachments/assets/c74dfaf8-1fca-44cb-acef-bee0e45411ea)

---

# 🛠 Dependencies Installation Guide

This guide helps you install **Ollama**, **ComfyUI**, required **custom nodes**, and set up your **folder structure** for the MLT Stock Image Automation Tool. 

[**Windows PowerShell** is used for all the command code installation]

---

## 1. ✅ Ollama Installation

Install Ollama from the official website:

- 👉 [Download Ollama](https://ollama.com/download)

Steps:
1. Download and install.
2. After installation, run this in PowerShell or terminal:

```bash
ollama run mistral
```

This pulls and prepares the Mistral model used for prompt generation.

---

## 2A. 🧰 Git Bash
If never install Git before, Download Git
Go to the official Git website:
👉 [Download Git](https://git-scm.com/downloads)

Run the Installer

---

## 2B. 🧰 ComfyUI Installation

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

### A. 📦 Install ComfyUI Manager (Recommended for Managing Nodes Easily)

Use ComfyUI Manager to install and manage custom nodes without manual Git operations.

1. Open terminal:
   ```bash
   cd C:\Users\xxx\Documents\ComfyUI\custom_nodes
   git clone https://github.com/ltdrdata/ComfyUI-Manager.git
   
   ```

2. Restart ComfyUI.
   ```bash
   cd C:\Users\xxx\Documents\ComfyUI\
   python main.py
   ```
   
3. In the ComfyUI interface (http://127.0.0.1:8188), go to:
   - **Top-right menu → Manager**

---

### B. 🧰 Use ComfyUI Manager to Install These Nodes

After installing the Manager, do the following inside ComfyUI:

#### ➕ WAS Node Suite

1. Go to: **Manager → Custom Nodes**
2. Search: `was-node`
3. Click **Install** next to `WAS Node Suite`

#### 🔼 Real-ESRGAN Upscaler Support

1. Go to: **Manager → Custom Nodes**
2. Search: `RealESRGAN`
3. Click **Install** (you may be prompted to download model weights)

> The node "Upscale by Model" will appear under your image processing node list after installation.

### Extended Save Image for ComfyUI
```
 cd C:\Users\xxx\Documents\ComfyUI\custom_nodes
git clone https://github.com/palant/extended-saveimage-comfyui
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



## ✅ Final Checklist

- [x] Ollama installed and `mistral` model downloaded
- [x] ComfyUI cloned to `Documents`
- [x] WAS nodes and optional KSampler installed
- [x] SDXL models downloaded via ComfyUI template
- [x] Real-ESRGAN model placed in correct folder
- [x] Folder mapping configured in the GUI settings

