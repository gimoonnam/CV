# Image Classification using CNN

## Dataset: [Breast Cancer Images](https://www.kaggle.com/paultimothymooney/breast-histopathology-images)

<p float="left">
  <img src="https://github.com/gimoonnam/CV/blob/main/non-Cancer-Images.png" width="500" height="500" />
  <img src="https://github.com/gimoonnam/CV/blob/main/Cancer-Images.png" width="500" height="500" />
</p>



## Models

### Basic CNN 
![....](https://github.com/gimoonnam/CV/blob/main/basic-cnn/graph-cnn.png)
<p align="center">
  <img src="https://github.com/gimoonnam/CV/blob/main/basic-cnn/basic-cnn-results.png" />
</p>



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




