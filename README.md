# Image Classification Algorithm Comparison

__TL;DR__ Dataset and Script for analysing and comparing different methods of machine learning in categorizing faces with/no mask

  The project will use basic methods of image processing algorithms for creating different datasets to which will be applied 4 methods of classifying the images with and without masks along with gender identification.


----
  Machine learning comes with many algorithms such as detection, recognition, classification and so on. Within this piece, we will be focusing on the classification algorithm of multimedia - images. The context of the multimedia is the current global situation that shifted the way we normally do activities. The Covid-19 pandemic forces us to wear masks in public spaces, where for security purposes, the face recognition systems are facing impediments. To improve the system, we need to have a good understanding of the tools available. To do so, we will use data sets of masked and unmasked people.

## Data set selection

  The image repository is a mix of the repository [Real World Masked Face Dataset](https://github.com/X-zhangyang/Real-World-Masked-Face-Dataset) found on GitHub, and the repository [Face Mask Detection Dataset](https://www.kaggle.com/omkargurav/face-mask-dataset) from Kaggle. The mix brought in a variety of ethnicities (the GitHub repository has a majority of Chinese faces) and image quality (the Kaggle dataset contains images with greater resolution compared to the first dataset).
   
   The GitHub repository is created for face recognition, so the images were split into folders by the person wearing and not wearing a mask. Therefore, I have made my own hand selection of images and split them by mask and no mask images. The selection was on the criteria: the full face to be visible(as the dataset has the faces already cropped out), the face to not be turned to either side so much that half of the face is not visible, not wearing sunglasses, but vision glasses were accepted(the eyes will be visible). The same criteria were applied to the second dataset, but the face cropping was done manually - faces extraction, from this dataset, can be improved by applying face detection algorithms to the full image. The dataset is available on [Google Drive](https://drive.google.com/drive/folders/19jKp5NA7Q8_u1ezzYAwaBzWJb7OzGUgk?usp=sharing).
   
   The face recognition algorithms will have an improved result when applying gender identification. Nevertheless, the simple model of gender classification can be used in demographics and building up target groups in a business.

  Therefore, the two existing folders will be split into other two folders for the "Feminine" and "Masculine" genders. In this way, we will obtain a multi-class classification problem with 4 different classes.


  The experiment will consist of creating a repository with the flattened arrays of the selected images, create four other variations, and compare four models trained with the five repositories created. The repositories will be created by applying the following methods:
1. Image Pre-processing
2. Feature extraction
3. Image augmentation
4. Class Decomposition

  The following code will take each image from the `data` file, read it, resize it, append it to the repositories: flattened pixels, binarised pixels, and the extracted features; and add the class in the `target` list.
