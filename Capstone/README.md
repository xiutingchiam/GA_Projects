

[![Linkedin Badge](https://img.shields.io/badge/-XiuTing-blue?style=flat-square&logo=Linkedin&logoColor=white&link=https://www.linkedin.com/in/ishagupta20//)](https://www.linkedin.com/in/xiuting) [![Gmail Badge](https://img.shields.io/badge/-xiuting@gmail.com-c14438?style=flat-square&logo=Gmail&logoColor=white&link=mailto:xiuting@gmail.com)](mailto:xiuting@gmail.com)
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
# Capstone: Signature Verification
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
## Background
Handwritten signatures have long been used as a form of biometric technique frequently used for personal identification and verification. Many documents like bank checks and legal transactions require signature verification, and traditional ways of going through signature-based documents and verifying signatures at a large scale is a very difficult and time consuming task.


## Problem Statement
Handwritten signatures are very important in our social and legal life for verification and authentication. However, detecting a signature forgery (especially skilled forgeries) is a challenging task as no two signatures made by the same person are exactly the same.

To resolve this problem, we want to build a model that can detect forgery that might be very similar in case of skilled forgeries, while accounting for the below variations in genuine signatures and establish the authenticity of a signature:
- Variability due to different pens used
- Variability arising out of the fact that “No two signatures of the same person are exactly- same” , and
- Noisy background of signatures, eg. stamp, signature positioning, size difference

We will use accuracy as a metric to select the best model for this problem statement.


## Dataset
<b>Handwritten Signatures: </b> [(source)](https://www.kaggle.com/divyanshrai/handwritten-signatures)<br>
Dataset contains signatures of 55 people, 20 genuine signatures and forged signatures per person. In total, there are 1,100 genuine signatures and 1,100 forged signatures.


## Methodology
1. Preview and examine image data.
2. Pre-process images.
3. Prepare data by creating lists of genuine and forged signatures and binary classification labels.
4. Explore and visualize data for data distribution, shape and labels.
5. Create pairs of genuine-genuine and genuine-forged signatures.
6. Create batches of pair signatures for modeling
7. Use deep learning to train data
8. Predict test data using the best epoch model and predict class labels using threshold of euclidean distance.
9. Evaluate models.

## Siamese Neural Network (SNN)
|   Model No. | Optimizer   |   Batch Size |   Learning Rate |   Epoch Number |   Accuracy (%) |
|------------:|:------------|-------------:|----------------:|---------------:|---------------:|
|           1 | Adam        |           32 |          0.0001 |             13 |           65.6 |
|           2 | Adam        |           64 |          0.0001 |             24 |           69.3 |
|           3 | Adam        |          256 |          0.0001 |              8 |           64.8 |
|           4 | Adam        |           32 |          1e-05  |              7 |           65.9 |
|           5 | Adam        |           64 |          1e-05  |             79 |           70.4 |
|           6 | Adam        |          256 |          1e-05  |              2 |           71.4 |
|           7 | RMSprop     |           32 |          0.0001 |              8 |           72.2 |
|           8 | RMSprop     |           64 |          0.0001 |             11 |           69.2 |
|           9 | RMSprop     |          256 |          0.0001 |             25 |           72.1 |
|          10 | RMSprop     |           32 |          1e-05  |              3 |           69.9 |
|          11 | RMSprop     |           64 |          1e-05  |             18 |           68.2 |
|          12 | RMSprop     |          256 |          1e-05  |              0 |           70.7 |

As Siamese Neural Networks work well with insufficient data as in our case, we focused on improving the performance of our models through the fine-tuning of the stated optimizers and parameters listed in the score table. Models were also run using Optimizers such as Adagrad and SGD. However, these models did not yield good results as compared to models built using Adam and RMSprop, and hence they were not included in this score table.

Our best model is model no. 7, which gave us an accuracy of 72.2% and a threshold of 0.1519. Signatures that have a difference in euclidean distance from a genuine signature of > 0.1519 will be predicted as forged, while signatures with a difference of less than 0.1519 in euclidean distance will be predicted as genuine.

## Future Works
1. Build model using triplet loss on Siamese Neural Networks (Current models built on contrastive loss)
2. Look into pre-trained models and fine-tune the model more.
3. Deploy model on web application
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
## Folder Organization
```
Capstone/
|__ README.md
|__ code/
|   |__ 01_preprocessing.ipynb
|   |__ 02_modeling.ipynb  
|__ datasets/
|   |__ train/
|   |  |__forged/
|   |  |   |__forged_person/
|   |  |__genuine/
|   |      |__genuine_person/
|   |__ test/  
|__ images/
|   |__ forged_signature.png  
|   |__ genuine_signature.png
|__ weights/
|   |
|__ slides/
    |__ signature_authentication.pdf
```

------------------------------------------------------------------------------------------------------------------------------------------------------------------

⭐️ From [XiuTing](https://github.com/xiutingchiam)
