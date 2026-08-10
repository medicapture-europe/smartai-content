# **aiScope: Medical AI Made Easy**

*by MediCapture Inc.*

## **aiScope Introduction**

aiScope is a built-in feature for the MediCapture MVR/MTR series of medical video recorders. It uses artificial intelligence to detect objects and classify images. aiScope outputs real-time data for external devices, such as tracking cameras, and saves data for further analysis and reporting. Optionally, aiScope can augment video input in real time with graphic overlays that can assist surgeons in making informed decisions or drawing their attention to specific features during surgical procedures.

Researchers can use aiScope to evaluate new ideas and create custom datasets.

* **Vendor-neutral:** Works with medical imaging devices of any brand.  
* **Open Source:** Open source models and training; open source online models conversion and deployment; community-developed models, models marketplace.

aiScope solves the "last mile" problem. Researchers typically develop models on PCs with GPUs, but deploying them for real-time surgical use requires a dedicated, robust hardware setup. aiScope provides a practical solution as a built-in feature of a certified medical video recorder.

### **Availability**

aiScope is available for device models MTR133, MTR156, and MVR436. It comes preloaded with modern, state-of-the-art open-source vision AI models. aiScope evaluation can be initiated with a few taps, requires no extra installation, and is free of charge.

## **How It Works**

Once video input is activated (Study Started), the assigned AI model is automatically loaded and performs inference for every input video frame. Inference results data are output in a JSON string, including the frame number and time stamp, and can be read via the LAN port in real time. Inference results can be visualized over the live video as graphic boxes and text overlays.

### **Processing Pipeline**

1. **Frame Acquisition:** The next video frame is acquired (sources: HDMI or USB-UVC; resolution from 400x400 to 4096x2160 pixels).  
2. **Scaling:** The acquired frame is scaled to match the model input size (typically 640 pixels for detection models, 224 pixels for classification models; processing time is 1 to 12 ms).  
3. **Inference:** AI model inference is performed (12 to 32 ms).  
4. **Post-processing:** Model output data is processed (bounding boxes thresholding, non-maximum suppression, object tracking with BoT-SORT; 0.5 to 1.5 ms).  
5. **Output & Visualization:** Processed data is output via TCP/IP port for real-time trackers, saved to a local file, and visualized (drawn over the recent video frame; under 0.5 ms).

Several execution threads (typically 2-3, maximum 5\) run parallel instances of the same processing pipeline. Every instance processes its own frame, utilizing one of the three available NPU (Neural Processing Unit) cores. This allows for high frame rate AI inference (90-120 fps) even though the total processing time per frame (16-48 ms) is longer than the frame interval (16.7-33.3 ms).

### **Inference Results**

* **Classification Models:** Inference results include the top 5 classes over the specified threshold.  
* **Detection Models:** Inference results include bounding boxes with the class ID and confidence level, object tracking boxes including object ID, class ID, object velocity in X and Y directions, and object lifetime.

### **Inputs and Outputs**

* **Video inputs:** HDMI and USB UVC (web) camera.  
* **Video output:** HDMI; augmented video: Input video stream with real-time AI-generated overlay.  
* **Data output:** JSON-formatted string for every input video frame over the LAN port.

### **Performance**

Performance metrics depend on the model. The metrics below are for the object detection model YOLO11s-RELU for 16:9 video input.

* **Single Video Input:** \* 1080p: 60 fps, data report latency: 19 ms;  
  * 2160p: 60 fps, data report latency: 28 ms.  
* **Dual Video Input:** \* 1080p or 2160p, 30 \+ 30 fps or 60 \+ 30 fps, 90 fps total max.  
  * Cameras can be activated simultaneously in Dual View, PIP, Split, or parallel recording mode, and each camera has differently trained models assigned.  
* **Power Consumption:** Around 2W at the maximum load of 90 fps (on top of the MVR/MTR device power consumption of 10-13W).

## **aiScope Evaluation**

aiScope can be evaluated free of charge. It comes preloaded with modern, state-of-the-art open-source vision AI models, trained on common datasets, like YOLO11s pre-trained on COCO (Common Objects in Context) with 80 classes.

Select a demo configuration for aiScope inference from the fixed presets, feed video footage over the HDMI input or live view from the USB camera, and Start Study. The selected AI model will be automatically loaded, and inference results (bounding boxes) will be drawn over the live video. It will take under 5 minutes to start with aiScope.

Simulate a surgical scenario using everyday objects, like a spoon and a fork. For evaluation, it is easier to use apples and bananas rather than polyps, hemorrhoids, or stool fragments. Record video overlay results and inference data results for analysis. Demo inference runs for 10 minutes with a watermark. Demo can run again after starting a new Study.

## **User Flow for Developing Custom Models**

When you are confident of getting the desired outcome while simulating various surgical scenarios, fine-tune the evaluated model on your custom dataset.

1. **Download & Fine-tune:** Download the pre-trained model, for example, YOLO11s-RELU, from the MediCapture GitHub in PyTorch format, and fine-tune it on your custom surgical dataset following the guidance published on the GitHub.  
2. **Convert & Upload:** Convert your new PyTorch model to the aiScope format using tools from the MediCapture GitHub repository. The model, relevant files, and settings will be saved as a zip archive. Upload it to the MTR device using a USB stick containing the archive file.  
3. **Deploy & Test:** Assign a new model to the video input, start Study, and evaluate the performance and inference results. With the right dataset and fine-tuning, the model will perform on surgical content with actual surgical instruments, yielding performance and results similar to those achieved during simulation using a common fork and knife.  
4. **Activation:** Demo inference is limited in time. Upon successful evaluation, purchase the aiScope activation key to remove the watermark and inference time limit.

## **Flexibility**

aiScope offers numerous documented adjustable parameters for inference, making it a robust tool for AI research.

* **General model selection and performance adjustments:** 9 parameters.  
* **Detection result post-processing:** 3 parameters.  
* **Multi-object tracking:** 9 parameters.  
* **Visualization:** 4 parameters.

## **FAQs (aiScope Device)**

### **Can we put our existing models into aiScope on the MTR device?**

Your existing models are developed to run on specific hardware, like NVIDIA or AMD platforms. It will not run optimally on aiScope even after being converted correctly.

The value is not in the pre-trained model you have, but in your dataset. If you have been able to train your own model, you have a training dataset.

**Correct workflow:** download the recommended aiScope-optimized model, fine-tune it on your custom dataset, convert, and deploy to the MTR device. This way, you can get a robust custom model running on MTR within 24 hours.

### **Can we use models other than YOLO?**

**Answer:** Yes. However, using suggested pre-tested models is faster and has predictable performance results. Using models of different architectures leaves many unanswered questions, like "Can my model be converted for the aiScope?", "Can my model run at 60 fps on the MVR/MTR device?", and many others.

The YOLO architecture is widely recognized for its efficiency and speed in object detection, making it suitable for applications demanding real-time video processing. Furthermore, YOLO is an open-source framework with robust support from Ultralytics, including options for commercial licensing, providing a flexible and sustainable development path.

### **Is it possible to use segmentation models?**

The use of the segmentation models is currently under development.

## **Regulatory Pathway**

The aiScope is a feature of the MVR/MTR video recorder, which is a Medical Class 1 device that complies with the EN 60601-1 standard and other relevant industry standards and regulations. Using aiScope for documentation purposes or assisting the physician does not alter the device classification. Deploy custom models that are not intended for diagnostic purposes or to replace clinical decision-making.

To deploy models beyond the intended outlined use, follow the established FDA process for approving AI models for clinical use.

* **GitHub repository:** [https://github.com/medicapture/aiScope\_YOLO\_to\_RKNN\_Pipeline](https://github.com/medicapture/aiScope_YOLO_to_RKNN_Pipeline)

# **aiScope YOLO to RKNN Conversion Pipeline**

An integrated pipeline for converting YOLO models (YOLOv8, YOLO11) to RKNN format for deployment on Rockchip NPU platforms, specifically designed for MediCapture aiScope \- an AI-powered feature for medical video recorders.

## **What is aiScope Pipeline?**

aiScope is a built-in AI inference feature for MediCapture MVR/MTR series medical video recorders that enables real-time object detection and image classification during surgical procedures. This pipeline provides the essential toolchain to convert your custom YOLO models into the RKNN format required by aiScope.

### **Features**

* **Fine-tuning Support:** Optional fine-tuning on custom datasets before conversion.  
* **Activation Replacement:** Automatically replaces SiLU/Swish activations with LeakyReLU for better RKNN compatibility.  
* **Pruned Model Support:** Handles structurally pruned modules (via torch-pruning).  
* **Pretrained Models:** Pre-optimized models trained on COCO dataset for quick testing.  
* **Multi-task Support:** Works with detection and classification models.  
* **Quantization:** Optional INT8 quantization for improved inference speed.  
* **Multiple Platforms:** Supports RK3562, RK3566, RK3568, RK3576, and RK3588.  
* **WSL2 Compatible:** Automatically detects and configures for WSL2 environments.  
* **aiScope Ready:** Output models are directly compatible with MediCapture aiScope devices.

### **Requirements**

#### **Recommended System:**

1. **OS:** Linux (or WSL2 on Windows)  
2. **Python:** 3.10  
3. **PyTorch:** 2.4.1 with CUDA 12.4 (for training/fine-tuning)  
4. **RKNN Toolkit2:** For ONNX to RKNN conversion  
5. **GPU:** CUDA-capable (optional, for fine-tuning)

#### **Target Deployment Platform:**

* MediCapture MTR133, MTR156, or MVR436 with firmware \>= 250901

## **Installation**

1. **Clone this repository:**  
   git clone \[https://github.com/medicapture/AiScope\_YOLO\_to\_RKNN\_Pipeline.git\](https://github.com/medicapture/AiScope\_YOLO\_to\_RKNN\_Pipeline.git)  
   cd AiScope\_YOLO\_to\_RKNN\_Pipeline

2. **Install PyTorch with CUDA (skip if already installed):**  
   conda install pytorch==2.4.1 torchvision==0.19.1 torchaudio==2.4.1 pytorch-cuda=12.4 \-c pytorch \-c nvidia

3. **Install remaining dependencies:**  
   pip install \-r requirements.txt  
   pip install rknn-toolkit2 \--no-deps

   *Note: The \--no-deps flag prevents pip from overriding your GPU-enabled PyTorch with a CPU-only version.*

## **Usage**

### **Basic Conversion (PT \-\> ONNX \-\> RKNN)**

Convert a pretrained YOLO model directly to RKNN format:

python aiscope\_pipeline.py \\  
    \--model pretrained\_models/yolo11s\_unpruned.pt \\  
    \--platform rk3588 \\  
    \--model-type i8

**Output files:**

* pretrained\_models/yolo11s\_unpruned.onnx \- Intermediate ONNX model  
* pretrained\_models/yolo11s\_unpruned\_i8.rknn \- Final RKNN model for aiScope

### **Fine-tuning \+ Conversion**

Fine-tune the model on your custom dataset before conversion:

python aiscope\_pipeline.py \\  
    \--model pretrained\_models/yolo11s\_unpruned.pt \\  
    \--fine-tune \\  
    \--platform rk3588 \\  
    \--model-type i8

**Prerequisites for fine-tuning:**

1. Prepare dataset in YOLO format.  
2. Create dataset config YAML in cfg/ (see cfg/coco128.yaml as an example).  
3. Update training parameters in ultralytics/cfg/default.yaml.  
   *Note: Before fine-tuning, update the data field in ultralytics/cfg/default.yaml to point to your dataset config.*

### **Custom Image Size**

Adjust input resolution based on your video aspect ratio:

**For 16:9 video:**

python aiscope\_pipeline.py \\  
    \--model pretrained\_models/yolo11s\_unpruned.pt \\  
    \--img-size 384 640 \\  
    \--platform rk3588 \\  
    \--model-type i8

**For square video (1:1 aspect ratio):**

python aiscope\_pipeline.py \\  
    \--model pretrained\_models/yolov8s\_unpruned.pt \\  
    \--img-size 640 \\  
    \--platform rk3588 \\  
    \--model-type i8

## **Pretrained Models**

All models are available in the pretrained\_models/ folder, pre-optimized for RKNN deployment:

### **Detection Models**

#### **YOLO11 (Latest)**

* yolo11s\_unpruned.pt \- Small, fast, COCO-80 pretrained  
* yolo11m\_unpruned.pt \- Medium, balanced performance  
* yolo11m\_pruned.pt \- Medium, structurally pruned for speed

#### **YOLOv8 (Stable)**

* yolov8s\_unpruned.pt \- Small, fast, legacy baseline  
* yolov8m\_unpruned.pt \- Medium, higher accuracy  
* yolov8m\_pruned.pt \- Medium, structurally pruned

### **Classification Models**

* yolo11m\_cls.pt \- ImageNet-1000 pretrained classifier

## **Pipeline Overview**

The conversion pipeline consists of three main stages:

### **1\. Optional Fine-tuning**

* Loads the base PyTorch model.  
* Replaces all activations with LeakyReLU (RKNN-compatible).  
* Detects if the model is pruned (C2f\_v2 modules).  
* Trains on custom dataset using Ultralytics API.  
* Saves best weights to runs/detect/{project\_name}/weights/best.pt.

### **2\. ONNX Export**

* Exports PyTorch model to ONNX format.  
* For classification models: automatically removes the Softmax layer.  
* Optimizes graph structure for RKNN conversion.  
* Outputs: {model\_name}.onnx.

### **3\. RKNN Conversion**

* Configures normalization (mean=\[0,0,0\], std=\[255,255,255\]).  
* Loads ONNX model.  
* Performs optional INT8 quantization using a calibration dataset.  
* Builds and exports RKNN model.  
* Outputs: {model\_name}\_{i8|fp}.rknn.

## **Dataset Preparation**

### **Training Dataset (for fine-tuning)**

Organize your dataset in YOLO format:

your\_dataset/  
├── images/  
│   ├── train/  
│   │   ├── img001.jpg  
│   │   ├── img002.jpg  
│   │   └── ...  
│   └── val/  
│       ├── img101.jpg  
│       └── ...  
└── labels/  
    ├── train/  
    │   ├── img001.txt  \# YOLO format: class\_id x\_center y\_center width height  
    │   ├── img002.txt  
    │   └── ...  
    └── val/  
        ├── img101.txt  
        └── ...

Create a dataset config file (e.g., cfg/my\_dataset.yaml):

path: /absolute/path/to/your\_dataset  
train: images/train  
val: images/val

names:  
  0: polyp  
  1: bleeding  
  2: normal\_tissue  
  \# ... add all your classes

Update ultralytics/cfg/default.yaml:

data: ./cfg/my\_dataset.yaml  
epochs: 100  
batch: 16  
imgsz: 640

### **Quantization Dataset (for INT8 conversion)**

For INT8 quantization, prepare 50-200 representative images from your dataset.

Example dataset.txt:

quantization\_dataset/000000000001.jpg  
quantization\_dataset/000000000016.jpg  
quantization\_dataset/000000000019.jpg  
...

*Important: Use images representative of your deployment scenario (lighting, angles, object sizes, etc.).*

## **Deployment to aiScope**

### **Step 1: Convert Your Model**

Use this pipeline to generate the .rknn file:

python aiscope\_pipeline.py \\  
    \--model pretrained\_models/yolo11s\_unpruned.pt \\  
    \--fine-tune \\  
    \--img-size 384 640 \\  
    \--platform rk3588 \\  
    \--model-type i8

### **Step 2: Package for aiScope**

After conversion completes, you will have:

* **Fine-tuned model:** runs/detect/pipeline\_test/weights/best\_i8.rknn  
* **Class names:** Defined in your dataset YAML.  
* **Quantization images:** Already used during conversion.

### **Step 3: Upload to MTR/MVR Device**

1. Copy the .rknn file to a USB flash drive.  
2. Prepare a configuration file with class names and parameters.  
3. Package as custom\_name.tar.gz (see aiScope documentation).  
4. Upload to your MediCapture device.  
5. Assign the model to a video input.

### **Step 4: Evaluate on aiScope**

#### **Free Evaluation Mode:**

* Test your model with 10-minute inference sessions.  
* A watermark will appear on output.  
* Verify inference accuracy with test objects.

#### **Production Mode:**

* Purchase an aiScope activation key to remove limitations.  
* Deploy for clinical use (following regulatory requirements).

#### **Performance Expectations:**

* Single 1080p input: 60 fps, \~19ms latency.  
* Single 2160p input: 60 fps, \~28ms latency.  
* Dual input: 30+30 fps or 60+30 fps (90 fps max total).

## **Advanced Configuration**

### **Training Hyperparameters**

Edit ultralytics/cfg/default.yaml to customize training behavior:

\# Training duration  
epochs: 100             \# More epochs for larger datasets  
patience: 50            \# Early stopping patience

\# Batch and image size  
batch: 16                \# Adjust based on GPU memory  
imgsz: 640               \# Match your deployment resolution

\# Folder name  
name: folder\_name        \# Select the name for the save folder

\# Learning rates  
lr0: 0.0002              \# Initial learning rate  
lrf: 0.4                 \# Final learning rate multiplier

\# Augmentation  
mosaic: 1.0              \# Mosaic augmentation probability  
mixup: 0.15              \# Mixup augmentation probability  
copy\_paste: 0.4          \# Copy-paste augmentation (for detection)

\# Loss weights  
box: 7.5                 \# Bounding box loss gain  
cls: 0.5                 \# Classification loss gain  
dfl: 1.5                 \# Distribution focal loss gain

### **RKNN Quantization**

The pipeline uses these default quantization settings (hardcoded in aiscope\_pipeline.py):

* mean\_values=\[\[0, 0, 0\]\] (No mean normalization)  
* std\_values=\[\[255, 255, 255\]\] (Scale pixels to \[0, 1\])

*These values are optimized for aiScope. Changing them may cause inference issues on the device.*

## **Regulatory and Clinical Use**

### **Important Disclaimer**

This pipeline and the pretrained models are provided for research and development purposes only.

For clinical deployment:

* aiScope is a feature of Medical Class 1 certified video recorders (EN 60601-1).  
* Using aiScope for documentation or physician assistance does not alter device classification.  
* Custom models should not be used for diagnostic purposes or to replace clinical decision-making.  
* For models intended for clinical diagnosis, follow the established FDA approval process for AI/ML medical devices.

*Consult with regulatory experts before deploying custom models in clinical settings.*

## **FAQ (Pipeline & Conversion)**

### **Can I use models other than YOLO?**

**Answer:** Technically yes, but not recommended. This pipeline is optimized for YOLO architectures (Ultralytics). Using other architectures (e.g., Faster R-CNN, EfficientDet) requires:

* Custom ONNX export logic  
* Unknown RKNN compatibility  
* Unpredictable performance on aiScope

YOLO is widely recognized for efficiency and speed in real-time video processing, making it ideal for medical applications.

### **Does this support segmentation models?**

**Answer:** Not currently. Segmentation support is under development for aiScope. This pipeline focuses on detection and classification models.

### **Can I run RKNN models on my PC for testing?**

**Answer:** No. RKNN models are specifically designed to run on Rockchip NPU hardware and cannot be executed on standard PC processors. Your PC can only perform the conversion process (PyTorch \-\> ONNX \-\> RKNN) using RKNN Toolkit2, but actual inference with .rknn files requires deployment on a physical device with a Rockchip NPU (RK3562, RK3566, RK3568, RK3576, or RK3588).

For testing and validation, use the PyTorch or ONNX versions of your model on PC before converting to RKNN format for final deployment.

### **How do I optimize model accuracy for medical images?**

**Answer:**

1. **Fine-tune with domain-specific data:** Use actual surgical/medical images, not general objects.  
2. **Augmentation:** Medical images have unique lighting and color properties.  
3. **Class balance:** Ensure representative samples of each condition.  
4. **Validation:** Test on held-out data from different patients/procedures.  
5. **Calibration:** Use diverse quantization images matching actual deployment conditions.