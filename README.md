# Fork of Isaac ROS Common for Catscanners

Contains dockerfiles and entrypoint additions for use with https://github.com/CatScanners/find-my-kitten

Running:

```
cd ${ISAAC_ROS_WS}/src/isaac_ros_common && ./scripts/run_dev.sh -i "ros2_humble.px4.zed.yolo.catscanners" -a "-v /usr/local/zed/resources/:/usr/local/zed/resources/"
```

Note that some directories/files may need a `sudo chown -hR admin <file>` or `sudo chmod 777 -R <file>` inside the container (probably some docker permission matter?)

Changes compared to upstream:
- Added docker/Dockerfile.catscanners
- Added docker/Dockerfile.px4
- Added docker/Dockerfile.yolo
- Added docker/Dockerfile.zed
- Added docker/Dockerfile.simulation
    - Currently overwrites base protobuf 26.0 with 12.4 to build PX4 from source. Need to configure to point to separate build
- Changed this README

This software contains source code provided by NVIDIA Corporation.

**Original README below**

# Isaac ROS Common

Dockerfiles and scripts for development using the Isaac ROS suite.

## Overview

The Isaac ROS Common
repository contains a number of scripts and Dockerfiles to help
streamline development and testing with the Isaac ROS suite.

<div align="center"><a class="reference internal image-reference" href="https://media.githubusercontent.com/media/NVIDIA-ISAAC-ROS/.github/main/resources/isaac_ros_docs/repositories_and_packages/isaac_ros_common/isaac_ros_common_tools.png/"><img alt="Isaac ROS DevOps tools" src="https://media.githubusercontent.com/media/NVIDIA-ISAAC-ROS/.github/main/resources/isaac_ros_docs/repositories_and_packages/isaac_ros_common/isaac_ros_common_tools.png/" width="auto"/></a></div>

Docker containers allow you to quickly set up a sensitive set of frameworks
and dependencies to ensure a smooth experience with Isaac ROS packages.
The Dockerfiles for x86_64 are based on the version 23.10 image from [Deep Learning
Frameworks Containers](https://docs.nvidia.com/deeplearning/frameworks/support-matrix/index.html).
On Jetson platforms, JetPack manages all of these dependencies for you.

Use of Docker images enables CI|CD systems to scale with DevOps work and
run automated testing in cloud native platforms on Kubernetes.

For solutions to known issues, see the [Troubleshooting](https://nvidia-isaac-ros.github.io/troubleshooting/index.html) section.

---

## Documentation

Please visit the [Isaac ROS Documentation](https://nvidia-isaac-ros.github.io/repositories_and_packages/isaac_ros_common/index.html) to learn how to use this repository.

---

## Latest

Update 2024-12-10: Refactored Dockerfiles
