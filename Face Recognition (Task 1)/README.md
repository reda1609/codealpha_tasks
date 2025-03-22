# Face Recognition System


## Overview

We developed a **Face Recognition System** using a deep learning approach that fine-tunes **ResNet-18** as a **Siamese Network**. This system is designed to recognize faces by comparing embeddings generated from facial images. The implementation involves training the model with **Triplet Loss**, generating a **database of face embeddings**, and using **MTCNN** for face detection and cropping.


## Model Training

### Fine-Tuning ResNet-18 as a Siamese Network

* We used **ResNet-18** as the backbone and modified it to work as a **Siamese Network**.

* The network was trained using Triplet Loss, ensuring that:

    * Embeddings of the **same person** are closer together.

    * Embeddings of **different people** are pushed further apart.

* The model was optimized for generating **robust face embeddings**.


### Dataset Preparation

* We used **two different datasets** and customized them for our needs.

* Data preprocessing steps included:

    * Preparing images in the form of triplets to facilitate training with Triplet Loss.

    * Augmenting data for improved generalization.

    * Splitting the dataset into training and validation sets.


## Face Recognition Pipeline

### Generating Face Embeddings

* After training, we used the model to **extract embeddings** for known individuals.

* The database consists of face embeddings extracted from actual facial images, associating each embedding with the corresponding person's name.

### Detecting Faces in New Images

* We integrated **MTCNN** (Multi-task Cascaded Convolutional Networks) as the face detection model.

* MTCNN was responsible for:

    * Locating faces in images.

    * Cropping and aligning detected faces before passing them to the recognition model.

### Face Matching & Recognition

* When a **new image** is processed:

    * MTCNN detects and crops faces.

    * The **ResNet-18 Siamese Network** extracts an embedding for the detected face.

    * The embedding is **compared** with stored embeddings using **pairwise distance**.

    * The closest match (if within a threshold) determines the recognized person.

* If no close match is found, the person is labeled as **Unknown**.


## Results & Visualization

* We processed multiple test images through the system.

* The results were **annotated** by drawing bounding boxes and names on detected faces.

* Images were displayed using **Matplotlib**, showcasing the model’s recognition performance.


## Summary

We successfully built a **deep learning-based face recognition system** by:
* ✅ Fine-tuning ResNet-18 as a Siamese Network with **Triplet Loss**.
* ✅ Using **MTCNN** for face detection and cropping.
* ✅ Creating a **database of embeddings** for face matching.
* ✅ Implementing a **pipeline** for real-time face recognition.
* ✅ Displaying and analyzing recognition results visually.

This system demonstrates a robust approach to facial recognition, combining powerful deep learning techniques with an efficient pipeline for real-world applications. 🚀