# 🧑‍⚖️ Face Mask Detection Using Deep Learning

This project aims to detect whether a person is wearing a face mask or not in images or real-time video streams. It utilizes **Convolutional Neural Networks (CNN)** and **MobileNetV2** (pretrained on ImageNet) for transfer learning to classify images into two categories: **with mask** and **without mask**.

The model leverages data augmentation techniques and a custom neural network head for classification. It's designed to work on both static images and live video from a webcam.

---

## 🚀 How It Works

1. **Data Collection**:  
   The dataset consists of images categorized into **"with_mask"** and **"without_mask"**. These images are preprocessed and augmented to improve model robustness.
   
2. **Data Preprocessing**:  
   - Images are resized to `(224, 224)` pixels to match MobileNetV2's input requirements.
   - Labels are one-hot encoded to convert string labels into numeric format (0 for `with_mask`, 1 for `without_mask`).

3. **Model**:  
   The project uses **MobileNetV2** as the base model with transfer learning. The model is then extended with custom layers for classification:
   - An **average pooling** layer reduces the feature map size.
   - A **dense layer** with ReLU activation for further learning.
   - A **dropout layer** for regularization.
   - A final **dense layer** with a **softmax** activation function to output two categories: **with mask** or **without mask**.

4. **Training**:  
   - The model is trained using an **Adam optimizer** with a learning rate of `0.0001` for 20 epochs.
   - Data augmentation is applied to the training data to improve generalization (includes rotation, zoom, shift, and horizontal flip).
   - The model is evaluated using **binary cross-entropy loss** and **accuracy** as the evaluation metric.

5. **Prediction**:  
   After training, the model can predict if a person in an image or video is wearing a mask or not.

---

## 📂 Dataset Setup:

- The dataset should be organized into two folders:
  - `with_mask`: Place images of people wearing masks in this folder.
  - `without_mask`: Place images of people not wearing masks in this folder.
---

## 🔮 Future Enhancements:

- **Real-time Detection Optimization**:  
  Improve the speed and accuracy of live webcam detection by applying techniques like **TensorRT** or **OpenVINO**.

- **Support for More Masks**:  
  Expand the model to detect different types of masks, such as **surgical masks**, **cloth masks**, etc.

- **Web Interface**:  
  Build a web app using **Flask** or **Streamlit** for users to upload images or video for mask detection.
