# AR_FinalProject
Final Project for the Augmented Reality Class: Raycasting a user's gaze captured by one webcam to create a virtual projection in a world view of a second webcam

Motivation: The motivation behind this works comes from developing a driving system that can detect the quality of driving of a person and provide
a report on the quality of driving in the end of a drive. Such a system will be very useful for individuals who want to improve their driving skills. 
Many systems developed to teach driving to neurodiverse population generally rely on driving simulators but their generalizability to on-road driving is not 
known. Hence, developing a system that could record the quality of real-life driving will provide with more accurate feedback.

One component of such a system is to track where the user is looking while driving i.e., did the user look at the stop sign and stopped the vehicle 
accordingly? For capturing the reigistration of the stop sign, there needs to be a device or set of devices that capture the eye gaze of the driver and creates a 
projection to see where the driver is looking. 

For the sake of simplicity, we hope to utilize not more than two webcams with a fixed relative position (one pointing to the road and the other pointing to the user's face) to capture
the projection of the user's gaze in world view. A similar system was developed by Mayer et al. [1] who utilized the front camera of an iPhone to capture the head of a user and raycast the 
estimated head direction vector into the 3D world space captured by the back camera. This work adapts Mayer et al. approach and tries to recreate it using two fixed webcams. 
Once the projected virtual object is added to the scene in the camera that views real world, its occlusion with objects in real world can be used as an indicator of whether 
the user looked at a certain object or not. 

Current goals
1. The paper [1] uses AR Kit to project the vector from the front camera to the view of rear camera. I am currently trying to figure out how that can be achieved with webcams.
Unity has been previously used to raycart between a main camera and a secondary camera in a virtual environment thus it is promising to find such a method for mapping from
one webcam to another. 
2. Detect facial landmarks (using dlib or OpenCV) that can most accurately estimate eye gaze (as opposed to the bridge of the nose used for the estimation of eye gaze in the paper).
3. A target image registered in Vuforia will be used as a target for gaze. A voice output will be released whenever the protected VR ray in the second camera will collide with the target object in the view of this camera.

Future goals
1. Check the accuracy of the system as it both the cameras are moved while their relative position (with respect to eachother) is fixed to simulate how the cameras installed
in a car will move 
2. Register road components like pedestrians, stop signs, and traffic signals etc. and see if the virtual project collides with any of them or not. Provide audio feedback if the user misses any of the targets 


References:
[1] Mayer, S., Laput, G., & Harrison, C. (2020, April). Enhancing mobile voice assistants with worldgaze. In Proceedings of the 2020 CHI Conference on Human Factors in Computing Systems (pp. 1-10).
