# Person Counter Using Open Cv and MobileNet-SSD (Object Detection and Object Tracking)

![image](https://user-images.githubusercontent.com/45294902/125672937-3c839946-b4e0-4145-b912-d696c00bc8b6.png)



1. Libraries used - OpenCv, Dlib, imutils, numpy

The following program uses two techniques to count people present walking in the video.
1. Object Detection
2. object Tracking


Firstly a more expensive model is run for every N frames to detect people in the current frame. The bounding box and centroid coordinates are stored for each of these detected persons. Simultaneously, a less expensive object tracking model is run for every other frame, it tries to associate the objects in that frame with the older objects by minimizing the distances between the centroids. 

The associated objects get a unique ID which stays for a maximum of D frames as specified in the code, if the program is not able to track the object, we deregister the object.

Lastly we draw out a vertical line on the video frames. This is to ensure if the object's current position is ahead of the vertical line or behind it. This is with the relative direction of the object with refrence to its old centroid will determine if the object is moving towards left or right.
