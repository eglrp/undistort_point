# Undistort Points
Computing distorted image coordinates can be done simply by multiplying/adding distortion coefficient to the undistorted coordinates (refer to the previous repository [retained_undistorted_image](https://github.com/stanathong/retained_undistort_image)). However, the reverse process i.e. computing undistorted image coordinates from the distorted (original) image coordinates, given the camera's intrinsics, requires a non-linear optimisation.<br><br>
The __OpenCV__ library has a function `cv::undistortPoints` to compute the undistorted coordinates easily. In this repository, we do this the hard way (?) through the use of the [Ceres Solver](http://ceres-solver.org/) to compute the undistorted coordinates by non-linearly minising the error between the input distorted coordinates and the computed distorted coordinates.<br>
