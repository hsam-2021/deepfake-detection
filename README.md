# Mini Project 3: Deepfake detection


## Introduction
We present a web based application for automatic detection of replacement and reenactment of deep fakes. We worked on a novel Res-Next convolution neural network for face reenactment which works for pose and expression variations and can be applied to single image or a video sequence. Our Res-Next Convolution neural network extracts the frame level features and these features used to train the Long Short Term Memory (LSTM) based Recurrent Neural Network (RNN) to classify whether the video is subject to any kind of manipulation or not. To emulate real time scenarios and make model performance better, we evaluated our model on the Celeb Deep Fake and DFDC dataset. 

In this project, we have worked on a novel Res-Next convolution neural network to detect whether the given video is deep faked or pristine. We trained the model on  the Celeb Deep Fake and DFDC dataset specifically and tried to improve the accuracy by experimenting with the depth and width of the architecture.


##  Directory Structure
Project structure should be as below:
```
Create new folder under that make following folders.
    
    --> Django Application : In this folder all the cloned files should be placed except model creation.
    
    --> Model Creation
```
1. Django Application 
   - In this directory the web application is saved. In this web application user can upload a short video and in real time the pretrained model will make prediction         whether the video is fake or pristine.
2. Model Creation
   - In this directory all the guidelines to create and train the model is provided.

## Model Architecture
The model consists of following layers:

• ResNext CNN : The pre-trained model of Residual Convolution Neural Network is used. The model name is resnext50_32x4d. This model consists
of 50 layers and 32 x 4 dimensions. Figure shows the implementation of our model.
of model.

![image](https://user-images.githubusercontent.com/94940146/168932029-f00507a9-b285-4295-88e7-17128251e164.png)

• LSTM architecture

![image](https://user-images.githubusercontent.com/94940146/168935598-90bb49fb-944b-4ac4-8783-7d3b59abdf20.png)
![image](https://user-images.githubusercontent.com/94940146/168935626-7ee1b975-dd3c-40ba-b58e-cf6d92a29067.png)



##  Demo 
<p align="center">
<img src="https://user-images.githubusercontent.com/94940146/168932391-9282d392-3dbf-4f95-8e1b-e0d3891ae788.png" />

</p>


##  Results
### Our application detects the deepfake correctly
![image](https://user-images.githubusercontent.com/94940146/168932553-910af90c-649c-4526-a63c-bcb2d9830874.png)

### Our application detects the real video correctly
![image](https://user-images.githubusercontent.com/94940146/168932582-08d31594-7357-4bc4-b6d3-a4a9e9cbe6ad.png)




## Steps to recreate

#### Prerequisites
- [ ] Nvidia Graphic card
- [ ]  CUDA 10 or above
- [ ] Parallel computing must be above 3.0
- [ ] Python 3.6.8
- [ ] Django >= v3.0
To recreate the results follow these steps:

### To run the application locally on your machine

 Copy your trained model to the models folder.
   - You can download the trained models from the [Google Drive](https://drive.google.com/drive/folders/1UX8jXUXyEjhLLZ38tcgOwGsZ6XFSLDJ-?usp=sharing) or you can train      your models using the steps mentioned in Model Creation directory.
   
#### Step 1 : Clone the repo and go to the Django Application
`git clone https://github.com/hsam-2021/deepfake-generation-and-detection `

#### Step 2: Install the requirements
`pip install -r requirements.txt`

**Note :** Here you may need to do a recursive install of the requirements.txt and depending up compatible versions update and re-install the requirements.txt

#### Step 3: Copy Models

Copy the pre-trained model to the models folder i.e Django Application/models/


#### Step 4: Run the project
Navigate to the path where manage.py file is located `\Deepfake_detection_miniproject_3\Django Application`. Open the command prompt and run 

`python manage.py runserver`

#### Step 5: Accessing the web app in browser
Once the server is up and running copy the following URL in any of your favourite browser.

`http://127.0.0.1:8000/`

#### Step 6: Upload video

The size of the video should not be more than 100 MB.

#### Step 6: Prediction

The prediction pipeline will give the predictionby first splitting the videos into frames, then do prediction and show real or fake as output.

## Experiments
To make better deepfakes we used DeepFaceLab XSEG masking techniques and SEAHD merging techniques and train for 20K iterations got following results.

### XSEG masking

![image](https://user-images.githubusercontent.com/94940146/168952299-20cf754d-8fbc-49fd-9606-a1bd93b7482b.png)

### SEAHD merging

![image](https://user-images.githubusercontent.com/94940146/168952131-16fba044-01bc-4d74-8df2-7cc640cc04ea.png)

## Conclusions

We tried to create better deepfake and then improve our detection model by doing some architectural changes, but as the artifacts were very less the model cpuld not detect such high quality deepfakes . However it performed with >90% accuracy on DFDC and Celeb deepfake datasets.


##  Contributors
   1. [Harshada Sinha](hs4703@nyu.edu)
   2. [Vaishnavi Rajput](vr2229@nyu.edu)
   3. [Drishti Singh](ds6730@nyu.edu)
   

##  Future Scope

### Below are some ideas that can improve the face detection 
- [ ]  Use cut out technique to improve the deepfake detection.
- [ ] Deploying the applications in free cloud.

## Acknowledgement
 Our sincere gratitute and thanks to our professors and Teaching assistants for their guidance and support for the project development.
 
[Siddharth Garg](https://engineering.nyu.edu/faculty/siddharth-garg?msclkid=47fb5f5dabed11ecbf387043e42d37ff)

[Arsalan Mosenia](http://www.arsalanmosenia.com/?msclkid=666ff071abed11ec93028e78876e48a0)



 





