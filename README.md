# Quadric SLAM With Probabolistic DataAssociation#

## Attention: This project is under construction, so it may NOT work well. Contact us freely if you have questions.

This code contains a basic implementation for Quaqric SLAM. Given RGB and 2D object detection, the algorithm detects quadrics from several frames then formulate an object SLAM to optimize both camera pose and qadric poses. 

**Authors:** [tiev-tongji]

**Related Paper:**

* **CubeSLAM: Monocular 3D Object SLAM**, IEEE Transactions on Robotics 2019, S. Yang, S. Scherer  [**PDF**](https://arxiv.org/abs/1806.00557)

* **QuadricSLAM: Dual Quadrics From Object Detections as Landmarks in Object-Oriented SLAM**,  IEEE Robotics and Automation Letters ( Volume: 4 , Issue: 1 , Jan. 2019 ), Lachlan Nicholson, Michael Milford, Niko Sünderhauf 

* **Probabilistic Data Association for Semantic SLAM**, [**PDF**]http://erl.ucsd.edu/ref/Bowman_SemanticSLAM_ICRA17.pdf

* **Multimodal Semantic SLAM with Probabilistic Data Association**, [**PDF**]https://marinerobotics.mit.edu/sites/default/files/doherty_icra2019_revised.pdf
## Installation

### Prerequisites
This code contains several ros packages. We test it in **ROS indigo/kinetic/Melodic, Ubuntu 14.04/16.04/18.04, Opencv 2/3**. Create or use existing a ros workspace.
```bash
mkdir -p ~/cubeslam_ws/src
cd ~/cubeslam_ws/src
catkin_init_workspace
git clone git@github.com:shichaoy/cube_slam.git
cd cube_slam
```

### Compile dependency g2o
```bash
sh install_dependenices.sh
```

### Compile
```bash
cd ~/cubeslam_ws
catkin_make -j4
```

## Running #
```bash
source devel/setup.bash
roslaunch object_slam object_slam_example.launch
```
You will see results in Rviz. Default rviz file is for ros indigo. A kinetic version is also provided.

## Change Log

### v0.2

2019/07/12

- Finished quadric detector

- Update README

### v0.1

2019/07/09

- Finished basic structure

- Update README

### v0.0

2019/07/07

- Initial Commit

## TODO List
- [X] Generate and update quadrics (Quadric_landmark.quadric_detection().
- [ ] Score quadrics.
- [ ] Data Association.
- [ ] Visualization the quadrics and camera pose(publish_all_poses()).
- [ ] Detect online with yolo.
- [ ] Offline mode.
- [X] Find the algorithm to determine the ID of vertex and edge.

