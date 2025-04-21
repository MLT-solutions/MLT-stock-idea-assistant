# ![MLT Logo](https://github.com/user-attachments/assets/f322d9cc-1adf-45d4-a38d-4764f62cf7bd) MLT Stock Image Automation Assistant

# Documentation & Usage Guide

**MLT Stock Image Assistant** is a Windows GUI tool designed to streamline the entire process of AI-based stock image generation, tagging, and publishing to stock sites such as Dreamstime. Built for creators and coders, it combines **Ollama**, **ComfyUI**, and **Python automation** under one user-friendly interface.

--- 

## 🔗 Quick Links
- [🏠 Home](../README.md)
- [🎯 Use Cases](case.md)
- [📚 Documentation](Documentation.md)
- [🛠 Installation Guide](INSTALLATION_GUIDE.md)
- [👀 Sample Outcome](../sample/sample.md)

---

## 🛠️ Built for Creators & Designers Who Automate

- 💬 Create AI-powered prompts
- 🖼️ Generate images via ComfyUI
- 🏷️ Inject metadata automatically
- 📄 Upload to stock sites (Dreamstime, Adobe)
- 0️⃣ **ZERO SETUP** if you already using ComfyUI & Ollama
- 🆓 **ZERO COST** on own PC
- 📌 Follow company policy NOT to use online AI

## Why You Might Need This
### Pain Points Solved
- Manual image renaming and sorting
- ComfyUI batch setup complexity
- No metadata in JPGs
- Uploading to stock sites one-by-one
- Manual image title and keywords entry

### This App Is For You If:
- You need a visualization idea pool
- You generate lots of AI art
- You want to automate stock uploads
- You enjoy organized & simplified workflows

---

## 🧠 Feature Highlights

- **Prompt Generation with Ollama LLM (e.g., Mistral)**
  - Automatically creates any number of high-quality prompts using a local language model (Free limit to 3)
  - Clean format with `Title`, `Description`, and `Keywords` (new lines for each)

- **Flattened Prompt Conversion**
  - Converts prompts into single-line ComfyUI-compatible format for batch processing

- **One-click ComfyUI Launch**
  - Launches ComfyUI and waits until the API is ready

- **Automated Image Generation**
  - Queues jobs into ComfyUI using SDXL workflow
  - Randomizes model seed
  - Uses: `sd_xl_base_1.0.safetensors`, `sd_xl_refiner_1.0.safetensors`, `dpmpp_2m_sde_gpu`, `karras`, `RealESRGAN_x4plus.pth`

- **Image Completion Wait Logic**
  - Waits for expected number of JPGs to be generated before proceeding

- **Metadata Embedding + CSV Creation**
  - Injects Title, Description, Keywords into JPG IPTC metadata
  - Generates Adobe Stock-compatible CSV

- **Output Management**
  - Sorts JPG and PNG files into timestamped folders (`YYYYMMDDHHMM`)
  - Ensures no overwrite of previous batches

- **FTP Upload (optional)**
  - Uploads latest image batch via FTP to a stock site
  - LATEST = most recent `timestamped folder`

---

## 🚀 Usage Sequence & Button Guide

![App Screenshot](https://github.com/user-attachments/assets/d4e3e899-8e4c-452b-8500-ac7715d274be)


## 📘 How to Use + Tips

### 1. Generate Prompt
- Enter theme/idea into the **"Prompt Theme"** box
- Built-in negative prompts avoid malformed hands, limbs, or NSFW content

### 2. Open Prompt
- You may paste prompts from other tools
- Format must be in 3 lines format without bullet points:
  - Title:
  - Description:
  - Keywords:
- Paste the prompt twice (PRO) for more image variety
- This is the source for embedding metadata into JPGs

### 3. Flatten Prompt
- Converts prompts to single-line format for ComfyUI
- **No prompt limit in PRO version**

### 4. Generate Image
- If a JPG metadata mapping fails, the next ones will still map correctly

### 5. Open JPG Folder
- Output folders use timestamp format `YYYYMMDDHHMM`
- JPGs are separated and upscaled with `RealESRGAN_x4plus.pth` to ensure size ≥ 3MB for 1344 x 768 & 768 x 1344.
- **Important:** Manually delete any low-quality images before uploading
- CSV file is generated with Title/Keywords ready for Adobe Stock—even if some images are deleted

### 6. Upload via FTP
- Set FTP URL, username, and password in the app
- Only JPGs in the **latest timestamped folder** will be uploaded
- After upload, visit the site to confirm tags/descriptions, then submit

### 7. Tips
- If generation is slow, check if **Ollama** is using GPU—terminate via Task Manager
- For big batches, **restart your PC** before starting
- If restarting midway, **exit and relaunch the app** to reset queue tracking

### 8. Known Issues
- If the **last image (e.g., #100)** has broken metadata, it might’ve skipped a line
- **Solutions:**
- 🛠 **Manual:** Use an EXIF viewer (e.g., **XnView MP**) to check for the skipped image
- ⚠️ **Avoid:** Generate smaller batches (e.g., 50 instead of 100)




---

