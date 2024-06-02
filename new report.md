**Report**

**Dataset Description**

The maximum counts of the dataset of class were 900 images and rest of starts from 200 to 700. Therefore, there is an imbalance in the dataset. We applied image augmentation techniques such as flipping and rotating (90°, 180°, 270°). With these augmentation techniques, each class now has 900 pictures.

**Train, Test, Validation:**

1. **Validation 20% data**
1. **Train 80%**
1. **Test data was separate.**

**Classes:**

- bbps-0-1 - 0
- bbps-2-3  - 1
- cecum - 2
- dyed-lifted-polyps - 3
- dyed-resection-margins - 4
- esophagitis - 5
- impacted-stool - 6
- normal-z-line - 7
- polyps - 8
- retroflex-rectum - 9
- ulcerative-colitis – 10

All models other than VGG 16 used following layers:

1. Flatten
1. Dense with 128 units

**Hyperparameters:**

- RMSprop(learning\_rate=1e-5)
- Epochs 10

**Best Model:**

VGG – 16


|<p></p><p>**Model**</p>|<p></p><p>**Accuracy**</p>|<p></p><p>**Loss**</p>|||||
| :-: | :-: | :-: | :- | :- | :- | :- |
||<p></p><p>**train**</p>|<p></p><p>**Validation**</p>|<p></p><p>**Test**</p>|<p></p><p>**train**</p>|<p></p><p>**Validation**</p>|<p></p><p>**Test**</p>|
|<p>VGG-16</p><p></p>|97%|96\.34%|89\.84%|0\.10|0\.12|0\.29|
|<p>VGG – 19</p><p></p>|97%|92%|89\.95%|0\.19|0\.10|0\.32|
|DenseNet121|99\.7%|97%|88\.98%|0\.03|0\.08|0\.32|

**Augmentation:**

`      `**Simple                   Augmented                                  Simple                                  Augmented**

![A close-up of a person's stomach

Description automatically generated](Aspose.Words.f5c310e8-866a-4c6e-9c48-91ffc175f821.001.jpeg)      ![](Aspose.Words.f5c310e8-866a-4c6e-9c48-91ffc175f821.002.jpeg)          ![](Aspose.Words.f5c310e8-866a-4c6e-9c48-91ffc175f821.003.jpeg)              ![](Aspose.Words.f5c310e8-866a-4c6e-9c48-91ffc175f821.004.jpeg)              












**VGG-16**

**Fine Tuning**

We applied the VGG-16 model and fine-tuned the last block 5, achieving an accuracy of 97% on the training set. However, the validation accuracy was only 70%, indicating overfitting. There was a significant difference in loss, approximately 25% to 29%.

To mitigate overfitting, we added a dense layer with 128 neurons, applied a dropout of 0.2, and included batch normalization. This adjustment led to an improved performance with a training accuracy of 97% and validation accuracy of 96%. The loss values ranged between 0.25 to 0.30.

**layers:**

1. Flatten
1. Dense with 128 units
1. Dropout 0.2
1. Batch Normalization

![](Aspose.Words.f5c310e8-866a-4c6e-9c48-91ffc175f821.005.png)![](Aspose.Words.f5c310e8-866a-4c6e-9c48-91ffc175f821.006.png)

**Test Accuracy Confusion Matrix and Classification report:**

![](Aspose.Words.f5c310e8-866a-4c6e-9c48-91ffc175f821.007.png)![](Aspose.Words.f5c310e8-866a-4c6e-9c48-91ffc175f821.008.png)




















**VGG – 19:**

**Removed dropout and batch normalization layer.**

![](Aspose.Words.f5c310e8-866a-4c6e-9c48-91ffc175f821.009.png)![](Aspose.Words.f5c310e8-866a-4c6e-9c48-91ffc175f821.010.png)

**Test Accuracy Confusion Matrix and Classification report:**

![ref1]![](Aspose.Words.f5c310e8-866a-4c6e-9c48-91ffc175f821.012.png)











**DenseNet121**

![](Aspose.Words.f5c310e8-866a-4c6e-9c48-91ffc175f821.013.png)![](Aspose.Words.f5c310e8-866a-4c6e-9c48-91ffc175f821.014.png)

**Test Accuracy Confusion Matrix and Classification report:**

![ref2]![](Aspose.Words.f5c310e8-866a-4c6e-9c48-91ffc175f821.016.png)


[ref1]: Aspose.Words.f5c310e8-866a-4c6e-9c48-91ffc175f821.011.png
[ref2]: Aspose.Words.f5c310e8-866a-4c6e-9c48-91ffc175f821.015.png
