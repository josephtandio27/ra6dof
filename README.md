# Simulate 6 dof robotic arm in Gazebo Harmonic with ROS2 Jazzy.
## References:

## Requirements
- ros2_control
- ros2_controllers
- gz_ros2_control

## Command
### Gripper
ros2 action send_goal /gripper_action_controller/gripper_cmd control_msgs/action/ParallelGripperCommand "{command: {name: [gripper_controller], position: [-0.7], effort: [2.0]}}" --feedback
### Robot Arm
ros2 topic pub --once /arm_controller/joint_trajectory trajectory_msgs/msg/JointTrajectory "{joint_names: ['link1_to_link2', 'link2_to_link3', 'link3_to_link4', 'link4_to_link5', 'link5_to_link6', 'link6_to_flange'], points: [{positions: [-1.345, -1.23, 0.264, -0.296, 0.389, -1.5], time_from_start: {sec: 3, nanosec: 0}}]}"

