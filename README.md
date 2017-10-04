# mocap_optitrack
ROS nodes for working with the NaturalPoint Optitrack motion capture setup

## How to verify axis configuration
1. Set OptiTrack Motive to stream data for some rigid body (make sure it has Rigid Body ID 1).
2. If you want to reset the orientation of the rigid body:
    * Place the rigid body in the motion capture area, so that the body axes of your rigid body align with the axes of the motion capture system.
    * Select the rigid body in OptiTrack Motive and press "Reset To Current Orientation".
4. Start the ROS node: `roslaunch mocap_optitrack mocap.launch`
5. Display live pose data: `rostopic echo /Robot_1/pose`
6. Move the rigid body around and make sure `position.<x/y/z>` are correct according to the motion capture coordinate system.
7. Start `rqt_pose_view`:
    * Run `rqt`.
    * Plugins &rarr; Visualization &rarr; Pose View.
    * Plugins &rarr; Topics &rarr; Topic Monitor.
    * Drag and drop the topic `/Robot_1/pose` into the Pose View window.
8. Rotate the body around all three axes and make sure the rotation and orientation is as expected.
