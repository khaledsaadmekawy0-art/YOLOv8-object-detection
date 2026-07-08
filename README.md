# YOLOv8 Object Detection

## Overview
This project demonstrates **object detection on images** using the pretrained **YOLOv8 Nano** model from **Ultralytics** in **Google Colab**.

The model takes an input image, performs object detection, and displays the result with **bounding boxes** and **class labels** using OpenCV.

---

## Technologies Used
- Python
- YOLOv8 (Ultralytics)
- OpenCV
- Google Colab

---

## Model Used
The project uses the pretrained **YOLOv8 Nano** model:

```python
model = YOLO("yolov8n.pt")
```

This model is lightweight and suitable for basic image object detection tasks.

---

## Project Workflow
1. Load the pretrained YOLOv8 model  
2. Read the input image using OpenCV  
3. Perform object detection on the image  
4. Draw bounding boxes and class labels  
5. Display the annotated output image in Google Colab  

---

## Code
```python
from ultralytics import YOLO
import cv2
from google.colab.patches import cv2_imshow

# Load pretrained YOLOv8 model
model = YOLO("yolov8n.pt")

# Read input image
image = cv2.imread("image.jpg")

# Run object detection
results = model(image)

# Draw bounding boxes and class labels
annotated_image = results[0].plot()

# Display result in Google Colab
cv2_imshow(annotated_image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

---

## Installation
Install the required library:

```bash
pip install ultralytics
```

---

## How to Run
1. Open the notebook or script in Google Colab.
2. Upload an image named `image.jpg`.
3. Run the code.
4. The model will detect objects and display the annotated output image.

---

## Output
The output of the project is an image showing:
- Detected objects
- Bounding boxes around each object
- Object class labels

---

## Future Improvements
- Apply object detection on videos
- Use webcam for real-time detection
- Save the output image automatically
- Use a custom-trained YOLO model for specific datasets
