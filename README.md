# Video Tracking Kinematics

This Python Notebook allows you to perform a video tracking of an object and obtain its kinematic information such as displacement, speed and acceleration.

## 🔰 How does it work?
- The code uses [OpenCV library](https://opencv.org/)
- User must upload the video.
- Some information is obtained from the video (FPS, duration, resolution)
- The first frame of the video is extracted in order to create a reference line to convert the pixel data into measurement units (i.e. cm).
- The reference line is created with a mouse_callback event where the pixel coordinates of the start and end point of the reference line are used for the unit conversion. For a correct measure, the video must have a reference guide such as a flexometer or ruler. The user must be knonw the real distance (cm, inches, etc) of the reference line. The current code is based on X direction but it could be modify to Y direction.

 <img src = "https://github.com/alejo1630/video_tracking/blob/main/Image_Readme/1.png" width="500">

- In the next step, the user must create a bounding box around the object to be tracked.

<img src = "https://github.com/alejo1630/video_tracking/blob/main/Image_Readme/2.png" width="500">

- After creating the bounding box the tracking process will start. Whenever the program succeeds in tracking, a green message "Tracking" will appear, otherwise a red message "Lost" will be displayed.

<img src = "https://github.com/alejo1630/video_tracking/blob/main/Image_Readme/3.png" width="500">

- When the video ends, all the kinematics of the object's movement are calculated. 
  - Displacement
  - Speed
  - Acceleration
- Based on the quality and FPS of the video, the data could have some noise. This is treated by two methods
  - [Savitzky–Golay filter](https://en.wikipedia.org/wiki/Savitzky%E2%80%93Golay_filter)
  - [Spline Interpolation](https://en.wikipedia.org/wiki/Spline_interpolation)
- The results obtained are compared with the video data processed in the [Tracker software](https://physlets.org/tracker/)

## 🔶 What is next?
- Improve the accuracy of the kinematics data.
- Perform the same analysis for live videos.
