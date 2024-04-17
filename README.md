# Project Name
> Outline a brief description of our project.


## Table of Contents
* [General Info](#general-information)
* [Project Pipeline](#Project-Pipeline)
* [Conclusions](#conclusions)
* [Contact](#contact)

<!-- we can include any other section that is pertinent to our problem -->

## General Information
- We are about to build a CNN based model which can accurately detect melanoma. Melanoma is a type of cancer that can be deadly if not detected early. It accounts for 75% of skin cancer deaths. A solution that can evaluate images and alert dermatologists about the presence of melanoma has the potential to reduce a lot of manual effort needed in diagnosis.
The dataset consists of 2357 images of malignant and benign oncological diseases, which were formed from the International Skin Imaging Collaboration (ISIC). All images were sorted according to the classification taken with ISIC, and all subsets were divided into the same number of images, with the exception of melanomas and moles, whose images are slightly dominant.
- The data set contains the following diseases:
    + Actinic keratosis
    + Basal cell carcinoma
    + Dermatofibroma
    + Melanoma
    + Nevus
    + Pigmented benign keratosis
    + Seborrheic keratosis
    + Squamous cell carcinoma
    + Vascular lesion

<!-- we don't have to answer all the questions - just the ones relevant to our project. -->
## Project Pipeline
- Data Reading/Data Understanding → Defining the path for train and test images 
- Dataset Creation→ Create train & validation dataset from the train directory with a batch size of 32. Also, make sure we resize our images to 180*180.
- Dataset visualisation → Create a code to visualize one instance of all the nine classes present in the dataset 
- Model Building & training : 
    + Create a CNN model, which can accurately detect 9 classes present in the dataset. While building the model, rescale images to normalize pixel values between (0,1).
    + Choose an appropriate optimiser and loss function for model training
    + Train the model for ~20 epochs
    + Write our findings after the model fit. we must check if there is any evidence of model overfit or underfit.
- Chose an appropriate data augmentation strategy to resolve underfitting/overfitting 
- Model Building & training on the augmented data :
    + Create a CNN model, which can accurately detect 9 classes present in the dataset. While building the model rescale images to normalize pixel values between (0,1).
    + Choose an appropriate optimiser and loss function for model training
    Train the model for ~20 epochs
    + Write our findings after the model fit, see if the earlier issue is resolved or not?
- Class distribution: Examine the current class distribution in the training dataset 
    + Which class has the least number of samples?
    + Which classes dominate the data in terms of the proportionate number of samples?
- Handling class imbalances: Rectify class imbalances present in the training dataset with Augmentor library.
- Model Building & training on the rectified class imbalance data :
    + Create a CNN model, which can accurately detect 9 classes present in the dataset. While building the model, rescale images to normalize pixel values between (0,1).
    + Choose an appropriate optimiser and loss function for model training
    + Train the model for ~30 epochs
    + Write our findings after the model fit, see if the issues are resolved or not?

## Conclusions
### <u> Overall <u>
- We have experimented many possible ways to develop and improve the model's performance for this project.  Most of them has failed on overfitting and underfitting problems. 
- And fortunately, the model2_enhanced with experiments of changing the architecture by reducing kernel_size from 3 to 2, adding more filters & FC neurons quantity, adding more Conv2D layers and dropout at Dense layer, we have resulted it with highest 81% training,  67% validation and 45% test accuracy performance. It has showed that we are going on the right direction, if we cannot improve much from other hyperparameters (number of augmented images generrated), we can modify the network architectures by reducing kernel_size from 3 to 2, adding more filters & FC neurons quantity, adding more Conv2D layers and dropout at Dense layer to improve the model performance. From this, we can fine tune the model2_enhanced in more possible ways for improvement in near future!

### <u> Findings on the 1st experimental model1 </u>:
The 1st experimental model1 - Image augmentation (Transformed1), after 5th epoch, while the training accuracy is still increasing (training loss is still decreasing), the validation accuracy is not improved (validation loss is turning from descreasing to increasing); moreover testing accruracy (on test dataset) is quite low at 0.36 (36%). This is the evidence of model's overfitting. Hence we need to tackle this in next steps. However, in overall, this 1st experiment model1 resulted a better testing accuracy than the previous model run ( 36% > 30% previously)

### <u> Findings on the 2nd experimental model2 </u>:
The 2nd experimental model2 - Image Augmented with the Augmentor lib (generate & add 500 images more to each class), after 10th epoch, while the training accuracy is still increasing (training loss is still decreasing), the validation accuracy is not improved (validation loss is turning from descreasing to increasing); moreover testing accruracy (on test dataset) is quite low at 0.34 (34%). This is the evidence of model's overfitting. Hence we need to tackle this in next steps. However, in overall, this 2nd experiment model2 resulted a worse testing accuracy than the previous model1 run ( 34% <>> 36% previously). Seems that, if we add more augmented images to both training and validation dataset, the model trends to more overfitting !

### <u> Findings on the model2_enhanced </u>:
The experimental model2_enhanced (changing the architecture by reducing kernel_size from 3 to 2, adding more filters & FC neurons quantity, adding more Conv2D layers and dropout at Dense layer) , after 15th epoch, the model starts overfitting, while the training accuracy is still increasing (training loss is still decreasing), the validation accuracy is not improved (validation loss is turning from descreasing to increasing); the testing accruracy (on test dataset) is highest so far at 0.45 (45%) but still not as high as expected (more than 70%). This is the evidence of model's overfitting. Hence we need to improve this in next steps.
In overall, this experimental model2_enhanced resulted the best testing accuracy so far at 45% test , 67% validation and 81% training accuracy. IT has showed that, if we cannot improve much from other hyperparameters (number of augmented images generrated), we can modify the network architectures by reducing kernel_size from 3 to 2, adding more filters & FC neurons quantity, adding more Conv2D layers and dropout at Dense layer to improve the model performance

### <u> Findings on model2b_enhanced </u>:
The experimental model2_enhanced2 (changing the architecture by adding more filters & FC neurons quantity, adding more Conv2D layers and dropout at Dense layer) is running on Google Colab, we have tried to add 3 more Conv2D layers into the previous model2_enhanced, but it shows an error and we are not able to add more leyers for experimenting on this way. Let's explore another

### <u> Findings on model3 </u>:
The experimental model3 (more images augmentation to ensure all 9 classes have same class-distribution of 1500 images/class), We have add all remained quantity of images to ensure 1500 images/class for classes-balancing. However, the overall model's performance is very poor, they are underfitting at 10-12% training & validation accuracy, 13.5% testing accuracy. Hence, we would not explore more on this adding more images augmentation!
<!-- we don't have to answer all the questions - just the ones relevant to our project. -->

## Contact
Created by [nguyenhoangthangbt@gmail.com] - feel free to contact me!
