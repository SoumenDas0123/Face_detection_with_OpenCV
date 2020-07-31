# Face_detection_with_OpenCV

	We are going to detect the faces in an image with OpenCV which is a very popular library for computer vision. When it comes to detecting face, machine 
doesnt just detect the face in a straight forward way, because it requires lots of small features and patterns to be matched. The task of identifying face are broken
down into lots of smaller jobs where it tries to match those simple individual patterns and features present generally in a human face. OpenCV uses machine learning
classification algorithms to do that.
	There will be thousands of smaller classification tasks which need to be performed on every parts of the image, which makes the preocess computationally very
heavy. For turn around OpenCV uses cascade classifier, where it doesnt try to search for all the patterns at a time, as we know that most of the parts of an image
wont have faces. It serachs for the patterns in several stages,where it intensifies the classification jobs for facal features, only when it passes the previous
stages of roughly and quickly jobs.
	OpenCV has these cascade classifers in terms of XML files, which we can use as pretrained features or patterns. Here we are going to use the xml file called 
haarcascade_frontalface_default.xml
PARAMETERS FOR FACE DETECTION

 cascadeClassifier.detectMultiScale(image, faceDetections, scaleFactor, minNeighbors, flags, minSize, maxSize)

1.) scaleFactor: Since some faces may be closer to the camera, they would appear bigger
		 than other faces in the background -> the scale factor compensates for this

			Specifying how much the image size is reduced at each image scale

			The model has a fixed size defined during training: in the haarcascade_frontalface_alt.xml file !!!
			By rescaling the input image, you can resize a larger face to a smaller one,
				 making it detectable by the algorithm

		Value: 1.1 - 1.4
			Small -> algorithm will be slow since it is more thorough
			High -> faster detection with the risk of missing some faces altogether

 2.) minNeighbors: specifying how many neighbors each candidate rectangle should have to retain it
 			Value interval: ~ 3-6
 				Higher values -> less detections but with higher quality !!!

 3.) flags: kind of a heuristic
 		Reject some image regions that contain too few or too much edges
 			 and thus can not contain the searched object

 4.) minSize: objects smaller than that are ignored !!!
 			We can specify what is the smallest object we want to recognize
 					[30x30] is the standard

 5.) maxSize: objects larger than that are ignored !!!
