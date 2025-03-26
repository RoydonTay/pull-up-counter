# Pull Up Counter using YOLOv11

In this project, I use **pose estimation** and **object detection** with **pre-trained YOLOv11** models to analyse videos and count pull-ups automatically in videos.

https://github.com/user-attachments/assets/26514c9c-e71e-4c48-a14e-51618014aeb8

## Method:
I used both the bounding box for pull-up bars from the object detection model, and keypoints of the person's body from the pose estimation model to detect pull-up repetitions. 

Fine-tuning was required to help YOLO object detection model identify pull-up bars. All inference and training was done using the **Ultralytics** package. Other operations like reading and writing the video, creating annotations and pull-up counting logic was implemented with **OpenCV**.

### Training parameters (fine-tuning for pull-up bar detection):
- epochs=300
- imgsz=640
- batch=-1 (adjust automatically based on GPU available)
- Dataset size: 106 images + 96 Augmented images (images of people doing pull-ups in different environments, with augmentations such as slight rotations to create more train examples)

#### Compute Resource
- Platform: Google Colab
- GPU: NVIDIA T4 (16GB VRAM)