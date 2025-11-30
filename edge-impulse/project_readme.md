# Silent-Voice: Sign Language Translator

This Edge Impulse project implements a **real-time, on-device Indian Sign Language (ISL) recognition system** using the **Arduino Nicla Vision**.  
The model performs gesture detection and labeling directly on-device and streams the results via Wi-Fi to any smartphone browser.

---

## 📌 Project Overview
Silent-Voice is a portable sign-language translator designed for accessibility.  
It captures live video, performs ML inference on the Nicla Vision microcontroller, overlays gesture labels, and streams the annotated feed through an MJPEG server.

---

## 📌 Dataset
- **Total images:** 3,036  
- **Classes:** 15 ISL gestures  
- **Images per class:** ~200  
- **Collection method:** Arduino Nicla Vision (OpenMV script)  
- **Annotation:** Manual bounding boxes using Edge Impulse Labeling UI  
- **Participants:** 4 users  

**Classes:**  
`agree, angry, bad, come, fine, go, happy, hello, how, hungry, me, please, sorry, thank, you`

---

## 📌 Model Information
- **Model Type:** MobileNetV2 0.35  
- **Input Size:** 96×96  
- **Color Mode:** Grayscale  
- **Quantization:** INT8  
- **Validation Accuracy:** 93.1%  
- **Test Accuracy:** 90.17%  
- **Precision:** 0.96  
- **Recall:** 0.90  
- **F1 Score:** 0.93  
- **Inference Time:** 691 ms  
- **Peak RAM:** 137.8 KB  
- **Flash Usage:** 81.9 KB  

---

## 📌 Functionality
- Real-time gesture detection  
- Bounding box + gesture label overlay  
- MJPEG video streaming over Wi-Fi  
- Optional display-connected mode for on-device visualization  

---

## 📌 Deployment Workflow
1. Train model in Edge Impulse  
2. Export as **OpenMV Library**  
3. Upload `trained.tflite`, `labels.txt`, and script to Nicla Vision  
4. Connect to Wi-Fi hotspot  
5. Access live stream from phone browser  
6. View real-time gesture predictions  

---