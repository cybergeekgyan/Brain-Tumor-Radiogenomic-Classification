# Brain-Tumor-Radiogenomic-Classification
Model to Predict the status of a genetic biomarker important for brain cancer treatment


- A malignant tumor in the brain is a life-threatening condition. Known as *glioblastoma*, it's both the most common form of brain cancer in adults and the one with the worst prognosis, with median survival being less than a year. The presence of a specific genetic sequence in the tumor known as *MGMT promoter methylation* has been shown to be a favorable prognostic factor and a strong predictor of responsiveness to chemotherapy.


- Currently, genetic analysis of cancer requires surgery to extract a tissue sample. Then it can take several weeks to determine the genetic characterization of the tumor. Depending upon the results and type of initial therapy chosen, a subsequent surgery may be necessary. If an accurate method to predict the genetics of the cancer through imaging (i.e., radiogenomics) alone could be developed, this would potentially minimize the number of surgeries and refine the type of therapy required.


- **The Radiological Society of North America (RSNA)** has teamed up with the **Medical Image Computing and Computer Assisted Intervention Society (the MICCAI Society)** to improve diagnosis and treatment planning for patients with *glioblastoma*. In this competition you will predict the genetic subtype of *glioblastoma using MRI (magnetic resonance imaging)* scans to train and test your model to detect for the presence of **MGMT promoter methylation**.


- If successful, It'll help brain cancer patients receive less invasive diagnoses and treatments. The introduction of new and customized treatment strategies before surgery has the potential to improve the management, survival, and prospects of patients with brain cancer.



## Brain-Tumor-Detector

Building a detection model using a convolutional neural network in Tensorflow & Keras.
Used a brain MRI images data founded on Kaggle. You can find it here.

About the data:
The dataset contains 2 folders: yes and no which contains 253 Brain MRI Images. The folder yes contains 155 Brain MRI Images that are tumorous and the folder no contains 98 Brain MRI Images that are non-tumorous.

Getting Started

Note: sometimes viewing IPython notebooks using GitHub viewer doesn't work as expected, so you can always view them using nbviewer.

Data Augmentation:

Why did I use data augmentation?

Since this is a small dataset, There wasn't enough examples to train the neural network. Also, data augmentation was useful in taclking the data imbalance issue in the data.

Further explanations are found in the Data Augmentation notebook.

Before data augmentation, the dataset consisted of:
155 positive and 98 negative examples, resulting in 253 example images.

After data augmentation, now the dataset consists of:
1085 positive and 980 examples, resulting in 2065 example images.

Note: these 2065 examples contains also the 253 original images. They are found in folder named 'augmented data'.

Data Preprocessing

For every image, the following preprocessing steps were applied:

Crop the part of the image that contains only the brain (which is the most important part of the image).
Resize the image to have a shape of (240, 240, 3)=(image_width, image_height, number of channels): because images in the dataset come in different sizes. So, all images should have the same shape to feed it as an input to the neural network.
Apply normalization: to scale pixel values to the range 0-1.
Data Split:

The data was split in the following way:

70% of the data for training.
15% of the data for validation.
15% of the data for testing.
Neural Network Architecture

This is the architecture that I've built:
