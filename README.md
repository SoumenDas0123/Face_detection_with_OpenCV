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

### Checking the results
