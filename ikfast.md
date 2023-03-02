# IKFast from OpenRAVE on Docker

This tutorial will cover installing IKFast on a Linux docker container with a Windows host. The steps should be similar with a Linux host.

---

The following MoveIt tutorials give an overview of the installation process:

MoveIt 2: https://moveit.picknik.ai/humble/doc/examples/ikfast/ikfast_tutorial.html

MoveIt 1 on ROS Noetic: https://ros-planning.github.io/moveit_tutorials/doc/ikfast/ikfast_tutorial.html

---

Install Docker Desktop: https://www.docker.com/products/docker-desktop/

From a terminal, run the following to install the docker image:
```
docker pull personalrobotics/ros-openrave
```
https://hub.docker.com/r/personalrobotics/ros-openrave

In Docker Desktop, run the newly pulled image. Docker Desktop will create a new container.
![image](https://user-images.githubusercontent.com/4022499/222288859-d42aa33c-a2f8-40be-a1b4-33bc1cb4cf6d.png)


To connect to the container from a terminal, run the following command in a terminal:
```
docker exec -it container_name /bin/bash
```
where `conainer_name` is the name of the container running the image.


There is an issue with the image where the version of `sympy` is wrong. As described in this tutorial, the version must be downgraded to `0.7.1`.
http://docs.ros.org/en/melodic/api/moveit_tutorials/html/doc/ikfast/ikfast_tutorial.html


First, insall pip
```
sudo apt update
sudo apt install python-pip
```
Then, downgrade `sympy`. For some reason, the usual method of running `pip install` doesn't work. Instead, download the correct version's tar file from https://pypi.org/project/sympy/0.7.1/#files.
After placing the file in the Docker image using the Docker desktop file manager, run
```
python -m pip install sympy-0.7.1.tar.gz
```


The IKfast documentation is found at http://www.openrave.org/docs/latest_stable/openravepy/ikfast/

You should be able to run the example provided in the documentation:
```
python `openrave-config --python-dir`/openravepy/_openravepy_/ikfast.py --robot=robots/barrettwam.robot.xml --baselink=0 --eelink=7 --savefile=ik.cpp --freeindex=2
```

The example was succesfull if you see a large file `ik.cpp` in your working directory.
