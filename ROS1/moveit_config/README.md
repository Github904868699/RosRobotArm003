# rosrobotarm003_moveit_config

This package bundles the updated URDF model for the robot arm together with controller gain parameters suitable for the ROS1 MoveIt project.

## Contents
- `urdf/robot.urdf`: robot description exported from SolidWorks and provided in the `URDF` folder.
- `config/joint_gains.yaml`: joint-wise parameters requested for the new control definitions.
- `launch/load_robot.launch`: helper launch file to push the URDF and gain parameters into the ROS parameter server.

## Usage
1. Add this package to your ROS1 workspace (e.g., `catkin_ws/src`).
2. Build the workspace with `catkin_make`.
3. Launch the configuration to load the robot description and gain parameters:
   ```bash
   roslaunch rosrobotarm003_moveit_config load_robot.launch
   ```

The gains follow the requested values: position gains (`p_int`/`kp_int`) are set to `0`, velocity gains (`v_int`/`kd_int`) to `10`, and torque limit (`t_int`) to `10` for each joint.
