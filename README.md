# 🦴 Volumetric CT-to-MRI Pelvis Synthesis

This project provides a deep learning framework for **volumetric (3D) paired CT-to-MRI image synthesis** for pelvic images. It leverages fully volumetric GAN training, validation and test.

⚠️ This project is under active development.  
To access full code or collaborate, please contact the author:  
mehrankhodadadzadeh90@gmail.com

---

## 🖼️ Example Output

Example CT-to-MRI synthesis:

- Predicted MRI (`synth_mri_01_*.nii.gz`)  
- Ground-truth MRI (`gt_mri_01_*.nii.gz`)  
- Evaluation metrics (`metrics_summary.csv`)


![Example MRI-to-CT synthesis](test.png)

---

## ✅ What This Framework Does

- Translates **pelvis CT volumes** to synthetic **MRI**
- Uses patch-wise **GAN training** with volumetric 3D models
- Evaluates output quality using **MAE**, **PSNR**, and **SSIM** inside anatomical masks
- Supports both **simple training** and **k-fold cross-validation**
- Supports multiple architectures:
  - `UNet3D`
  - `Swin-UNETR`  

---

## 📁 Dataset Format

Each patient folder should contain:

dataset_root/
├── patient001/
│ ├── ct.nii.gz # input CT
│ ├── mr.nii.gz # ground-truth MRI
│ └── mask.nii.gz # binary mask for evaluation

## 🏋️‍♂️ To Train the Model

Edit `main.py` to set paths and parameters

Then run:

bash
Copy
Edit
python main.py



o Run Inference
Edit paths in inference.py:

python
Copy
Edit
CHECKPOINT = "/path/to/best_generator.pth"
TEST_DIR   = "/path/to/test_data"
OUTPUT_DIR = "/path/to/save/output"
GENERATOR  = "attention_unet"
PATCH_SIZE = (64, 64, 64)
BASE_CH    = 32
Then run:

bash
Copy
Edit
python inference.py

You can install all dependencies with:

bash
Copy
Edit
pip install -r requirements.txt
Or manually install:

bash
Copy
Edit
torch==2.1.2  
monai==1.3.0  
nibabel==5.2.0  
scikit-image==0.22.0  
scikit-learn==1.4.2  
tqdm==4.66.1  
wandb==0.16.1  
numpy>=1.23  
pandas>=1.5  
yaml
Copy
Edit

---

✅ You can now paste this into a `README.md` file in your GitHub repo. Let me know if you want it sav
