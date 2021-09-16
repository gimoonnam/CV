# Image Classification using CNN

## Dataset: [Breast Cancer Images](https://www.kaggle.com/paultimothymooney/breast-histopathology-images)

<p float="left">
  <img src="https://github.com/gimoonnam/CV/blob/main/non-Cancer-Images.png" width="500" height="500" />
  <img src="https://github.com/gimoonnam/CV/blob/main/Cancer-Images.png" width="500" height="500" />
</p>



## Models

### Basic CNN 
```
           OPERATION           DATA DIMENSIONS   WEIGHTS(N)   WEIGHTS(%)

               Input   #####     50   50    3
              Conv2D    \|/  -------------------       896     0.1%
                relu   #####     50   50   32
              Conv2D    \|/  -------------------      9248     1.4%
                relu   #####     48   48   32
  BatchNormalization    μ|σ  -------------------       128     0.0%
                       #####     48   48   32
        MaxPooling2D   Y max -------------------         0     0.0%
                       #####     24   24   32
             Dropout    | || -------------------         0     0.0%
                       #####     24   24   32
              Conv2D    \|/  -------------------     18496     2.8%
                relu   #####     24   24   64
              Conv2D    \|/  -------------------     36928     5.5%
                relu   #####     22   22   64
  BatchNormalization    μ|σ  -------------------       256     0.0%
                       #####     22   22   64
        MaxPooling2D   Y max -------------------         0     0.0%
                       #####     11   11   64
             Dropout    | || -------------------         0     0.0%
                       #####     11   11   64
              Conv2D    \|/  -------------------     36928     5.5%
                relu   #####     11   11   64
              Conv2D    \|/  -------------------     36928     5.5%
                relu   #####      9    9   64
  BatchNormalization    μ|σ  -------------------       256     0.0%
                       #####      9    9   64
        MaxPooling2D   Y max -------------------         0     0.0%
                       #####      4    4   64
             Dropout    | || -------------------         0     0.0%
                       #####      4    4   64
             Flatten   ||||| -------------------         0     0.0%
                       #####        1024
               Dense   XXXXX -------------------    524800    78.8%
                relu   #####         512
             Dropout    | || -------------------         0     0.0%
                       #####         512
               Dense   XXXXX -------------------      1026     0.2%
             softmax   #####           2
```

<p align="center">
  <img src="https://github.com/gimoonnam/CV-BreastCancerImages/blob/main/basic-cnn/loss_acc_cnn.png" />
  <img src="https://github.com/gimoonnam/CV-BreastCancerImages/blob/main/basic-cnn/CM_by_cnn.png" />
</p>


```
              precision    recall  f1-score   support

    Negative       0.84      0.85      0.84      3679
    Positive       0.85      0.83      0.84      3669

    accuracy                           0.84      7348
   macro avg       0.84      0.84      0.84      7348
weighted avg       0.84      0.84      0.84      7348

```



### VGG13

```
           OPERATION           DATA DIMENSIONS   WEIGHTS(N)   WEIGHTS(%)

               Input   #####    224  224    3
              Conv2D    \|/  -------------------      1792     0.0%
                relu   #####    224  224   64
              Conv2D    \|/  -------------------     36928     0.0%
                relu   #####    224  224   64
  BatchNormalization    μ|σ  -------------------       256     0.0%
                       #####    224  224   64
        MaxPooling2D   Y max -------------------         0     0.0%
                       #####    112  112   64
             Dropout    | || -------------------         0     0.0%
                       #####    112  112   64
              Conv2D    \|/  -------------------     73856     0.1%
                relu   #####    112  112  128
              Conv2D    \|/  -------------------    147584     0.2%
                relu   #####    110  110  128
  BatchNormalization    μ|σ  -------------------       512     0.0%
                       #####    110  110  128
        MaxPooling2D   Y max -------------------         0     0.0%
                       #####     55   55  128
             Dropout    | || -------------------         0     0.0%
                       #####     55   55  128
              Conv2D    \|/  -------------------    295168     0.4%
                relu   #####     55   55  256
              Conv2D    \|/  -------------------    590080     0.7%
                relu   #####     53   53  256
  BatchNormalization    μ|σ  -------------------      1024     0.0%
                       #####     53   53  256
        MaxPooling2D   Y max -------------------         0     0.0%
                       #####     26   26  256
             Dropout    | || -------------------         0     0.0%
                       #####     26   26  256
              Conv2D    \|/  -------------------   1180160     1.4%
                relu   #####     26   26  512
              Conv2D    \|/  -------------------   2359808     2.9%
                relu   #####     24   24  512
  BatchNormalization    μ|σ  -------------------      2048     0.0%
                       #####     24   24  512
        MaxPooling2D   Y max -------------------         0     0.0%
                       #####     12   12  512
             Dropout    | || -------------------         0     0.0%
                       #####     12   12  512
              Conv2D    \|/  -------------------   2359808     2.9%
                relu   #####     12   12  512
              Conv2D    \|/  -------------------   2359808     2.9%
                relu   #####     10   10  512
  BatchNormalization    μ|σ  -------------------      2048     0.0%
                       #####     10   10  512
        MaxPooling2D   Y max -------------------         0     0.0%
                       #####      5    5  512
             Dropout    | || -------------------         0     0.0%
                       #####      5    5  512
             Flatten   ||||| -------------------         0     0.0%
                       #####       12800
               Dense   XXXXX -------------------  52432896    63.4%
                relu   #####        4096
             Dropout    | || -------------------         0     0.0%
                       #####        4096
               Dense   XXXXX -------------------  16781312    20.3%
                relu   #####        4096
             Dropout    | || -------------------         0     0.0%
                       #####        4096
               Dense   XXXXX -------------------   4097000     5.0%
                relu   #####        1000
             Dropout    | || -------------------         0     0.0%
                       #####        1000
               Dense   XXXXX -------------------      2002     0.0%
             softmax   #####           2
```

<p align="center">
  <img src="https://github.com/gimoonnam/CV-BreastCancerImages/blob/main/basic-cnn/loss_acc_vgg13.png" />
  <img src="https://github.com/gimoonnam/CV-BreastCancerImages/blob/main/basic-cnn/CM_by_vgg13.png" />
</p>

```
              precision    recall  f1-score   support

    Negative       0.83      0.87      0.85       786
    Positive       0.86      0.82      0.84       754

    accuracy                           0.85      1540
   macro avg       0.85      0.85      0.85      1540
weighted avg       0.85      0.85      0.85      1540
```


