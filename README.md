1. Introduction
   
In this Kaggle contest "Pawpularity," we had the opportunity to participate in a fascinating challenge that involved predicting the cuteness of stray dogs or cats. The underlying motivation behind this contest was to find improved ways of understanding and assessing these adorable animals. By leveraging advanced data analysis and machine learning techniques, we aimed to identify the factors that contribute to their appeal and likability. Ultimately, the goal was to provide valuable insights that could lead to better adaptations and accommodations for these precious creatures, ultimately improving their well-being and chances of finding loving homes. Furthermore, In this competition, participants are provided with a substantial dataset comprising images of domestic animals for training and testing purposes. Each image is accompanied by a set of metadata containing diverse features, including the crucial Pawpularity score, which is available only in the training set. While various machine learning approaches can be employed to model the dataset, we focus on the usage of the Swin-transformer, which had shown great performance in image analysis and align with our initial intuition for tackling this task.

2. General techniques

In this competition, we put forward three approaches. Our initial method serves as a prototype, while the second and third methods represent our enhanced versions. Throughout the task, we conducted tests using "Swin-Transformer" and observed its remarkable efficacy in this competition. As a result, we extensively explored the advantages of the Swin-transformer in the second and third methods, leading to improved outcomes. We will delve into the specifics of our implementation in the subsequent sections:

(1) Data preprocessing

 Fastai, a popular deep learning library, offers powerful data augmentation techniques.
Among these techniques, we used brightness, contrast, hue, and saturation adjustments
in this competition. With scales set at 0.2, these augmentations introduce controlled
variations to the input images. They modify the image's intensity, color range, sharpness,
tone, and vibrancy, enhancing the creation of diverse training data for improved model
generalization and robustness.
