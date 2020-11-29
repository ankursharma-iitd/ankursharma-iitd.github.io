---
title: "Augmented Reality"
date: 2019-10-30
tags: [computer vision, image processing]
header:
  image: "/images/augmented-reality/main2.jpg"
excerpt: "Computer Vision, Image Processing"
mathjax: "true"
---

# Objective
![alt]({{ site.url }}{{ site.baseurl }}/images/augmented-reality/multiple-objects.gif)

## Brief Description of the approach followed
1. Camera Calibration
---
&nbsp;&nbsp;&nbsp;&nbsp;First, we recorded a video of a 9x7 chessboard using a laptop’s webcam. Using multiple frames of this video, we found out 8x6 chess board in each frame and its corners with the help of OpenCV library. Then we refined the corners to subpixels & finally found the ​intrinsic camera matrix​, and ​distance coefficients​ using OpenCV library functions.

![alt]({{ site.url }}{{ site.baseurl }}/images/augmented-reality/chessboard.png)

2. Visual Markers
---
We experimented with multiple visual markers to use as planar template objects.
* 6x6 ArUco markers
![alt]({{ site.url }}{{ site.baseurl }}/images/augmented-reality/aruco.png)
* Simple playing cards
![alt]({{ site.url }}{{ site.baseurl }}/images/augmented-reality/card.png)


3. Marker Detection
---
* Based on the template images, the task was to now detect the markers in a video which was pre-recorded. 
* This was done by first finding feature descriptors like SIFT, ORB, SURF etc. and then finding matches between each frame and template image. 
* Then homography is estimated using matching points which were refined using `RANSAC` and `Lowe’s test`.

4. Rendering Object On Marker
---
* After finding the homography, we find the ​projection matrix. 
* We then use this projection matrix to render an object (read from a `.obj` file) on to the frame of the video.
![alt]({{ site.url }}{{ site.baseurl }}/images/augmented-reality/joker.gif)
![alt]({{ site.url }}{{ site.baseurl }}/images/augmented-reality/aruko-2.gif)

5. Moving a Marker Until Hitting Another
---
* Now, the first time we observe a marker of ArUco id=1. We place the object there, saving the ​projection matrix​ and start translating the object in one direction parallel to the plane. 
* This is achieved by finding $$P' = P \times M$$ where ​ $$P'$$ and $$P$$ are the new & old projection matrix respectively. $$M$$ corresponds to the movement matrix where $$M = ​[I \mid T]$$ and $$T = [0, x, 0]^{T​}$$. Here, $$x$$ is incremented in each frame based upon a rate.
* In order to stop the car, we observe that the car’s front corner pixel, $$p$$ in the other frame’s coordinates. We have the car’s extrinsic matrix $$S$$, the wall’s extrinsic matrix $$E$$. Since, $$S = E \times X \rightarrow X = E^{-1}S$$. Then, $$p$$'s coordinate in wall's frame of reference can be given by $$p_{W} = X \times p$$.
* Thus, we check ​$$(X \times p)$$’​ s $$z$$-coordinate to see when it would hit the plane. When it does so, we stop the car from translating further.
![alt]({{ site.url }}{{ site.baseurl }}/images/augmented-reality/racing-car-simple.gif)
![alt]({{ site.url }}{{ site.baseurl }}/images/augmented-reality/racing-car-slope.gif)
<!-- ![alt]({{ site.url }}{{ site.baseurl }}/images/augmented-reality/car.png) -->  

6. Projecting multiple objects on the same scene
---
![alt]({{ site.url }}{{ site.baseurl }}/images/augmented-reality/multi.png)

Other results have been mentioned in this [link](https://drive.google.com/open?id=1-XKVTrERD0bWK_0W7Gpy_oHIIqseLNH1) along with a comprehensive report.