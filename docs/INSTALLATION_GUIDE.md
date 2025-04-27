<p align="center">
  <img src="https://github.com/user-attachments/assets/f322d9cc-1adf-45d4-a38d-4764f62cf7bd" alt="My Image" width="400"/>
</p>



# ![Screenshot 2025-04-21 102643](https://github.com/user-attachments/assets/f322d9cc-1adf-45d4-a38d-4764f62cf7bd) MLT Stock Idea Assistant
# Installation Documentation

## “Your private AI-powered visual assistant that goes from spark to stock-ready.”
Designers, marketers, and solopreneurs — this is your fast lane from idea to income.

---

# Quick links:
- [🏠 Home](../README.md)
- [🎯 Use Cases](case.md)
- [✨ Real Results](../sample/sample.md)
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

# Dependency Checker [Main GUI - Click the second button on the left]
![Screenshot 2025-04-24 214439](https://github.com/user-attachments/assets/22f0beaa-6212-485d-9cb9-20b5b2dbd2e3)

---

# 🛠 Dependencies Installation Guide

This guide helps you install **Ollama**, **ComfyUI**, required **custom nodes**, and set up your **folder structure** for the MLT Stock Idea Assistant. 

[**Windows PowerShell** is used for all the command code installation]

    ```
    When ever you see instruction to go into a folder, e.g.:
    C:\Users\xxx\Documents\ComfyUI\
    
    You can use Window Explorer to go to that folder, then Right-Click --> Open Terminal
    Paste the "CODE" and Press ENTER.

    You will see your xxx username when you Open Terminal via right-click in Documents

    ```

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

## 2. </> Git Bash
If never install Git before
Go to the official Git website:
- 👉 [Download Git](https://git-scm.com/downloads)

Steps:
1. Download and install.

---

## 3. 🐍 Python
Open Command Prompt and follow command in image to do status check:
![Screenshot 2025-04-27 131157](https://github.com/user-attachments/assets/1a09d86e-f2ec-4857-987a-448e520cd500)



1. If never install Python before (0 LINE return), go to the Microsoft Store and install Python 3.12
   - 👉 [Download Python 3.12](https://apps.microsoft.com/detail/9ncvdn91xzqp?hl=en-US&gl=US)
   - Download & install.

2. If you see 1 line or more lines of phyton.exe path, that means you have more than 1 phyton in your system.
   - If you had Microsoft Store Python before, it will stay as LINE 1 even you have uninstalled it (suggest reinstall it)
   - For all the following installation, use Command Prompt should warrant all installation go into default Python.

---

## 4. 🧰 ComfyUI Installation

You can install ComfyUI anywhere. Here we use your `Documents` folder.

Replace `xxx` with your PC username:

```
    cd C:\Users\xxx\Documents\
    git clone https://github.com/comfyanonymous/ComfyUI.git
```

Resulting folder structure:
```
    C:\Users\xxx\Documents\ComfyUI\
```

---

## 5. 🔦 Pytorch Installation
1. Open PowerShell (anywhere) and enter
     ```
     nvidia-smi
     ```
2. Read top right of table for something like CUDA 12.9
3. Visit https://pytorch.org/get-started/locally/ to identify the right python installation code
4. My PC is CUDA 12.9 - Selecting Stable Window pip python cuda 12.6
     ```
     pip3 install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu126
     ```  
6. After installation, Open PowerShell (anywhere) and enter
     ```
     import torch
     print(torch.cuda.is_available())  # Should print True if CUDA is available
     print(torch.cuda.current_device())  # Should print the GPU device index (usually 0)
     print(torch.cuda.get_device_name(0))  # Should print the name of the GPU (e.g., "NVIDIA GeForce RTX 4060")
     ```
---

## 6. 🧰 ComfyUI's Requirement Installation
```
This MUST be AFTER PyTorch Installation
```
1. Open PowerShell, Replace `xxx` with your PC username:
    ```bash
    cd C:\Users\xxx\Documents\ComfyUI\
    pip install -r requirements.txt
    ```
## 7. ⚙️ Environment Variables > User Variables 
1. Add the script directory to PATH: You can add the directory where the scripts are installed to your system PATH by following these steps:
2. Open System Properties → Environment Variables.
3. Under " "User Variables", find Path and click Edit.
4. Add the following directory to the path (based on the warning ORANGE text appear in PowerShell):
    ```
    C:\Users\xxx\AppData\Local\Packages\PythonSoftwareFoundation.Python.3.12_qbz5n2kfra8p0\LocalCache\local-packages\Python312\Scripts
    ```

### Run ComfyUI: Now you should be able to run ComfyUI or its components via the terminal/command prompt. If you need any help running or configuring ComfyUI, just let me know!


---

## 8. 🔌 Install Custom Nodes & Models

### A. 📦 Install ComfyUI Manager (Recommended for Managing Nodes Easily)

Use ComfyUI Manager to install and manage custom nodes without manual Git operations.

1. Open terminal:
   ```bash
   cd C:\Users\xxx\Documents\ComfyUI\custom_nodes
   git clone https://github.com/ltdrdata/ComfyUI-Manager.git
   
   ```

2. Close the PowerShell Window & Restart ComfyUI.
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
4. Restart Required to see is go live

#### 🔼 RealESRGAN_x4plus.pth

1. Go to: [RealESRGAN_x4plus.pth Website](https://huggingface.co/lllyasviel/Annotators/blob/main/RealESRGAN_x4plus.pth)
2. Click **Download** 
3. Move the Downloaded file from **Download Folder** to C:\Users\xxx\Documents\ComfyUI\models\upscale_models

### 💾 Extended Save Image for ComfyUI
1. Open PowerShell anywhere (or right click in custom_nodes)
    ```
     cd C:\Users\xxx\Documents\ComfyUI\custom_nodes
    git clone https://github.com/palant/extended-saveimage-comfyui
    ```
2. If you have conflict of **SaveImageExtended**, look for this folder ComfyUI\custom_nodes\save-image-extended-comfyui and **delete it**.
3. If you want to use both versions someday:
   - Edit save-image-extended-comfyui  script and change** class SaveImageExtended ➝ SaveImageExtendedV2**
    ```
    In NODE_CLASS_MAPPINGS: change to "SaveImageExtendedV2": SaveImageExtendedV2
    ```
---

### C. SDXL Base & Refiner 

Instead of manually downloading from HuggingFace:

1. Open PowerShell anywhere, use code below to run ComfyUI:
   ```bash
   cd C:\Users\xxx\Documents\ComfyUI\
   python main.py
   ```

2. In the ComfyUI UI:
   - Top left menu → **Workflow** → **Browse templates** → **SDXL → SDXL Simple**
   - Another alternative path may be:
     - Top left menu → **Workflow** → **Browse templates** → **Image → SDXL Simple**

3. A popup will appear to **auto-download** the required base + refiner models.
   - You may be prompted to visit HuggingFace to agree to terms.
   - Once you do that, ComfyUI will download:
     - `sd_xl_base_1.0.safetensors`
     - `sd_xl_refiner_1.0.safetensors`
   - If these are NOT automatically placed in `models/checkpoints/`, copy them from Download Folder and moved to `models/checkpoints/`



## ✅ Final Checklist

- [x] Ollama installed and `mistral` model downloaded
- [x] ComfyUI cloned to `Documents`
- [x] ComfyUI Manager installed
- [x] WAS nodes installed
- [x] Real-ESRGAN model placed in correct folder
- [x] Extended Save Image for ComfyUI
- [x] SDXL base & refiner models downloaded via ComfyUI template
- [x] Folder mapping configured in the GUI settings

