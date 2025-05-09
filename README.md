# Text-Behind-You-video-
# Text Behind Person in Video

This project takes an input video, identifies people in it using a DeepLabV3 segmentation model, and renders specified text "behind" them on a slightly blurred background. The output is a new video with this effect applied.

## Features

* **Person Segmentation:** Uses a pre-trained DeepLabV3 (ResNet50 backbone) model from PyTorch Hub to create a mask for people in each frame.
* **Text Placement:** Renders user-defined text.
* **Background Effect:** The background behind the person (where the text appears) is slightly blurred.
* **Video Processing:** Reads an input video, processes each frame, and writes to an output video file.

## How it Works

For each frame of the input video:
1.  The frame is converted from OpenCV's BGR format to a PIL Image (RGB).
2.  The PIL Image is preprocessed (tensor conversion, normalization) and fed into the DeepLabV3 model to get a segmentation mask.
3.  A binary mask is created specifically for the "person" class (class ID 15 in COCO).
4.  The original frame (PIL image) is blurred to create a background layer.
5.  The desired text is drawn onto this blurred background layer. The text is centered by default.
6.  The final frame is composited:
    * Where the person mask is active (person), the original sharp pixels of the person are shown.
    * Where the person mask is not active (background), the blurred background with the text is shown.
7.  The processed PIL Image is converted back to OpenCV format and written to the output video.

## Requirements

* Python 3.x
* PyTorch (`torch`, `torchvision`)
* Pillow (`PIL`)
* OpenCV (`cv2`)
* NumPy (`numpy`)


