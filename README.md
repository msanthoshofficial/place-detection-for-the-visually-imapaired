# place-detection-for-the-visually-imapaired
This model is based on opencv,yolov3 
API's used are:
  1.gTTs for text to speech converson
  2.pyTessaract for OCR model
This helps the visually imapaired to find objects infront of them and identify the text written on it.
*Just install the above files and download the yolov3 weights and you are good to go.
PLACE DETECTION APP FOR VISUALLY IMPAIRED PERSON
OBJECT DETECTION
● This feature detects the objects in the image which is captured by the user.
● For now 80 objects can be detected if required we can add object using custom
dataset
● We are using Yolo version 3 and Opencv to detect the objects,the neural network
used here is DNN(deep neural network).
YOLO [ you only look once ]V3:
YOLOv3 is the latest variant of a popular object detection algorithm YOLO – You Only Look
Once. The published model recognizes 80 different objects in images and videos, but most
importantly it is super fast and nearly as accurate as Single Shot MultiBox (SSD).
Yolo contains three sub folders:
● Yolo weights
● Yolo config
● Coco names
Yolo weights- This is the saved weights of the pre-trained neural network ,we use it so that
we don't have to train the model every time we run the program.
Yolo config- yolo.cfg is based on the darknet reference network.
Coco names- This contains all the 80 labels/names of the objects that we have trained our
yolo model on.
Opencv [ Open Source Computer Vision Library ] :
Opencv is a library of programming functions mainly aimed at real-time computer vision.
Opencv uses hardware acceleration to complete the process quickly.
Implementation of object detection model:
● First we install all the requirements and import all the libraries required.
● Then we set the confidence threshold values as 0.5 i.e confidence value greater than
0.5 is considered as ok to form the boundary boxes over the objects and in the final
objects greater than 30% accuracy are only considered.
● And then the labels are added to the objects.
OBJECT POSITIONING:
● Based on the boundary boxes appended on the objects detected the position of the
object can be easily identified.
● The position of the boundary box can be found though these 4 parameters
[W,H,W,H].
● After finding the position the names of detected objects plus the count of the objects
plus the position of the object is made into a single string and appended to a list so
that we can do text to speech conversion later.
OPTICAL CHARACTER RECOGNITION:
Why OCR?
If the visually impaired person wants to read the text in any image,we can use OCR.
OCR is the conversion of text present in the images to machine encoded text. The output will
be human readable text which is exactly the same as the text present in the image.
IMPLEMENTATION OF OCR :
● We can implement OCR using Py-Tesseract.
● Pytesseract is a tool which is used for performing OCR that extracts the text from
the image.
● Instead of writing into a file it will directly output the text.
● We can install the Py-Tesseract file in our working environment and it can be used
by calling it in our code.
● Tesseract Tools for Android is a set of Android APIs
FACE RECOGNITION:
This feature helps the visually impaired people by recognizing / Identifying a known person
based on the image source.
We use a face recognition api which is also based on YoloV3.
Implementation of face recognition:
● Initially the known faces are saved in a folder with the image name as their respective
names.
● We are going to train the model with the known faces, which we are going to detect
and recognize.
● The identified faces are then cropped and encoded in a separate directory to perform
classification.
● The model checks whether the face is known or unknown by a basic check before
classification to reduce time complexity,if the faces are unknown then it is tagged as
unknown, else it's left for classification.
● Now the known faces are classified based on multiple classification instead of binary
classification and then the names of the persons are tagged and added to a list as
strings.
TEXT TO SPEECH :
● The outputs which we get from Object detection, OCR and Face recognition will be
stored as strings in their respective lists.
● But we can't instruct the blind people with bare texts.
● So we need to convert the text or strings to voice or speech.
● To perform text to speech conversion we are going to use gTTs API.
● gTTS is a very easy to use tool which converts the text entered, into audio which can
be saved as a mp3 file.
● We can use language = 'en' command to prefer the language as English.
DEPLOYMENT IN A WEB APP:
● We are using Jupyter web app for Deploying our model in a local host webpage.
● The following commands are executed that turn jupyter notebooks into web
applications.
● pip install appmode
● jupyter nbextension enable --py --sys-prefix appmode
● jupyter serverextension enable --py --sys-prefix appmode
● We can run our code in app mode and get the output in a webpage.
● We can also change the user interface by manipulating custom.js file.
