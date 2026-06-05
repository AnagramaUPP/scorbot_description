# SCORBOT ER 4pc Description Package for ROS 2 Jazzy

## Description

This package contains the URDF model of the **SCORBOT ER 4pc** industrial robot developed for ROS 2 Jazzy.

The package includes:

* Robot kinematic structure based on the manufacturer specifications.
* STL meshes for visualization.
* URDF description of links and joints.
* Joint limits according to the robot technical manual.
* Mass, center of mass, and inertia properties for each link.
* RViz configuration files.
* Launch files for visualization using:

  * `robot_state_publisher`
  * `joint_state_publisher_gui`
  * `rviz2`

The purpose of this package is to provide a digital representation of the SCORBOT ER 4pc robot for visualization, kinematic analysis, dynamic modeling, and future integration with Gazebo and ros2_control.

---

## Robot Specifications

| Parameter          | Value                         |
| ------------------ | ----------------------------- |
| Robot Type         | Vertical articulated robot    |
| Degrees of Freedom | 5 rotational joints + gripper |
| Maximum Reach      | 610 mm                        |
| Feedback           | Optical encoders              |
| Actuators          | DC servo motors               |
| Transmission       | Gears and timing belts        |

### Joint Ranges

| Joint | Description       | Range            |
| ----- | ----------------- | ---------------- |
| J1    | Base rotation     | 310°             |
| J2    | Shoulder rotation | +130° / -35°     |
| J3    | Elbow rotation    | ±130°            |
| J4    | Wrist pitch       | ±130°            |
| J5    | Wrist roll        | ±570° electrical |

---

## Package Structure

```text
scorbot_description/
├── config/
├── launch/
│   └── display.launch.py
├── meshes/
│   ├── base_link.stl
│   ├── link_1.stl
│   ├── link_2.stl
│   ├── link_3.stl
│   ├── link_4.stl
│   └── link_5.stl
├── rviz/
│   └── scorbot.rviz
├── urdf/
│   └── scorbot.urdf
└── CMakeLists.txt
```

---

## Dependencies

ROS 2 Jazzy packages:

```bash
sudo apt install ros-jazzy-rviz2
sudo apt install ros-jazzy-joint-state-publisher-gui
sudo apt install ros-jazzy-robot-state-publisher
```

---

## Build

```bash
cd ~/ros2_ws

colcon build --packages-select scorbot_description

source install/setup.bash
```

---

## Run

```bash
ros2 launch scorbot_description display.launch.py
```

---

## References

### Manufacturer Documentation

Intelitek / Eshed Robotec

SCORBOT ER 4pc User Manual

Available at:

https://www.intelitek.com

---

### Technical Specifications

The kinematic limits, gear ratios, actuator specifications, and mechanical characteristics were obtained from the official SCORBOT ER 4pc documentation and technical manuals.

Additional educational references consulted:

https://www.studocu.com/es-mx/document/instituto-tecnologico-de-toluca/robotica/manual-de-usuario-4pc-guia-completa-y-especificaciones-del-robot/125478023

---

## Future Work

* Gazebo simulation.
* ros2_control integration.
* Dynamic validation.
* Inverse kinematics implementation.
* Trajectory generation.
* Digital twin development.
* EMG-based teleoperation.
* Reinforcement learning experiments.

---

## Author

Dr. Mitchell Angel Gomez Ortega

Professor and Researcher

Universidad Politécnica de Pachuca (UPP)



