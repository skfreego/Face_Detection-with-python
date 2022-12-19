# Face_Detection-with-python
Image detection and Video(Webcam)

### Face Detection
	Face detection is the process of detecting a face in an image or video.

#### OpenCV
	pip install opencv-python
   OpenCV is the most popular library for computer vision. Originally written in C/C++, it now provides bindings for Python.4
   OpenCV uses machine learning algorithms to search for faces within a picture. Because faces are so complicated, there isn’t one simple test that will tell you if it found a face or not. Instead, there are thousands of small patterns and features that must be matched. The algorithms break the task of identifying the face into thousands of smaller, bite-sized tasks, each of which is easy to solve. These tasks are also called classifiers.
   OpenCV is a Library which is used to carry out image processing using programming languages like python. This project utilizes OpenCV Library to make a Real-Time Face Detection using your webcam as a primary camera.

Following are the requirements for it:- 
    Python 2.7
    OpenCV
    Haar Cascade Frontal face classifiers


## Face Detection : IMAGE

What’s a cascade?
     The best answer can be found in the dictionary: “a waterfall or series of waterfalls.”
 Like a series of waterfalls, the OpenCV cascade breaks the problem of detecting faces into multiple stages. For each block, it does a very rough and quick test. If that passes, it does a slightly more detailed test, and so on. The algorithm may have 30 to 50 of these stages or cascades, and it will only detect a face if all stages pass. 


Understanding the Code
	We’ll use the test.jpg image as well as the default cascade for detecting faces provided by OpenCV.	
	create the cascade and initialize it with our face cascade. This loads the face cascade into memory so it’s ready for use. Remember, the cascade is just an XML file that contains the data to detect faces.
	Here we read the image and convert it to grayscale. Many operations in OpenCV are done in grayscale.
	This function detects the actual face and is the key part of our code
		The detectMultiScale function is a general function that detects objects. Since we are calling it on the face cascade, that’s what it detects. 
		The first option is the grayscale image.
		The second is the scaleFactor. Since some faces may be closer to the camera, they would appear bigger than the faces in the back. The scale factor compensates for this.
	The function returns a list of rectangles in which it believes it found a face. 
	This function returns 4 values: the x and y location of the rectangle, and the rectangle’s width and height (w , h).
		We use these values to draw a rectangle using the built-in rectangle() function.
	we display the image and wait for the user to press a key.

"Face detection using Haar cascades is a machine learning based approach where a cascade function is trained with a set of input data. OpenCV already contains many pre-trained classifiers for face, eyes, smiles, etc.. Today we will be using the face classifier."


A few things to note:
	The detection works only on grayscale images. So it is important to convert the color image to grayscale. (line 8)
    
	detectMultiScale function (line 10) is used to detect the faces. It takes 3 arguments — the input image, scaleFactor and minNeighbours. scaleFactor specifies how much the image size is reduced with each scale. minNeighbours specifies how many neighbors each candidate rectangle should have to retain it. You can read about it in detail here. You may have to tweak these values to get the best results.
    
	faces contains a list of coordinates for the rectangular regions where faces were found. We use these coordinates to draw the rectangles in our image.



## Face Detection : Webcam


Pre-requisites

    OpenCV installed (see the previous blog post for details)
    A working webcam

Understanding the code

	 We are creating a face cascade, as we did in the image example.
	 video_capture = cv2.VideoCapture(0)
		This line sets the video source to the default webcam, which OpenCV can easily capture.	
	 Here, we capture the video. The read() function reads one frame from the video source, which in this example is the webcam. This returns:
		The actual video frame read (one frame on each loop)
    		A return code
	 The return code tells us if we have run out of frames, which will happen if we are reading from a file. This doesn’t matter when reading from the webcam, since we can record forever, so we will ignore it.
	 #### Stop if escape key is pressed
