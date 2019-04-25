Guide to use python3.5 and rosjava. 

# Environment

- OS: Ubuntu 16.04

- ROS: kinectic

- Python: 2.7 and  3.5

  ```
  $ python -V
  $ python3 -V
  ```



# ROS Kinectic Installation

```
wget https://raw.githubusercontent.com/ROBOTIS-GIT/robotis_tools/master/install_ros_kinetic.sh && chmod 755 ./install_ros_kinetic.sh && bash ./install_ros_kinetic.sh 
```

[1]: https://cafe.naver.com/openrt/14575



# JAVA 1.8 Installation

```
$ sudo add-apt-repository ppa:webupd8team/java
$ sudo apt-get update
$ sudo apt-get install oracle-java8-installer
$ java -version
```



# ROS JAVA Installation

```
$ sudo apt-get install ros-kinetic-catkin ros-kinetic-rospack python-wstool openjdk-8-jdk
$ mkdir -p ~/rosjava/src
$ wstool init -j4 ~/rosjava/src https://raw.githubusercontent.com/rosjava/rosjava/kinetic/rosjava.rosinstall
$ source /opt/ros/kinetic/setup.bash
$ cd ~/rosjava
# Make sure we've got all rosdeps and msg packages.
$ rosdep update
$ rosdep install --from-paths src -i -y
$ catkin_make

$ cd ~/rosjava/src
# Merging a rosinstall set
$ wstool merge https://raw.githubusercontent.com/me/rosinstalls/master/my_custom_msg_repos.rosinstall
# Applying a single repo
$ wstool set my_custom_msgs --git https://github.com/me/my_custom_msgs --version=kinetic-devel
# Build
$ cd ~/rosjava
$ catkin_make
```

[2]: http://wiki.ros.org/rosjava/Tutorials/kinetic/Source%20Installation



# PIP Installation

```
$ sudo apt install python-pip
$ sudo apt install python3-pip
```



# ROS PYTHON3 Installation

```
$ sudo apt-get install python3-yaml
$ sudo pip3 install rospkg catkin_pkg
$ sudo pip3 install netifaces
```

​	

# Test

- beginner_tutorial: copy to catkin_ws/src

- rosjava_catkin_package_a package : copy to rosjava/src

- Test 1: send a message from the talker(beginner_tutorial) to listener(rosjava_catkin_package_a package)

  ```
  $ rosrun beginner_tutorials talker.py
  $ cd rosjava
  $ src/rosjava_catkin_package_a/my_pub_sub_tutorial/build/install/my_pub_sub_tutorial/bin/my_pub_sub_tutorial com.github.rosjava.rosjava_catkin_package_a.my_pub_sub_tutorial.Listener
  ```

- Test2: send a message from the listener(rosjava_catkin_package_a package) to talker(beginner_tutorial) 

  ```
  $ rosrun beginner_tutorials listener.py
  $ cd rosjava
  $ src/rosjava_catkin_package_a/my_pub_sub_tutorial/build/install/my_pub_sub_tutorial/bin/my_pub_sub_tutorial com.github.rosjava.rosjava_catkin_package_a.my_pub_sub_tutorial.Talker
  ```




# Appendix

## Upgrade pip

```
$ sudo pip install --upgrade pip
$ sudo pip3 install --upgrade pip
```

## Errors: 

```
Error Message:
**its parent directory is not owned by the current user and the cache has been disabled. Please check the permissions and owner of that directory.

Solution: add "-H" option
ex, sudo -H pip3 install --upgrade pip
```


```
Error Message:
**Package oracle-java8-installer is not available, but is referred to by another package.

Solution: 
sudo apt-get install aptitude
sudo aptitude install default-jre default-jre-headless

```
