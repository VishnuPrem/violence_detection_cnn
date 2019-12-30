# Violence detection from Videos using Dual stream CNN

This project is to implement an action detection binary classifier to detect violence by extracting spatial and temporal data. The classifier finds applications in public surveillance and social media screening. The feature extraction method and model architecture implemented can be extended to any kind of action recognition from videos. The method implemented is decribed in this [**journal paper**](https://arxiv.org/pdf/1406.2199.pdf) article titled 'Two-Stream Convolutional Networks for Action Recognition in Videos'.

The [**dataset**](https://www.kaggle.com/mohamedmustafa/real-life-violence-situations-dataset
) we used consists of 1000 short clips from each class: Violence and Nonviolence. Each video ranges from a duration of 1 to 6 seconds.
The videos from the violence class includes violent interactions between people in different setting like street fights and physical altercations during sports games. The non violence class has videos of people in taking part in various activities that are non violent.

<p align="center"> 
<img src="/img/img3.jpg" width = "400"/>
</p> 
Here are some examples from the violence class.

<p align="center"> 
<img src="/img/img4.jpg" width = "400"/>
</p> 
And these are some examples from the non-violence class.

## Data Preprocessing Pipeline

Since the dataset consists of raw videos, some processing was done to make it useful for training:

<p align="center"> 
<img src="/img/img1.jpg" width = "400"/>
</p> 

1. 10 frames are extracted from the middle second in the video
2. All frames are cropped to a square and resized to a fixed resolution
3. The optical flow data is extracted from consecutive images
4. The first frame and the optical flow images are stacked to form the input to the model

## Model 

The CNN has the dual stream architecture described in this [**journal paper**](https://arxiv.org/pdf/1406.2199.pdf) where the spatial stream takes the first frame and the termporal stream takes the optical flow data as the input.

<p align="center"> 
<img src="/img/img2.jpg" width = "400"/>
</p> 

