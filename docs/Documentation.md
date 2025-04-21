# ![Screenshot 2025-04-21 102643](https://github.com/user-attachments/assets/f322d9cc-1adf-45d4-a38d-4764f62cf7bd) MLT Stock Image Automation Assistant
![image](https://github.com/user-attachments/assets/ecf069e2-bc52-4e58-9a50-97ef8abc2ba3)


**MLT Image Automation** is a Windows GUI tool designed to streamline the entire process of AI-based stock image generation, tagging, and publishing to stock sites such as Dreamstime. Built for creators and coders, it combines Ollama, ComfyUI, and Python automation under one user-friendly interface.

# Quick links:
- [🏠 Home](README.md)
- [📚 Documentation](docs/Documentation.md)
- [🛠 Installation](docs/INSTALLATION_GUIDE.md)

## 🚀 Usage Guide sequences & what each button does
![Screenshot 2025-04-21 142959](https://github.com/user-attachments/assets/d4e3e899-8e4c-452b-8500-ac7715d274be)

---

## 🚀 Features Detail

- **Prompt Generation with Ollama LLM (e.g., Mistral)**
  - Automatically creates 10 high-quality prompts using a local language model
  - Clean, structured format with Title, Description, Keywords
- **Flattened Prompt Conversion**
  - Converts prompts into a single line ComfyUI-compatible format for batch processing
- **One-click ComfyUI Launch**
  - Launches ComfyUI and waits until the API is ready
- **Automated Image Generation**
  - Queues jobs into ComfyUI using SDXL workflow
  - Model seed will be randomized
  - sd_xl_base_1.0.safetensors + sd_xl_refiner_1.0.safetensors + dpmpp_2m_sde_gpu + karras + RealESRGAN_x4plus.pth
- **Image Count Wait**
  - Waits until expected number of JPGs are generated
- **Metadata Embedding + CSV Generation**
  - Transfers prompt data into IPTC metadata (JPG)
  - Prepares Adobe Stock-compatible CSV
- **Output File Management**
  - Moves generated JPGs and PNGs into timestamped folders
  - JPG and PNG separated into different folders
- **FTP Upload (optional)**
  - Automatically uploads LATEST folder via FTP (LATEST = Last batch image creation)


# 📘 Stock Image Automation - User Guide & Some tips
1. Generate Prompt
   - Enter your wanted image description in "Prompt Theme" text box
   - Negative prompts already build-in to prevent low quality, malform hand/ limbs & NSFW
     
2. Open prompt
  - can generate with other tool and paste here.
  - make sure ask online AI to generate with this format
	Title:
	Description:
	Keywords:
   - Paste 2 copies of the same prompt set to get more variety of images (PRO)
   - **Note:** this file is for jpg data embed metadata

3. Flatten prompt
   - this is to generate prompt into single line per prompt to start image creation
   - No max prompt limit (PRO)

4. Generate image
   - You may see token error >77 in ComfyUI window, this is normal as our prompt is prepare in consideration of metadata mapping in JPG too
   - If you see one JPG image metadata mapping error and proceeding to next, the later prompts will be map correctly skipping the error one.

5. Open JPG folder
   - You will find many folders with number in YearMonthDayHourMinute format
     This is to ensure all images created are kept and avoid overwrite issue
   - ComfyUI default output PNG.
   - Image in folders here are all JPG upscale using RealESRGAN_x4plus.pth to ensure image is at least 3MB for image 1344 x 768 & 768 x 1344.
   - **Important:** QC and delete not satisfied image before click upload
   - A csv file created in this folder, title and keywords table compatible Adobe upload format. 
     You can directly use this file even if you deleted some low quality photos here

6. Upload FTP
   - You can go to Account of respective stock image site to find URL, ID & password instruction 
   - When you click upload, it will only upload JPG in latest timestamp YearMonthDayHourMinute folder
   - After upload, you still need to go to upload website, check AI tag, description AI generation are done, just click next

7. Tips
   - If you notice image generation very slow, check Task manager to see if ollama taking up GPU resource (End the Task)
   - If you are creating big batch of images repeatedly, it is recommended to restart PC especially if you are not monitoring it
   - If you started Generate Image half way & want to restart the prompt creation process etc, do close the app and restart app.
     (The log will continue to track image count based on earlier queue if not restart)

8. **Known issue:**
   - If you see last image e.g. image 100 mapping failure, that means it accidently skip one line somewhere.
     ***Solution1:*** use exif viewer to check back earlier jpg (manual process), error occurs somewhere 80-90 JPG based on testing.
     You can use **XnView MP** to view & check metadata and picture with ease
    ***Solution2:*** create image in smaller batches




