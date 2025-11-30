# 📁 Silent-Voice Dataset Summary
Dataset for real-time Indian Sign Language (ISL) gesture recognition using Arduino Nicla Vision + Edge Impulse.

---

## 📌 Overview
This dataset was created specifically for the **Silent-Voice: Sign Language Translator** project.  
It consists of **3,036 images** collected from **4 participants**, covering **15 Indian Sign Language (ISL)** gestures.  
Images were captured **directly on the Arduino Nicla Vision** using a custom OpenMV script.

All images were manually annotated using the **Edge Impulse Labeling UI** with bounding boxes around the active signing hand.

---

## 📌 Dataset Specifications

- **Total Images:** 3,036  
- **Number of Classes:** 15  
- **Average per Class:** ~200 images  
- **Image Resolution:** 240 × 240 pixels  
- **Color Space:** RGB (converted to Grayscale internally)  
- **Capture Hardware:** Arduino Nicla Vision  
- **Capture Method:** OpenMV script capturing frames every 200 ms  
- **Environment Variations:**  
  - Indoor lighting  
  - Outdoor lighting  
  - Mixed backgrounds  
  - Multiple hand shapes & skin tones  
- **Participants:** 4 individuals  

---

## 📌 Class List & Distribution

| Class   | Count |
|---------|-------|
| agree   | 201 |
| angry   | 203 |
| bad     | 202 |
| come    | 201 |
| fine    | 216 |
| go      | 201 |
| happy   | 201 |
| hello   | 201 |
| how     | 203 |
| hungry  | 202 |
| me      | 201 |
| please  | 202 |
| sorry   | 200 |
| thank   | 201 |
| you     | 201 |

**Total:** 3,036 images

---

## 📌 Collection Method

1. **OpenMV Script:**  
   A custom script running on the Nicla Vision captured frames in RGB565 format using:  
   ```python
   sensor.set_framesize(sensor.QVGA)
   sensor.set_windowing((240, 240))
    ```
### 📌 Capture Details
- **Capture Frequency:** 1 frame every 200 ms  
- **Variation:** Volunteers performed each gesture multiple times, varying:
  - Orientation  
  - Distance from camera  
  - Background  
  - Lighting conditions  

---

### 📌 Annotation Details
- Annotated manually in **Edge Impulse**  
- One bounding box per frame  
- Bounding box labels match the gesture class  
- Verified manually for correctness  
- Exported in Edge Impulse JSON format  

This enables the model to learn **localized gesture detection** rather than relying on full-frame classification.

---

### 📌 Preprocessing Pipeline (Inside Edge Impulse)
- Resize to **96×96**  
- Convert to **grayscale**  
- Normalize pixel values  
- Generate features via **Image** block  
- Train using **MobileNetV2 0.35** backbone  
- **Quantization:** INT8 optimized  

---

### 📌 Intended Use
This dataset is designed for:

- On-device gesture recognition  
- Edge AI models (MobileNet, FOMO, CNNs)  
- Real-time inference on low-power microcontrollers  
- ISL gesture classification research  
- Accessibility and assistive technologies  

---

### 📌 Ethical Considerations
- Dataset collected voluntarily from consenting participants  
- Contains only **hands performing gestures** — no faces  
- Safe for public release (if you choose to release it)  
- No sensitive or identifiable personal information stored  
