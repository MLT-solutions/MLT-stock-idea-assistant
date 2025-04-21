# MLT Stock Image Automation Assistant

**MLT Image Automation** is a Windows GUI tool designed to streamline the entire process of AI-based stock image generation, tagging, and publishing to stock sites such as Dreamstime. Built for creators and coders, it combines Ollama, ComfyUI, and Python automation under one user-friendly interface.

# Quick links:
- [🏠 Home](README.md)
- [📚 Documentation](docs/Documentation.md)
- [🛠 Installation](docs/INSTALLATION_GUIDE.md)



---

## 🚀 Features

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
- **Image Count Wait**
  - Waits until expected number of JPGs are generated
- **Metadata Embedding + CSV Generation**
  - Transfers prompt data into IPTC metadata (JPG)
  - Prepares Adobe Stock-compatible CSV
- **Output File Management**
  - Moves generated JPGs and PNGs into timestamped folders
  - JPG and PNG separated into different folders
- **FTP Upload (optional)**
  - Automatically uploads selected folder to Dreamstime via FTP

# 📘 Stock Image Automation - User Guide

## ✅ Method 1 - Online AI Prompt Creation

1. Open `prompts.txt` and paste your AI-generated prompts.
   - ✅ Recommended: Paste 2 copies of the same prompt set to ensure metadata matches across image sets.
2. Run the app:
   - Either `python main_workflow.py` or click through the GUI.
3. In the CLI or GUI:
   - Select **Step 2** to flatten the prompt.
   - The app will auto-run up to **Step 7** (image generation + metadata + moving to folder).
4. After reviewing and deleting unwanted `.jpg` files:
   - Select **Step 8** to upload approved images to Dreamstime via FTP.

---

## ✅ Method 2 - Local Mistral LLM Prompt Creation

1. (Optional) Edit the prompt design logic in `1prompt.py` or adjust workflow in `main_workflow.py`.
2. Run the app:
   - Either `python main_workflow.py` or launch from GUI.
3. In the CLI or GUI:
   - Select **Step 1** to generate prompts with Mistral.
   - The app will auto-run from Step 2 to Step 7.
4. After reviewing and deleting unwanted `.jpg` files:
   - Select **Step 8** to upload the good ones to Dreamstime via FTP.

---

## 🛠 ComfyUI Setup Notes (One-Time Installation)

1. Install ComfyUI in `C:` or `C:/Users/<yourname>/Documents` for path consistency.
2. Launch ComfyUI manually once.
3. Browse to and **open the "SDXL Simple" workflow** template.
4. Download the following:
   - ✅ **SDXL Model** (for base and refiner)
   - ✅ **RealESRGAN Upscaler** model
5. Ensure the following ComfyUI nodes are working (as used in script):
   - `KSamplerAdvanced`
   - `CLIPTextEncode`
   - `RealESRGAN_x4plus.pth` model in upscaler

---

Enjoy automating your AI-driven stock image workflow!





Ideal folder structure

https://matthewcraft7.gumroad.com/l/qwwvb




Open prompt
can generate with other tool and paste here.
make sure ask online AI to generate with this format
	Title:
	Description:
	Keywords:
paste prompt 2 times (pro)
Note: this file is for jpg data embed metadata

generate prompt
key in your wanted image description in Prompt Theme text box
negative prompts already build into app focusing on
- no show face
- no malform hand

Flatten prompt
this is to generate prompt into single line per prompt to start image creation
No max prompt limite


Generate image
You may see token error >77 in ComfyUI window, this is normal as our prompt is prepare in consideration of metadata mapping in JPG too
If you see one JPG image metadata mapping error and proceeding to next, the later prompts will be map correctly skipping the error one.
Known issue:  If you see last image e.g. image 100 mapping failure, that means it accidently skip one line somewhere.
Solution1: use exif viewer to check back earlier jpg (manual process), error occurs somewhere 80-90 JPG based on testing
Solution2: create image in smaller batches

Open JPG folder
You will find many folders with number in YearMonthDayHourMinute format
This is to ensure all image created are kept and avoid overwrite issue
ComfyUI default output PNG, image in folders here are all JPG upscale using RealESRGAN_x4plus.pth to ensure image is at least 3MB for image 1344 x 768 & 768 x 1344.
Important: QC and delete not satisfied image before click upload
a csv file created with file name, title and keywords table as some websites need to upload in this format


Upload FTP
You can go to Account of respective stock image site to find URL, ID & password instruction 
When you click upload, it will only upload JPG in latest timestamp YearMonthDayHourMinute folder

Tips
- If you notice image generation very slow, check Task manager to see if ollama not close > end task.
- If you are creating big batch of images repeatedly, it is recommended to restart PC especially if you are not monitoring it
- If you started Generate Image half way & want to restart the prompt creation process etc, do close the app and restart app, the log will continue to track image count based on earlier queue.





