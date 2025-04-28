<p align="center">
  <img src="https://github.com/user-attachments/assets/de79370d-078c-4448-a996-9624d107cd3b" alt="My Image" width="150"/>
</p>




# SIA - Stock Idea Assistant
### Powered by Modern Logic Tech (MLT™)



***“Your private AI-powered visual assistant that goes from spark to stock-ready.”***

Designers, marketers, and solopreneurs — this is your fast lane from idea to income.


--- 

## 🔗 Quick Links
- [🏠 Home](../README.md)
- [🎯 Use Cases](case.md)
- [✨ Real Results](../sample/sample.md)
- [📚 Documentation & Usage Guide](Documentation.md)
- [🛠 Installation Guide](INSTALLATION_GUIDE.md)
- [🛡️ Privacy Policy](PrivacyPolicy.md)


---

## 🚀 Usage Sequence & Button Guide
![Screenshot 2025-04-27 132843](https://github.com/user-attachments/assets/58551013-dda4-43d9-a09a-6c5239ef7d20)

![App Screenshot](https://github.com/user-attachments/assets/d4e3e899-8e4c-452b-8500-ac7715d274be)
## 🚨 If you wish to rerun same script, just click "3-Generate" again
---

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
  - Gap by [ONE empty line]
- Paste the prompt twice (PRO) for more image variety
- This is the source for embedding metadata into JPGs

### 3. Flatten Prompt
- Converts prompts to single-line format for ComfyUI
- **No prompt limit in PRO version**

### 4. Generate Image
- SDXL Native Resolution supported (before upscale)
  -  1024 x 1024
  -  1152 x 896
  -  896 x 1152
  -  1216 x 832
  -  832 x 1216
  -  1344 x 768
  -  768 x 1344
  -  1536 x 640
  -  640 x 1536
- Randomizes model seed
- Uses: `sd_xl_base_1.0.safetensors`, `sd_xl_refiner_1.0.safetensors`, `dpmpp_2m_sde_gpu`, `karras`, `RealESRGAN_x4plus.pth`
- If a JPG metadata mapping fails, the next ones will still map correctly

### 5. Open JPG Folder
- Output folders use timestamp format `YYYYMMDDHHMM`
- JPGs are separated and upscaled with `RealESRGAN_x4plus.pth` to ensure size ≥ 3MB 
- **Important:** Manually delete any low-quality images before uploading
- CSV file is generated with Title/Keywords ready for Stock site such as Adobe, even if some images are deleted

### 6. Upload via FTP
- Set FTP URL, username, and password in the app
- Only JPGs in the **latest timestamped folder** will be uploaded
- After upload, visit the site to confirm tags/descriptions, then submit

### 7. Tips
- If generation is slow, check if **Ollama** is using GPU—terminate via Task Manager
- For big batches, **restart your PC** before starting
- If restarting midway, **exit and relaunch the app** to reset queue tracking

### 8. Known Issues 
- Even though negative prompts build-in in App, you may still still malform hands
- You may see a **"prompt exceeds 77 tokens"** message in the log — this is expected and **not an error**.
  - Prompts include **title, description, and keywords** for metadata embedding.
  - The 77-token limit (~300–350 characters) account only to the **start of the positive prompt**.
  - This does **not affect image quality** or generation.
- If the **last image (e.g., #100)** has broken metadata, it might’ve skipped a line (Rare)
  - **Solutions:**
    - 🛠 **Manual:** Use an EXIF viewer (e.g., **XnView MP**) to check for the skipped image
    - ⚠️ **Avoid:** Generate smaller batches (e.g., 50 instead of 100)



