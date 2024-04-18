I. Introduction
   
In this Kaggle contest "Pawpularity," we had the opportunity to participate in a fascinating challenge that involved predicting the cuteness of stray dogs or cats. The underlying motivation behind this contest was to find improved ways of understanding and assessing these adorable animals. By leveraging advanced data analysis and machine learning techniques, we aimed to identify the factors that contribute to their appeal and likability. Ultimately, the goal was to provide valuable insights that could lead to better adaptations and accommodations for these precious creatures, ultimately improving their well-being and chances of finding loving homes. Furthermore, In this competition, participants are provided with a substantial dataset comprising images of domestic animals for training and testing purposes. Each image is accompanied by a set of metadata containing diverse features, including the crucial Pawpularity score, which is available only in the training set. While various machine learning approaches can be employed to model the dataset, we focus on the usage of the Swin-transformer, which had shown great performance in image analysis and align with our initial intuition for tackling this task.

II. Our Method
1. General techniques

In this competition, we put forward three approaches. Our initial method serves as a prototype, while the second and third methods represent our enhanced versions. Throughout the task, we conducted tests using "Swin-Transformer" and observed its remarkable efficacy in this competition. As a result, we extensively explored the advantages of the Swin-transformer in the second and third methods, leading to improved outcomes. We will delve into the specifics of our implementation in the subsequent sections:

   (1) Data preprocessing

Fastai, a popular deep learning library, offers powerful data augmentation techniques. Among these techniques, we used brightness, contrast, hue, and saturation adjustments in this competition. With scales set at 0.2, these augmentations introduce controlled variations to the input images. They modify the image's intensity, color range, sharpness, tone, and vibrancy, enhancing the creation of diverse training data for improved model generalization and robustness.



   (2) Metadata insights

Although the competition page mentions that the metadata are not used for deriving the pawpularity score, we discover some people using regression models with ensemble learning can get better prediction performance. So we calculate the correlation matrix between all the metadata attributes and the pawpularity score, representing it as the heatmap as shown in Figure 1. The correlation between the pawpularity score and all the metadata attributes is very low. It makes sense as mentioned previously. However, it may exist some nonlinear correlations, so we decided to use some kind of regression model to test the performance.


   (3) Training process - Stratified K-fold validation

K-fold validation is a popular technique for evaluating machine learning models. It involves partitioning the dataset into K equal-sized subsets and performing training and testing K times, each time using a different subset as the validation set. This helps assess the model's performance and mitigate issues like overfitting.

   (4) Ensembling process - Optuna

Optuna Ensemble is a framework that automates ensemble construction and selection. It utilizes Optuna for efficient exploration of ensemble configurations, optimizing weights to improve model performance. This tool simplifies the process of creating effective ensembles and enhancing overall model robustness.

2. Backbone models
   
   (1) Swin-Transformer

Swin-Transformer, a state-of-the-art architecture, has gained significant attention in the field of computer vision. It utilizes a hierarchical design with shifted windows to capture spatial dependencies effectively. By exploiting the power of transformers, Swin-Transformer has demonstrated exceptional performance across various visual recognition tasks, making it a preferred choice for researchers and practitioners.

   (2) BERT Pre-Training of Image Transformer (BEiT)

BERT Image Transformer is an innovative approach that extends the success of BERT language models to the domain of computer vision. By leveraging the transformer architecture, it learns powerful representations for image understanding. BERT Image Transformer has shown promising results in tasks like image classification, object detection, and image captioning, revolutionizing the field of visual recognition.
