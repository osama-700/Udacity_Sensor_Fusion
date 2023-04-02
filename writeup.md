# Writeup: Track 3D-Objects Over Time

Please use this starter template to answer the following questions:

### 1. Write a short recap of the four tracking steps and what you implemented there (filter, track management, association, camera fusion). Which results did you achieve? Which part of the project was most difficult for you to complete, and why?

Step 1: Implement Extended Kalman Filter (EKF) by finding out F and Q using a matrix, then use it to find out the predicted car position, then update the car position (P and X value).

Step 2: Implement a track management where each vehicle has a score and it will decrease if the sensor did not find that vehicle and increase if the sensor finds out the vehicle, then the vehicle will be removed if the track score reaches less than 0.05 and finally, it will indicate if it confirmed or tentative depends on the track score and confirmed_threshold.

Step 3: Implement an association matrix where it will loop over the measurement and assign each measurement to the corrected vehicle by using  Mahalanobis Distance (MHD).

Step 4: Implement nonlinear camera measurement model by Implementing in_fov which is a function for checking if the input state of an object can be seen by the sensor and return either a true or false value, then implement get_gx function for the camera so at the end they will be 2 different sensors for car tracking.

Each step was having some difficulties to figure out how to solve but now I think I am capable to do any project like this  


### 2. Do you see any benefits in camera-lidar fusion compared to lidar-only tracking (in theory and in your concrete results)? 
Yeah, I do. There is much difference when using lidar and camera together because the camera is better for classification and identifying if the object is a vehicle or something else. This project shows there is a significant improvement in the accuracy when finishing implementing the final step


### 3. Which challenges will a sensor fusion system face in real-life scenarios? Did you see any of these challenges in the project?
I think the camera has less accuracy compared to lidar during the night if you try to estimate distance so lidar is used to cover the error and that can easily be seen in the project that lidar has better accuracy than the camera


### 4. Can you think of ways to improve your tracking results in the future?
There is a way might reduce the error by optimizing the code like implementing Joint Probabilistic Data Association (JPDA) or Global Nearest Neighbor (GNN) and tuning parameters or reducing RMSE



Step 1 Implement EKF to track a single real-world target with lidar measurement input over time!

code on 
student/objdet_detect.py

image proof on
img/Step1_pic.png


Step 2 Implement the track management to initialize and delete tracks, set a track state and a track score.

code on 
student/trackmanagement.py

image proof on
img/Step2_pic.png

Step 3 Implement a single nearest neighbor data association to associate measurements to tracks.

code on 
student/association.py

image proof on
img/Step3_pic.png


Step 4 Implement the nonlinear camera measurement model.

code on 
student/measurements.py

image proof on
img/Step4_pic.png

