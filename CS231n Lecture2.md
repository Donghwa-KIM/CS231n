## CS231n Lecture2

[TOC]

# Sematic gap

 Width x Height x RGB (complexity of tasks)  

![table](https://Donghwa-KIM.github.io/picture/cs231n/Semantic_Gap.svg.png)

# Challenges

1. Viewpoint Variation: zoom, shift, all pattern is changed 

2.     Illumination:brightness value


3.     Deformation:for example, strange images 


4.     Occlusion:hidden foreground object


5.     Backgroundclutter: how to distinguish between foreground and background


6.    Intra-classvariation: full species that look similar

      ​

*Training example for pattern matching base on **ImageNet** – CIFAR-10: 10 labels and 50,000 training images [32x32], 10,000 test images

![table](https://donghwa-kim.github.io/picture/cs231n/l1.png)

# Q & A

**Q. How does the classificationspeed depend on the size of the training data?**

- Linearlyindependently, 

- CNNs:despite of expensive training, it is possible to test in real time.

  ​

**Q. What is the accuracy of the nearest neighbor classifier on the training data, when using the Euclidean distance?**

- 100%

- We’re always find a training example exactly on top of that test which has 0distance, according to data manifold.

  ​

**Q. What if using Manhattan distance instead?**

- Absolute value, it will be same as well.



**Q. What is the accuracy of the k-nearest neighbor classifier on the training data?**

- Basically, the point around you overwhelmed, the best example is of a different class.



**Q.** **How do we set the hyper-parameters?**

- Very problem-dependent
- Justtry them all out and see what works best
- K-nearest neighbor on images never used due to shifted, messed up and darkened image



**_Parametric approach_**

- It is going to be choose parameters (weights)
- Linear classifier (w, b)



**Q. What does the linear classifier do?**

![table](https://Donghwa-KIM.github.io/picture/cs231n/linear.png)



**Q. How we could process differentscales from images?**

- Resizethe different images easily such as augmentation.
- Jittering andstretching : huge amount of that stuff such that is rotated.



**Q. Average of pixels?**

- Work worse, it doesn’t want to minimize the mean of images.



**_A feacture for images_**

- There are many label examples in images based on colors.



**Q. If a class is imbalanced?**

- The bias for imbalanced class would be higher because this classifier is just used to spewing out large numbers **based on the loss.**

- We must find data manofold what you want to do, jittering, rotating and separating out, for example, all the cars and non-cars.

  ​

**Q. What would be a very hard set of classes for a linear classifier todistinguish?**

- Negative Images mean to make the shape such as an edge but not exact color for the originalimage. 
- In a image, forexample, there is a cat on the left side and there is also a cat next to it. It dosen’t have problem, the weight would be shown on the pixels in the image.



**_Stacking linear classifiers_**

- The purpose for image classification is to minimize the loss, changing weights unitl loss is almost zero, and then that is classifying all the images unless it is higher loss.





