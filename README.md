# 🎥 Text Behind Person – Video Editing with DeepLabV3

Add **text behind people** in a video using semantic segmentation — no heavy editing software required! This lightweight Python pipeline segments people, blurs the background, and places your custom text in your desired font and style.

---

## 📌 Features

- Person segmentation using **DeepLabV3 (ResNet50)**
- Background **Gaussian blur** applied frame-wise
- Custom **text overlay behind the person**
- Uses **OpenCV** and **Pillow** for frame processing
- Easily customizable font, text, color, and position

---

## 🛠️ Tech Stack

- Python 🐍
- PyTorch
- torchvision
- OpenCV
- PIL (Pillow)

---

## 🎯 Use Cases

- Marketing and product videos 📢  
- Personal branding and promo reels 💼  
- Storytelling & creative content 🎬

---

## ▶️ How It Works

1. Loads the DeepLabV3 model from torchvision.
2. Reads each frame of the video using OpenCV.
3. Segments the **person class** (COCO class ID 15).
4. Applies a blur to the background using the person mask.
5. Adds your custom **text behind the person**.
6. Saves the processed video.

---

## 📁 Usage

1. Clone the repo:

```bash
git clone https://github.com/yourusername/text-behind-person.git
cd text-behind-person
