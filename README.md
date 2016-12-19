# camera_LAM_ros
Localization of camera in 3D space for more accurate tracking of objects in space. Integrated with ROS and built on @ecdeng branch of OpenFace and OpenCV 3.

Built on ARUCO (https://sourceforge.net/projects/aruco/files/) and http://www.uco.es/investiga/grupos/ava/node/57

Goals: 
Using fiducial markers in a 3D space we hope to build a system that can return the 6-dof location and position of a camera in that space. This would allow for much more robust global vision systems to be deployed in "hostile" environments that may cause movement during or between data collections. By removing the assumptions that are currently being made about fixed position and location of cameras we can provide much cleaner data to be built on. 

The initial drive to pursuing this project is for work being done in the @interaction-lab and projecting gaze behavior from a human subject using OpenFace. Because the cameras in the deployment setup had the possibility of being moved there was a significant change of incorrect data from projecting gaze. The hope is that after giving the cameras the ability to localize in space, systems in the future can automatically account for movement and therefore decrease error in the data.

@Vadim 

The end goal of this system is to be able to use head poze (and/or gaze behaviors) to see where a person is looking. We know what the desktop setup looks like (i.e. the location and angle of the screen, position of the robot, location of the parent, etc.) and if we have the location and position of the camera in space we can transform gaze/head into a vector and determine where they are looking (error would stem COMPLETELY from OpenFace so we actually don't need to make this a distribution).

The first demo to run is have different areas on a flat surface (table) marked off and track gaze behavior/head pose using 2 cameras (one looking down from overhead and one from the tablet plane) and 1) Appropriately choose which camera to use (compare projected error--relatively straightforward) 2)Output which areas are being looked at at any one time.

The second demo to run is actually having the setup and determining which objects someone is looking at (Robot, Screen, Parent, or Nothing).

The third (and final) demo would be more of an experiment to explore the fidelity of this system and see if it would be possible to use the tablet webcam to actually determine where on the screen the child is looking or use the top webcam to determine whether or not the child is looking at the robot in the face.

TO-DO: 
1. Look over http://www.uco.es/investiga/grupos/ava/node/57 and see if you can get their system to work as a quick demo. Looks pretty straightforward and their known bugs shouldn't really effect our project. 
2. Their project is different in that they are building maps using these fiducials but we want to work back using a built map to localize ourselves. This is a nice solving problem for you to play with (a bit easier than most if not all 6-dof IK solvers so it would be a nice segway into that next thing). :) So using the map that you've already built trhough running the demo try to see if they have functionality (or build it yourself) for localizing the camera. 
3. Merging the camera localization with ROS--see if you can visualize this system in ROS/RViz. This can/should be done in two steps--first connect their stable ARUCO build with ROS and then your camera localization bit.
4. OpenFace Integration with (ROS + ARUCO). Reading in the vectors from OpenFace and using those to draw project rays from the eyes to table. 
5. Build towards demo(s) listed above.
n. We want to minimize the number of fiducials we would be using so ideally we can just use two markers with known location on the plane (relative size and distances from each other and other defining features (edges of table). Building a system like this would be the last thing and a nice thing to have but in no way is it required for now so just ignore this. 
