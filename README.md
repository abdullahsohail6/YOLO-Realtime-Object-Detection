📌 Overview
This project demonstrates real-time object detection using the YOLOv8 architecture, executed directly in a Google Colab notebook. By leveraging a JavaScript-to-Python webcam bridge, the system captures live video frames from the user's browser, runs inference using a pre-trained YOLOv8 model, and renders annotated results with bounding boxes, class labels, and confidence scores — all without requiring any local setup.
The notebook is structured into clear, sequential steps, making it accessible for beginners while remaining flexible enough for advanced users to customize model size, confidence thresholds, and output destinations.

✨ Features

🔴 Live Webcam Detection — Captures real-time frames directly from your browser camera
🤖 YOLOv8 Inference — Powered by Ultralytics YOLOv8 with support for multiple model sizes
🎨 Visual Annotations — Bounding boxes with unique per-class colors, labels, and confidence scores
📊 Live Stats Overlay — Real-time FPS counter, object count, model name, and device displayed on each frame
🎛️ Interactive Controls — Confidence threshold slider and model selector built with ipywidgets
💾 Google Drive Export — Save annotated detection frames directly to your Google Drive
⚡ GPU Accelerated — Optimized for NVIDIA T4 GPU available on Google Colab
🏷️ 80 Object Classes — Detects all COCO dataset categories including people, vehicles, animals, and everyday objects


🗂️ Project Structure
📦 yolo-realtime-detection/
 ┣ 📓 YOLO_Realtime_Object_Detection.ipynb   ← Main Colab notebook
 ┗ 📄 README.md                               ← Project documentation

🚀 Getting Started
Prerequisites
No local installation is required. You only need:

A Google account
A modern web browser (Chrome or Firefox recommended)
A working webcam

Running the Notebook

Open Google Colab
Upload the YOLO_Realtime_Object_Detection.ipynb notebook
Navigate to Runtime → Change runtime type and select T4 GPU
Run each cell sequentially from top to bottom
When prompted, allow camera access in your browser


⚠️ Camera permission must be granted in the browser for webcam capture to function correctly.


📋 Notebook Walkthrough
The notebook is organized into 9 clearly labeled steps:
StepTitleDescription1Install LibrariesInstalls all required dependencies including Ultralytics, OpenCV, Pillow, and ipywidgets2Import & Verify GPUImports all modules and confirms CUDA GPU availability3Load YOLOv8 ModelDownloads and initializes the selected YOLOv8 model4Helper FunctionsDefines utilities for drawing detections and converting image formats5Webcam JS BridgeSets up the JavaScript bridge to access the browser webcam from Python6Single Frame TestCaptures one test frame to verify the full pipeline before live mode7Live Detection LoopMain loop — runs continuous real-time YOLO detection on webcam feed8Save to Drive (Optional)Captures and saves annotated frames to a Google Drive folder9Interactive Controls (Optional)Provides a GUI with sliders and dropdowns for live configuration

🤖 Model Options
Select the model that best fits your speed vs. accuracy requirements:
ModelSizeSpeedAccuracyBest Foryolov8nNano⚡ Fastest⭐ GoodReal-time, resource-limitedyolov8sSmall🚀 Fast⭐⭐ BetterBalanced performanceyolov8mMedium🏃 Moderate⭐⭐⭐ HighHigher accuracy needsyolov8lLarge🐢 Slower⭐⭐⭐⭐ ExcellentMaximum accuracy
The default model is yolov8n (Nano), which provides the best real-time performance on Colab's T4 GPU.

🏷️ Detectable Object Classes
This project uses models pre-trained on the COCO dataset, which includes 80 object categories:
<details>
<summary>View all 80 classes</summary>
Person, Bicycle, Car, Motorcycle, Airplane, Bus, Train, Truck, Boat, Traffic Light, Fire Hydrant, Stop Sign, Parking Meter, Bench, Bird, Cat, Dog, Horse, Sheep, Cow, Elephant, Bear, Zebra, Giraffe, Backpack, Umbrella, Handbag, Tie, Suitcase, Frisbee, Skis, Snowboard, Sports Ball, Kite, Baseball Bat, Baseball Glove, Skateboard, Surfboard, Tennis Racket, Bottle, Wine Glass, Cup, Fork, Knife, Spoon, Bowl, Banana, Apple, Sandwich, Orange, Broccoli, Carrot, Hot Dog, Pizza, Donut, Cake, Chair, Couch, Potted Plant, Bed, Dining Table, Toilet, TV, Laptop, Mouse, Remote, Keyboard, Cell Phone, Microwave, Oven, Toaster, Sink, Refrigerator, Book, Clock, Vase, Scissors, Teddy Bear, Hair Drier, Toothbrush
</details>

⚙️ Configuration Reference
The following parameters in Step 7 can be adjusted to customize detection behavior:
ParameterDefaultDescriptionCONF_THRESHOLD0.45Minimum confidence score required to display a detectionMAX_FRAMES100Total number of frames to process before stoppingDISPLAY_EVERY1Render output every N-th frame (increase to reduce display lag)MODEL_NAMEyolov8n.ptYOLOv8 model variant to use for inference

📈 Performance Expectations
RuntimeApproximate FPST4 GPU (Colab)5 – 15 FPSCPU Only1 – 3 FPS

Enabling the T4 GPU in Colab is strongly recommended for a smooth real-time experience.


🛠️ Tech Stack
ComponentTechnologyObject DetectionUltralytics YOLOv8Computer VisionOpenCVDeep Learning FrameworkPyTorchNotebook EnvironmentGoogle ColabWebcam AccessJavaScript (browser API)Interactive WidgetsipywidgetsImage ProcessingPillow (PIL)

🔧 Troubleshooting
Camera not working?
Ensure you have clicked "Allow" when the browser requests camera permission. In Chrome, check the camera icon in the address bar to manage permissions.
Low FPS or slow detection?
Verify that the GPU runtime is enabled under Runtime → Change runtime type → T4 GPU. Using yolov8n also provides the fastest inference speed.
Model download fails?
Ensure the Colab session has an active internet connection. The model is downloaded automatically on first use from the Ultralytics servers.
Drive mount not working?
Re-run the Drive mount cell and follow the authentication prompts in the popup window.

📄 License
This project is distributed under the MIT License. See the LICENSE file for full details.
The YOLOv8 model weights are subject to the Ultralytics License.

🙏 Acknowledgements

Ultralytics for developing and maintaining the YOLOv8 framework
Google Colab for providing free GPU-accelerated cloud notebooks
The COCO Dataset team for the object detection benchmark and annotations


<div align="center">
