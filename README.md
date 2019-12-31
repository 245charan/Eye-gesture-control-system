# Eye-gesture-control-system
The goal of this Machine Learning project is to build a
classification model that can precisely identify human eyes blinks.
Working on this machine learning project will help you to play
dinosour game without a keyboard.

# Eye Blink Detection Algorithms

Eye blinks can be detected by referencing significant facial landmarks. Many software libraries can plot significant facial features within a given region of interest. Python’s dlib library uses Kazemi and Sullivan’s One Millisecond Face Alignment with an Ensemble of Regression Trees[3] to implement this feature.

The program uses a facial training set to understand where certain points exist on facial structures. The program then plots the same points on region of interests in other images, if they exists. The program uses priors to estimate the probable distance between keypoints [1].

The library outputs a 68 point plot on a given input image.

![alt text](https://lh4.googleusercontent.com/xolQSgnvCzqWTHM45UIj3mW1aIIzRsHrv-g7rDhtDXSiqsI6nvCLBkhTWJ8QMCwt2vwdpTYRggaULEUpAMl17pp_Siudj3q8PEUv9Vc2bXO9OcZHy34zODBuZSn1ygmdu4nZFwEp)

[1, Figure 1: Dlib Facial Landmark Plot]

For eye blinks we need to pay attention to points 37-46, the points that describe the eyes.

In Real Time Eye Blinking Using Facial Landmarks[2], Soukupová and Čech derive an equation that represents the Eye Aspect Ratio. The Eye Aspect Ratio is an estimate of the eye opening state.

Based on Figure 2, the eye aspect ratio can be defined by the below equation

![alt text](https://lh4.googleusercontent.com/nRrUTXr-8JDgU90YI_eKentZtQQeMSRWshc1TW73SBRKiJzRcund2J4T_VjyGAMHOB7nhgZJskpSa2o93e-eL7pyUhU_1D6UuNxC2f6SXlPLGr3iN9eWTCujRpOcn_OAf_KYHzIb)
[2, Figure 2: Eye Facial Landmarks]

![alt text](https://lh6.googleusercontent.com/qoeyiEcyQI4jfi3Bu2WTXX0rWsPYixvJjmqSjQ6ChvPpi2tCLBNXQCLedJNhaq4B-_U9vyk70e5vpOChxlPZNCUGAfv9A30pXsGXgarmUAmryM-M91hUS0Bgy2Yle1J7SX2NYSln) 
[2, Figure 3: Eye Aspect Ratio Equation]

“The Eye Aspect Ratio is a constant value when the eye is open, but rapidly falls to 0 when the eye is closed.” [1] Figure 4 show a person’s Eye Aspect Ratio over time. The person’s eyeblinks are obvious.


![alt text](https://lh5.googleusercontent.com/NEdpVPSIHlb6vKjJ86d3Q_spX0MrYB33GeMvdn3J3k4B4kr87Jpy7YBw4shn1JfwpXEOfNzjIhEHpsDh-dndx2j-riFGiDgbqk7diPEGl5mA__sgDKUuczbJd5tCUKSALwIJ6zp3) [2, Figure 4: Eye Aspect Ratio vs Time]

A program can determine if a person’s eyes are closed if the Eye Aspect Ratio falls below a certain threshold.


### Code Requirements
- Pyhton dependencies for machine learning.
  -OpenCV --> pip install opencv-python
  -imutils --> pip install imutils

- You will need to install pynput library to perform keyboard operations

Use below command to install:   pip install pynput 
( This library allows you to control and monitor input devices.
Currently, mouse and keyboard input and monitoring are supported. )  

- You will need shape_predictor_68_face_landmarks.dat file to detect 68-facial landmarks, I have included this file in repository.

- Just run below command to play Dino on your eye blink and Have fun! :   python Eye_gesture.py --shape-predictor shape_predictor_68_face_landmarks.dat

ref:https://hackaday.io/project/27552-blinktotext/log/68360-eye-blink-detection-algorithms



