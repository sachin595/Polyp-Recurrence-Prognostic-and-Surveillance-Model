# Polyp-Recurrence-Prognostic-and-Surveillance-Model
Multimodal AI Framework for Predicting Polyp Recurrence and Tailored Surveillance Recommendations

[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)
![Research Medical AI](https://img.shields.io/badge/Research-Medical%20AI-green.svg)
![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)
![TensorFlow](https://img.shields.io/badge/Framework-TensorFlow-orange.svg)
![PyTorch](https://img.shields.io/badge/Framework-PyTorch-red.svg)
[![Dataset: ERCPMP-v5](https://img.shields.io/badge/Dataset-ERCPMP--v5-brightgreen.svg)](https://data.mendeley.com/datasets/7grhw5tv7n/6/files/72cc0287-84ad-4ade-ae74-8e1e8b30c0a4)

---

## **Table of Contents**
1. [Dataset Description](#dataset-description)
2. [Dataset Preprocessing](#dataset-preprocessing)
3. [Workflow Diagram](#workflow-diagram)
4. [Implementation Approach](#implementation-approach)
   - [Multimodal AI Framework](#multimodal-ai-framework)
   - [Fusion Model](#fusion-model)
5. [Project Objective](#project-objective)
6. [Model Outputs](#model-outputs)
7. [Analysis of Metrics](#analysis-of-metrics)
8. [Key Observations](#key-observations)
9. [Conclusion](#conclusion)
10. [License](#license)

---

## **Dataset Description**
The ERCPMP-v5 dataset contains detailed endoscopic images, videos, and patient data focused on the morphology and pathology of colorectal polyps. Key details:

- **Patients**: Data from 217 patients.
- **Images & Videos**: 430+ anonymized images and videos.
- **Demographic Data**: Includes patient demographics.
- **Morphological Data**: Classifications based on Paris, Pit, and JNET Classification systems.
- **Pathological Data**: Includes diagnoses like Tubular, Villous, Tubulovillous, Hyperplastic, and more.

### Contributors
Prepared by experts in Gastroenterology, Hematology, Oncology, and Artificial Intelligence.

---

## **Dataset Preprocessing**
1. **Metadata Preprocessing**: Patinet_ID is the Unique identifier for each patient with morphological and pathological details.
    - Scaled numerical features (e.g., age, polyp size).
    - One-hot encoded categorical features (e.g., dysplasia grade, morphology classification).
2. **Image and Video PreProcessing**: Images and videos are processed to ensure that they are correctly associated with the corresponding Patient_ID.Frames extracted at 2 FPS, resized to 224x224 pixels, and normalized to [0, 1].
3. **Data Merging**: Using Patient_ID as a key, image paths are merged with the metadata. This links each image/frame with the corresponding demographic, morphological, and pathological details.
4. **Splitting the Dataset**:
   - Training Set (60%)
   - Validation Set (20%)
   - Test Set (20%)
5. **Final Dataset Creation**: The final dataset includes:
- Metadata: Patient and polyp-specific information (size, morphology, diagnosis, etc.).
- Image Paths: Linking images/frames to patient metadata.
- Split Information: Indicates whether an entry belongs to training, validation, or test sets.


## **Workflow Diagram**
![Workflow Diagram](workflow.png)

---

## **Implementation Approach**
### **Multimodal AI Framework**
The Multimodal AI refers to an approach that combines and processes multiple types of data (here text metadata and image data) together to make predictions or provide insights. In this project, Multimodal AI is used to combine:
1. Metadata: Information about the patient (like age, sex) and polyp characteristics (like size, location, and dysplasia grade).
2. Image Features: Detailed information extracted from colonoscopy images or video frames.

By integrating these two types of data, the system creates a more comprehensive understanding of the patient's condition, which helps make better predictions about polyp recurrence and provides tailored surveillance recommendations.


### **Fusion Model**
Fusion Model:
A Fusion Model is a deep learning approach that combines information from multiple sources (or modalities) to make predictions. In this project, it combines:
1. Metadata Features: Information like patient demographics (e.g., age, sex) and polyp characteristics (e.g., size, location, dysplasia grade).
2. Image Features: Detailed visual information extracted from colonoscopy frames using a pre-trained model like Vision Transformer (ViT).

Why Use a Fusion Model?
Multimodal Learning: A fusion model integrates multiple or diverse data types, combining metadata for contextual information (e.g., patient history) with images that capture detailed visual characteristics of polyps. In simple terms, a Fusion Model is like combining two experts—one analyzing patient details and the other examining polyp images—to make the best possible prediction about recurrence risk and follow-up care.


---

## **Project Objective**
Develop an AI model to:
- Predict polyp recurrence post-polypectomy.
- Recommend tailored surveillance intervals.
- Assist clinicians in optimizing patient outcomes and resource allocation.

---

## **Model Outputs**
### **Primary Outputs**
1. **Binary Prediction**: Likely to recur or not likely to recur.
2. **Confidence Score**: Probability indicating prediction certainty.

### **Secondary Outputs**
1. **Risk Categories**:
   - Low Risk: Probability < 30%.
   - Moderate Risk: Probability 30–70%.
   - High Risk: Probability > 70%.
2. **Tailored Surveillance Recommendations**:
   - Low Risk: Follow-up in 1–3 years.
   - Moderate Risk: Follow-up in 6–12 months.
   - High Risk: Follow-up in 3–6 months.

---

## **Analysis of Metrics**
- **Test Loss**: 0.0013 (high accuracy, minimal error).
- **Test Accuracy**: 99.89% (state-of-the-art performance).

---

## **Key Observations**
### **Violin Plot Analysis**
1. **Larger Polyp Sizes and Recurrence**:
   - Yes Recurrence shows higher median size and variability.
2. **Non-Recurrent Polyps**:
   - Smaller sizes with tightly packed distributions.
3. **Distinct Categories**:
   - Clear separation between No and Yes categories.
4. **Outliers**:
   - Larger polyps (>5 cm) in Yes Recurrence group.

![Violin Plot](violin_plot.png)

---

## **Conclusion**
The AI-Enhanced Prognostic Model leverages multimodal data for actionable post-polypectomy care. By reducing unnecessary procedures and facilitating early detection, the model improves patient outcomes while optimizing healthcare resources.

---

## **License**
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)

This project is licensed under the Attribution 4.0 International (CC BY 4.0). For more details, visit the [Creative Commons License](https://creativecommons.org/licenses/by/4.0/).

---

Let me know if you need further refinements or additional sections.
