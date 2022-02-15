# Face-Emotion-Recognition
# Introduction
Emotion recognition is the process of identifying human emotion. People vary widely in their accuracy at recognizing the emotions of others. Use of technology to help people with emotion recognition is a relatively nascent research area. Generally, the technology works best if it uses multiple modalities in context. To date, the most work has been conducted on automating the recognition of facial expressions from video, spoken expressions from audio, written expressions from text, and physiology as measured by wearables. Facial expressions are a form of nonverbal communication. Various studies have been done for the classification of these facial expressions. There is strong evidence for the universal facial expressions of seven emotions which include: neutral happy, sadness, anger, disgust, fear, and surprise. So it is very important to detect these emotions on the face as it has wide applications in the field of Computer Vision and Artificial Intelligence. These fields are researching on the facial emotions to get the sentiments of the humans automatically.
# Problem Statement 
The Indian education landscape has been undergoing rapid changes for the past 10 years owing to the advancement of web-based learning services, specifically, eLearning platforms.

Global E-learning is estimated to witness an 8X over the next 5 years to reach USD 2B in 2021. India is expected to grow with a CAGR of 44% crossing the 10M users mark in 2021. Although the market is growing on a rapid scale, there are major challenges associated with digital learning when compared with brick and mortar classrooms. One of many challenges is how to ensure quality learning for students.

Digital platforms might overpower physical classrooms in terms of content quality but when it comes to understanding whether students are able to grasp the content in a live class scenario is yet an open-end challenge. In a physical classroom during a lecturing teacher can see the faces and assess the emotion of the class and tune their lecture accordingly, whether he is going fast or slow. He can identify students who need special attention Digital classrooms are conducted via video telephony software program (ex-Zoom) where it’s not possible for medium scale class (25-50) to see all students and access the mood. Because of this drawback, students are not focusing on content due to lack of surveillance.

While digital platforms have limitations in terms of physical surveillance but it comes with the power of data and machines which can work for you. It provides data in the form of video, audio, and texts which can be analyzed using deep learning algorithms. Deep learning backed system not only solves the surveillance issue, but it also removes the human bias from the system, and all information is no longer in the teacher’s brain rather translated in numbers that can be analyzed and tracked.

I will solve the above-mentioned challenge by applying deep learning algorithms to live video data. The solution to this problem is by recognizing facial emotions.
# Dataset Information
The data comes from the past Kaggle competition “Challenges in Representation Learning: Facial Expression Recognition Challenge”: we have defined the image size to 48 so each image will be reduced to a size of 48x48.The faces have been automatically registered so that the face is more or less centered and occupies about the same amount of space in each image. Each image corresponds to a facial expression in one of six categories (0=Angry, 1=Fear, 2=Sad, 3=Happy, 4=Surprise, 5=Neutral). The dataset contains approximately 36K images.

Dataset link - www.kaggle.com/jonathanoheix/face-expression-recognition-dataset
# Dependencies 
-Python 3

-Tensorflow 2.0

-Streamlit

-Streamlit-Webrtc

-OpenCV
# Model Creation 
Using Deep learning CNN In deep learning, a convolutional neural network (CNN, or ConvNet) is a class of deep neural network, most commonly applied to analyze visual imagery.based on the shared-weight architecture of the convolution kernels or filters that slide along input features and provide translation equivariant responses known as feature maps.Counter-intuitively, most convolutional neural networks are only equivariant, as opposed to invariant, to translation. They have applications in image and video recognition, recommender systems, image classification, image segmentation, medical image analysis, natural language processing, brain-computer interfaces, and financial time series.CNNs are regularized versions of multilayer perceptrons. Multilayer perceptrons usually mean fully connected networks, that is, each neuron in one layer is connected to all neurons in the next layer. The "full connectivity" of these networks make them prone to overfitting data. Typical ways of regularization, or preventing overfitting, include: penalizing parameters during training (such as weight decay) or trimming connectivity (skipped connections, dropout, etc.) CNNs take a different approach towards regularization: they take advantage of the hierarchical pattern in data and assemble patterns of increasing complexity using smaller and simpler patterns embossed in their filters. Therefore, on a scale of connectivity and complexity, CNNs are on the lower extreme. Convolutional networks were inspired by biological processes in that the connectivity pattern between neurons resembles the organization of the animal visual cortex. Individual cortical neurons respond to stimuli only in a restricted region of the visual field known as the receptive field. The receptive fields of different neurons partially overlap such that they cover the entire visual field.CNNs use relatively little pre-processing compared to other image classification algorithms. This means that the network learns to optimize the filters (or kernels) through automated learning, whereas in traditional algorithms these filters are hand-engineered. This independence from prior knowledge and human intervention in feature extraction is a major advantage.
![image](https://user-images.githubusercontent.com/85886359/154071305-79f06da3-12f9-4024-a478-43ed342c211c.png)

The training gave the accuracy of 83% and test accuracy of 57%. It seems good as compared to the dataset. So, I save the model and the detection i got from live video was excellent. 
One drawback of the system is the some Disgust faces are showing Neutral .Because less no. of disgust faces are given to train .This may be the reason.
I deployed these model on streamlit
# Algorithm
First, the haar cascade method is used to detect faces in each frame of the webcam feed.

The region of image containing the face is resized to 48x48 and is passed as input to the CNN.

The network outputs a list of softmax scores for the six classes of emotions.

The emotion with maximum score is displayed on the screen.
# Loss and Accuracy plot 
![image](https://user-images.githubusercontent.com/85886359/154072670-69bcab7e-4f22-4ecd-8f9f-8b16e3a12fc8.png)
# Deployment of Streamlit WebApp in Heroku and Streamlit
In this repository I have made a front end using streamlit .Streamlit doesn’t provide the live capture feature itself, instead uses a third party API. I have used streamlit-webrtc which helped to deal with real-time video streams. Image captured from the webcam is sent to VideoTransformer function to detect the emotion. Then this model was deployed on heroku and streamlit platform with the help of buildpack-apt which is necessary to deploy opencv model on heroku and streamlit.
- Heroku Link: - https://face-emotion-recognition-alma.herokuapp.com/ 
# Conclusion 
Finally I build the webapp and deployed which has training accuracy of 70.56% and test accuracy of 60.71%

-If failed to access the website and just wanted to see how the webapp works, then visit this link:-https://drive.google.com/drive/folders/17EB1ayDrVSacF6AaqdnQ_SITfR-q8zhx?usp=sharing
