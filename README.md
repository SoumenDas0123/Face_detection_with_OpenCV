# Face Detection with OpenCV

We are going to detect the faces in an image with OpenCV which is a very popular library for computer vision. When it comes to detecting face, machine doesnt just
detect the face in a straight forward way, because it requires lots of small features and patterns to be matched. Hence the task of identifying face are broken down
into lots of smaller jobs where it tries to match individual patterns and features generally present in a human face. OpenCV uses machine learning classification
algorithms to do that.  

There will be thousands of smaller classification tasks which need to be performed on every parts of the image and it makes the preocess computationally very heavy.
For turn around OpenCV uses cascade classifier, it doesnt run all classification jobs at a single time, as we know that most of the parts of an image wont have faces.
Instead it searchs for the patterns in several stages, where it looks for the deatailed features, only when it passes few rough and quick seraches in the previous
stage.  

OpenCV has these cascade classifers in terms of XML files, which we can use as pretrained features or patterns. Here we are going to use the xml file called 
**haarcascade_frontalface_default.xml**, which you can grab from my repo or download from official OpenCV repo [here](https://github.com/opencv/opencv/tree/master/data/haarcascades).


### Parameters for face detection
cascadeClassifier.detectMultiScale(image, scaleFactor, minNeighbors, minSize, maxSize)  
1. **scaleFactor**: Since some faces may be closer to the camera, they would appear bigger than other faces in the background, the scale factor compensates for this
specifying how much the image size is reduced at each image scale. The model has a fixed size defined during training in the haarcascade_frontalface_default.xml file.
By rescaling the input image, you can resize a larger face to a smaller one,making it detectable by the algorithm. Value: 1.1 - 1.4, **Small**-> algorithm will be
slow since it is more thorough, **High**-> faster detection with the risk of missing some faces altogether.  
2. **minNeighbors**: Specifying how many neighbors each candidate rectangle should have to retain it, Value interval: ~ 3-6, Higher values-> less detections but with
higher quality.  
3. **minSize**: Objects smaller than this are ignored,	we can specify what is the smallest object we want to recognize, 30x30 is the standard.  
4. **maxSize**: Objects larger than that are ignored.


### Checking the results
We will try to detect the faces on an [image](https://www.needsomefun.net/best-pink-floyd-photos/) of the Pink Floyd band. At first we will try with commonly used values, scaleFactor=1.1, minNeighbors=5, minSize=(30, 30).
![Reult1](/PinkFloydResult1.jpg "first result")
As we can see 5 faces have been detected and that one with smaller window size is not face. Let increase the size of minSize=(70, 70).
![Reult2](/PinkFloydResult2.jpg "second result")
