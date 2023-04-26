<img src="http://imgur.com/1ZcRyrc.png" style="float: left; margin: 20px; height: 55px">

# Capstone: Classifying Artefacts in the National Collection

---
### Overview

Background
- Cataloguing artefacts involves systematically documenting information about cultural, historical, or scientific objects. It includes creating a comprehensive inventory, organizing objects, and providing detailed descriptions and metadata. Proper cataloguing enables efficient management, preservation, and access to collections, supporting research and promoting access to cultural heritage.

- The cataloguing process can involve both manual and automated elements, depending on the institution and the scale of the collection. Traditionally, cataloguing was primarily a manual process that involved physically documenting information about each artefact on paper records or index cards. However, with the advancement of technology, many institutions now utilize specialized cataloguing databases to create and manage digital records for their collections.

In this project, we will develop an image classification model predicting selected labels for the metadata of an artefact that the cataloguer would have to tag.
- `Multi-class Image Classification`: Predicting labels for five (5) classes of images/artefacts according to their categories.
- `Multi-label Image Classification`: Predicting a set of labels corresponding to the object and attribute present in an image. 


---
### Problem Statement

To develop an image classification system that accurately predicts tags for artefacts captured in the photographs, for more efficient cataloguing of Singapore’s national treasures. Success will be measured by the accuracy of the model in classifying the artefact.  

---
### Success Metric
Accuracy is a commonly used metric for evaluating the performance of an image classification system, measuring the proportion of correctly classified images compared to the total number of images. 

Accuracy will be used as the success metric for this project as it is easy to interpret and the target class is well balanced. A wrong classification of the image would have limited impact as the complete cataloguing process would involve detailed verification checks (e.g. via research on the objects..).

---
### Datasets

Images from online collections of various local and international museums were used.

- `Multi-class Image Classification`: Close to 6,000 images belonging to five classes - (i)bowl; (ii)painting; (iii)plate; (iv)sculpture; (v)vase. This dataset can be accessed via the following link on Google Drive: [link](https://drive.google.com/drive/folders/19nFMRS24TDRO05ujRmcD_QKuJ04pUUVH?usp=share_link)
- `Multi-label Image Classification`: Close to 4,200 images belonging to two classes with two subcategories - (a) Type: (ai)Dress;(aii)Watercolor; (b) Period: (bi) 18th century; (bii) Present.  This dataset can be accessed via the following link on Google Drive: [link](https://drive.google.com/drive/folders/1E9pG2RkVAbm_J_A2QDtuxBu6gnv0mnjn?usp=share_link)


---
### Submissions

The following technical reports are included:
- `Model 1(Baseline)`: This includes loading & pre-processing the images; developing, training & evaluating the model for classifying the five image classes
- `Multi-class Image Classification Model`: This includes loading & pre-processing the images; developing, training & evaluating the model for classifying the five image classes using transfer learning (MobileNet-v2)
- `Multi-label Image Classification Model`: This includes loading & pre-processing the images; developing, training & evaluating the model for classifying the images using transfer learning (VGG16)
- `Model1.h5`,`Model2.h5`,`model1_multilabel`,`model2_multilabel2`: Saved copy of model's architecture 
- `Multiclass_WebApp`, `ngrok.yml`: Application to run the model

---
### Modelling
Summary of results

|Model|Type|Train Accuracy|Validation Accuracy|Test Accuracy|
|---|---|---|---|---|
|Model 1 (Baseline)| 3 Layers of Convolution & MaxPooling| 0.95| 0.56|0.59|
|Model 2 Multi-class| MobileNet-v2| 0.85| 0.82|0.82|
|Model 3 Multi-label| VGG16| period: 0.66 type: 0.99|period: 0.71 type: 1.00|period: 0.71 type: 1.0|

---
### Conclusion and Recommendations

Limitations:
- Limited dataset
- Lack of interpretability
- Complex systems in archaeology and cultural complexity

Conclusion:
1) Results for the image classification system are promising.
- 81% accuracy in predicting tags for the various artefacts (classes) for the multi-class system
- High level of accuracy for both ‘period’ and ‘type’ outputs for the multi-label system

2) Further improvements and finetuning could be explored to optimize the model's performance

3) Results highlight the potential of using image classification models for cataloguing for artefacts for museums locally and internationally.

--- 
