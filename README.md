# camera_LAM_ros
Localization of camera in 3D space for more accurate tracking of objects in space. Integrated with ROS and built on @ecdeng branch of OpenFace and OpenCV 3.

Built on ARUCO (https://sourceforge.net/projects/aruco/files/) and http://www.uco.es/investiga/grupos/ava/node/57

Goals: 
Using fiducial markers in a 3D space we hope to build a system that can return the 6-dof location and position of a camera in that space. This would allow for much more robust global vision systems to be deployed in "hostile" environments that may cause movement during or between data collections. By removing the assumptions that are currently being made about fixed position and location of cameras we can provide much cleaner data to be built on. 

The initial drive to pursuing this project is for work being done in the @interaction-lab and projecting gaze behavior from a human subject using OpenFace. Because the cameras in the deployment setup had the possibility of being moved there was a significant change of incorrect data from projecting gaze. The hope is that after giving the cameras the ability to localize in space, systems in the future can automatically account for movement and therefore decrease error in the data.

TO-DO: 
