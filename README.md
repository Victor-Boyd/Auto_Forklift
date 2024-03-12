# Auto-Forklift
**Use ros2 Humble on Ubuntu 22.04**  
**All dependencies are in the package.xml files of each package**

## Current state:
- When running `ros2 launch forklift_robot launch_sim.launch.py` the four wheel controller is not working because of the following error: 
```
[ros2-7] Could not contact service /controller_manager/load_controller
[ERROR] [ros2-7]: process has died [pid 40183, exit code 1, cmd 'ros2 control load_controller --set-state active forward_velocity_controller'].
[ros2-6] Could not contact service /controller_manager/load_controller
[ros2-8] Could not contact service /controller_manager/load_controller
[ERROR] [ros2-6]: process has died [pid 40181, exit code 1, cmd 'ros2 control load_controller --set-state active forward_position_controller'].
[ERROR] [ros2-8]: process has died [pid 40185, exit code 1, cmd 'ros2 control load_controller --set-state active joint_state_broadcaster'].

```
- Following that it will need some additional configuration. If you run `ros2 launch gazebo_simulation robot_sim.launch.py` you will see that the controller does not give the error but it is only set up for joystick control.  (This is a package copied from this video: https://www.youtube.com/watch?v=VX53gAXafUA and we are trying to integrate it into our package: forklift_robot)
  - If you can verify that it works with a joystick that is great as we currently have no way of testing it.

## Next milestones:
1. Working four wheel controller
2. Working sensors
3. Working Navigation and Slam