# Image Style transfer using Pre-trained CNN (VGG19)

<img width="601" alt="style_tx_cat" src="https://user-images.githubusercontent.com/68460588/178955017-f89ff729-1123-4f51-b38f-436e246c19e0.png">

--- 

## Overview
Style Transfer is a process of convert the style of image with another style while preserving the content of image. It can be applied on images or videos.
This project is a mini project in the Deep Learning Nanodegree at Udacity. The implementation of style transfer method that is outlined in the [paper]( https://www.cv-foundation.org/openaccess/content_cvpr_2016/papers/Gatys_Image_Style_Transfer_CVPR_2016_paper.pdf).

--- 
## Implementation Details
The CNN often used as feature extractor to help in classification tasks. Although, CNN can extract feature for other tasks, such as Style Transfer, the CNN extract features to construct new image based on extracted feature of content and style image. Based on the [paper]( https://www.cv-foundation.org/openaccess/content_cvpr_2016/papers/Gatys_Image_Style_Transfer_CVPR_2016_paper.pdf) I used pre-trained CNN, which is the VGG19 was used as feature extractor in both content and style image. The Step of implementation as follow:
1)	I use the VGG19 as pre-trained feature extractor, so I ignore the classification part and freeze the weight of features portion.
2)	Load the content and the target image.
3)	Create the target image, which is a copy of content image. So during the iteration (learning process) in step4, we iterate for number of epochs to enhance the style of the target image while keep the content as it is. We will measure the loss function as total of content and style loss and used this total loss function to calculate the gradient and update the weight of target image.  
4)	Iterate though number of epochs to enhance the target image:
      - Input the content image to the VGG19 and extract features from specific layer, as mentioned in the paper.
      - Input the style image to the VGG19 and extract features from set of specific layers, as mentioned in the paper.
      - Calculate the content, style and total loss function.
      - Backward pass, compute gradient of the loss with respect to model parameters
      - Perform a single optimization step (parameter update)
 
--- 

## Results

### Content image
![octopus](https://user-images.githubusercontent.com/68460588/178957893-fd94fdad-b5bd-474a-a04c-25a4bcf20b0b.jpg)

### Style image
![hockney](https://user-images.githubusercontent.com/68460588/178957913-e11db21f-ee35-4fc8-bf94-7e2db9ad44b0.jpg)

### Output
![Screenshot (623)](https://user-images.githubusercontent.com/68460588/178958162-883c977b-be01-43c3-b013-aee1400a9a0a.png)


---

## Requirements	
- Python 3.7
- Numpy 
- PyTorch
- Matplotlib 
- Jupyter Notebook

---

## Running the project
The whole project is located in the jupyter notebook file ```Style_Transfer_Exercise.ipynb```, you can use the Anaconda envirenoment to open the Jupyter Notebook and install the requirement.

