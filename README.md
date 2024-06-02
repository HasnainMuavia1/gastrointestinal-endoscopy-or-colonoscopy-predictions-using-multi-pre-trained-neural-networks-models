**Report**

**Dataset Description**

The maximum counts of the dataset of class were 900 images and rest of
starts from 200 to 700. Therefore, there is an imbalance in the dataset.
We applied image augmentation techniques such as flipping and rotating
(90°, 180°, 270°). With these augmentation techniques, each class now
has 900 pictures.

**Train, Test, Validation:**

1.  **Validation 20% data**

2.  **Train 80%**

3.  **Test data was separate.**

**Classes:**

-   bbps-0-1 - 0

-   bbps-2-3 - 1

-   cecum - 2

-   dyed-lifted-polyps - 3

-   dyed-resection-margins - 4

-   esophagitis - 5

-   impacted-stool - 6

-   normal-z-line - 7

-   polyps - 8

-   retroflex-rectum - 9

-   ulcerative-colitis -- 10

> All models other than VGG 16 used following layers:

1.  Flatten

2.  Dense with 128 units

**Hyperparameters:**

-   RMSprop(learning_rate=1e-5)

-   Epochs 10

**Best Model:**

VGG -- 16

  ------------------------------------------------------------------------------------------------
  **Model**     **Accuracy**                               **Loss**                     
  ------------- -------------- ---------------- ---------- ----------- ---------------- ----------
                **train**      **Validation**   **Test**   **train**   **Validation**   **Test**

  VGG-16        97%            96.34%           89.84%     0.10        0.12             0.29

  VGG -- 19     97%            92%              89.95%     0.19        0.10             0.32

  DenseNet121   99.7%          97%              88.98%     0.03        0.08             0.32
  ------------------------------------------------------------------------------------------------

**Augmentation:**

**Simple Augmented Simple Augmented**

![A close-up of a person\'s stomach Description automatically
generated](vertopal_6d0a176a7af64a3b9aa7bbbdf4bdd54a/media/image1.jpeg){width="1.28125in"
height="1.0748534558180227in"}
![](vertopal_6d0a176a7af64a3b9aa7bbbdf4bdd54a/media/image2.jpeg){width="1.2604166666666667in"
height="1.0573753280839895in"}
![](vertopal_6d0a176a7af64a3b9aa7bbbdf4bdd54a/media/image3.jpeg){width="1.15625in"
height="0.9817749343832021in"}
![](vertopal_6d0a176a7af64a3b9aa7bbbdf4bdd54a/media/image4.jpeg){width="1.1902766841644794in"
height="1.010667104111986in"}

**VGG-16**

**Fine Tuning**

We applied the VGG-16 model and fine-tuned the last block 5, achieving
an accuracy of 97% on the training set. However, the validation accuracy
was only 70%, indicating overfitting. There was a significant difference
in loss, approximately 25% to 29%.

To mitigate overfitting, we added a dense layer with 128 neurons,
applied a dropout of 0.2, and included batch normalization. This
adjustment led to an improved performance with a training accuracy of
97% and validation accuracy of 96%. The loss values ranged between 0.25
to 0.30.

**layers:**

1.  Flatten

2.  Dense with 128 units

3.  Dropout 0.2

4.  Batch Normalization

![](vertopal_6d0a176a7af64a3b9aa7bbbdf4bdd54a/media/image5.png){width="3.0884733158355204in"
height="2.294134951881015in"}![](vertopal_6d0a176a7af64a3b9aa7bbbdf4bdd54a/media/image6.png){width="3.0576312335958007in"
height="2.3085958005249343in"}

**Test Accuracy Confusion Matrix and Classification report:**

![](vertopal_6d0a176a7af64a3b9aa7bbbdf4bdd54a/media/image7.png){width="3.2786537620297462in"
height="1.9671916010498687in"}![](vertopal_6d0a176a7af64a3b9aa7bbbdf4bdd54a/media/image8.png){width="2.983741251093613in"
height="2.7041152668416446in"}

**VGG -- 19:**

**Removed dropout and batch normalization layer.**

![](vertopal_6d0a176a7af64a3b9aa7bbbdf4bdd54a/media/image9.png){width="2.761791338582677in"
height="2.051474190726159in"}![](vertopal_6d0a176a7af64a3b9aa7bbbdf4bdd54a/media/image10.png){width="2.773011811023622in"
height="2.0936996937882766in"}

**Test Accuracy Confusion Matrix and Classification report:**

![](vertopal_6d0a176a7af64a3b9aa7bbbdf4bdd54a/media/image11.png){width="2.9093416447944005in"
height="1.8427690288713912in"}![](vertopal_6d0a176a7af64a3b9aa7bbbdf4bdd54a/media/image12.png){width="2.8080708661417324in"
height="2.5449081364829396in"}

**DenseNet121**

![](vertopal_6d0a176a7af64a3b9aa7bbbdf4bdd54a/media/image13.png){width="3.050472440944882in"
height="2.26590769903762in"}![](vertopal_6d0a176a7af64a3b9aa7bbbdf4bdd54a/media/image14.png){width="3.055777559055118in"
height="2.307194881889764in"}

**Test Accuracy Confusion Matrix and Classification report:**

![](vertopal_6d0a176a7af64a3b9aa7bbbdf4bdd54a/media/image11.png){width="3.279296806649169in"
height="2.077097550306212in"}![](vertopal_6d0a176a7af64a3b9aa7bbbdf4bdd54a/media/image15.png){width="2.4929560367454067in"
height="2.259325240594926in"}
