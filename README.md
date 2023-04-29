# Inspiration

The RSNA (Radiological Society of North America) Bone Age Competition was a machine learning competition hosted by the RSNA Pediatric Bone Age Machine Learning Challenge in 2017. The goal of the competition was to develop algorithms that could accurately predict the bone age of pediatric patients based on X-ray images of their hands.

Bone age is an important indicator of a child's growth and development, and is typically assessed by comparing X-ray images of the child's hand with a standard atlas of bone development. However, this process can be time-consuming and subjective, leading to variability in results.

The competition provided a dataset of hand X-ray images and corresponding bone age assessments from a diverse population of children. The participants were tasked with developing machine learning algorithms that could accurately predict bone age based on the X-ray images.

The competition attracted a large number of participants, including academic and industry teams from around the world. The top-performing algorithms demonstrated high accuracy in predicting bone age, with some exceeding the performance of expert radiologists.

The RSNA Bone Age Competition highlighted the potential of machine learning algorithms to improve medical imaging and diagnosis, and demonstrated the value of collaborative efforts between academic and industry partners in advancing the field.

## Results of the competition

This is the results of other teams on the same dataset. Our primary objective was to to create 
model that meets the standards of the above mentioned models and takes less computational resources while training and prediction.


| Experiment  | Chest training size | Epochs | MAE |  Date |
| ------------- | ------------- | ------------- | ------------- |  ------------- |
| 16Bit challenge winner								| n/a	| 500	| 4.265	| 2017  |
| Radiologist	performance							| n/a	| n/a	| 7.32	| 2017  |
| Imagenet								| n/a	| 50	| 76.8	| 181020  |
| Imagenet								| n/a	| 250	| **8.8**	| 181029  |
| No TL, random init.					| n/a	| 250	| **10.8**	| 181030  |
| Chest 0-20yrs., 30 layers finetuning	| 1560	| 50	| 33.9	| 181022  |
| Chest 0-20yrs., 100 layers finetuning	| 1560	| 50	| 37	| 181022  |
| Chest 0-20yrs., 100 layers finetuning	| 1560	| 250	| 41.8	| 181024  |
| Chest 0-20yrs., 50 layers finetuning	| 1560	| 250	| 34.5	| 181025  |
| Chest 0-20yrs., 20 layers finetuning	| 1560	| 250	| 36.7	| 181026  |
| Chest 0-20yrs., 30 layers finetuning	| 1560	| 250	| 35.8	| 181027  |
| Chest 0-100yrs, 3 layers finetuning	| 89696	| 250	| 34.8	| 181103 |
| Chest 0-100yrs, all layers finetuning	| 89696	| 250	| pending*	| pending* |

## Objectives

Our main objective was to create a model which will take less computation while training and will have a high accuracy in bone age and gender estimation.

# Semantic Segmentation

Semantic segmentation is a computer vision task that involves assigning a label to every pixel in an image. The goal is to classify each pixel into a predefined set of categories or classes. 

Semantic segmentation is widely used in many applications, such as self-driving cars, medical imaging, and robotics. It is a challenging task that requires a high degree of accuracy and efficiency.

## How it Works

Semantic segmentation uses deep neural networks to perform pixel-level classification. The input to the network is an image, and the output is a pixel-wise classification map. The network is trained on a large dataset of labeled images to learn the mapping from input images to output segmentation maps.

The most common architecture for semantic segmentation is the Fully Convolutional Network (FCN). FCN is a deep neural network that consists of convolutional layers and upsampling layers. The convolutional layers extract features from the input image, and the upsampling layers restore the resolution of the output segmentation map.

## Evaluation Metrics

To evaluate the performance of a semantic segmentation model, several metrics are used, including accuracy, precision, recall, and F1 score. 

- **Accuracy**: the percentage of correctly classified pixels over the total number of pixels.
- **Precision**: the ratio of true positives to the total number of predicted positives.
- **Recall**: the ratio of true positives to the total number of actual positives.
- **F1 score**: the harmonic mean of precision and recall.

## Applications

Semantic segmentation has a wide range of applications, including:

- **Self-driving cars**: semantic segmentation is used to identify different objects in the environment, such as pedestrians, cars, and traffic signs.
- **Medical imaging**: semantic segmentation is used to identify different organs and tissues in medical images, which can aid in diagnosis and treatment.
- **Robotics**: semantic segmentation is used to identify different objects in a robot's environment, which can help it navigate and interact with its surroundings.

## Usage in this Project

In this project, We  manually labeled **30 images** and created its coresponding masks. With data augmentation techniques, we managed to increase the size of data set to **90 images**

**After that we trained the model and obtained an accuracy of 99%. Thus, creating a model which is capable of removing noise from the image. Its effect helped us to create a classfication model which achieved a high accruracy with less computation**

## Conclusion

Semantic segmentation is a powerful computer vision technique that can be used in many applications. It involves assigning a label to every pixel in an image and requires a deep neural network trained on a large dataset of labeled images. With the increasing availability of labeled datasets and the growing power of deep learning techniques, semantic segmentation is becoming more accurate and efficient, making it a valuable tool in many domains.

# Classfication

In classfication and regression, we have use the concept of transfer learning and fine tunning to achieve our project objectives.

Base Model - **EfficientNetB4**

EfficientNetB4 is a convolutional neural network (CNN) architecture that was introduced in a 2019 paper by Mingxing Tan and Quoc V. Le. It is part of a family of EfficientNets, which were designed to achieve state-of-the-art accuracy on image classification tasks with a smaller number of parameters and lower computational cost compared to previous models.

EfficientNetB4 has 19 million parameters and achieves high accuracy on standard image classification benchmarks such as ImageNet. It is based on a compound scaling method that balances the depth, width, and resolution of the network to achieve optimal performance.

The architecture of EfficientNetB4 consists of a series of convolutional layers with batch normalization, followed by global average pooling and a fully connected layer for classification. It also includes a set of efficient block modules that use a combination of depthwise separable convolutions, which reduce the number of parameters and computation required.

EfficientNetB4 has been shown to achieve state-of-the-art performance on a range of computer vision tasks, including image classification, object detection, and semantic segmentation. It has also been used in transfer learning applications, where pre-trained weights from the model are fine-tuned for specific tasks with limited labeled data.

Overall, EfficientNetB4 is a powerful and efficient deep learning architecture that has demonstrated impressive performance on a range of computer vision tasks while reducing the computational cost and memory requirements compared to previous models.

## Results:-

We used only 10 epochs to train the model with 7062 images. It took us only 2 hrs to complete this process. A great improvement compared to work done by other developers. Due to resource constraint, we couldn't able to achieve extreme high accuracy. 

### Regression Results:-

Valdation Accuracy - 11 months MAE
Test Accuracy - 11 months MAE
Train Accuracy - 9 months MAE

### Classification Matrix

![Classificaion Matrix](https://raw.githubusercontent.com/Anirban20001962/rsan-bone-age/main/confusion_matrix.png)

### Classification Report

![Classfication Report](https://raw.githubusercontent.com/Anirban20001962/rsan-bone-age/main/classification_report.png)



## Post Studies

There are many potential research directions related to bone age assessment beyond prediction or estimation using machine learning algorithms.:

* Analysis of inter-observer variability: One area of research could focus on analyzing the variability in bone age assessments made by different radiologists or clinicians. This could involve studying the factors that contribute to variability, such as differences in training or experience, or the use of different atlases or reference standards. Understanding the sources of variability could help improve the accuracy and consistency of bone age assessments.

* Development of new atlases or reference standards: Another area of research could involve the development of new reference standards or atlases for bone age assessment. Existing atlases are often based on limited populations and may not accurately represent the diversity of pediatric patients. Developing new reference standards could improve the accuracy and reliability of bone age assessments, particularly for underrepresented populations.

* Validation of bone age assessment in clinical outcomes: Bone age assessment is often used as a proxy for assessing growth and development in pediatric patients. However, there is limited evidence linking bone age assessments to clinical outcomes such as height, weight, or pubertal development. Research could focus on establishing these links and determining the clinical utility of bone age assessment in predicting long-term outcomes.

* Assessment of radiation exposure: X-ray imaging is commonly used for bone age assessment, but it also exposes pediatric patients to ionizing radiation. Research could investigate the potential risks associated with radiation exposure from bone age assessments and explore alternative imaging techniques or protocols that minimize radiation exposure.

