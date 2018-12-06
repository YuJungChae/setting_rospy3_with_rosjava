Guide to use python3.5 and rosjava. 

# Environment

- OS: Ubuntu 14.04

- ROS: indigo

- Python: 2.7 and  3.5

  ```
  $ python -V
  $ python3 -V
  ```



# ROS Kinectic Installation

```
wget https://raw.githubusercontent.com/oroca/oroca-ros-pkg/master/ros_install.sh && chmod 755 ./ros_install.sh && ./ros_install.sh catkin_ws indigo
```

# JAVA 1.8 Installation

```
$ sudo add-apt-repository ppa:webupd8team/java
$ sudo apt-get update
$ sudo apt-get install oracle-java8-installer
$ java -version
```



# ROS JAVA Installation

```
$ sudo apt-get install ros-indigo-catkin ros-indigo-rospack python-wstool
$ mkdir -p ~/rosjava/src
$ wstool init -j4 ~/rosjava/src https://raw.githubusercontent.com/rosjava/rosjava/indigo/rosjava.rosinstall
$ source /opt/ros/indigo/setup.bash
$ cd ~/rosjava
# Make sure we've got all rosdeps and msg packages.
$ rosdep update
$ rosdep install --from-paths src -i -y
$ catkin_make


$ cd ~/rosjava/src
# Merging a rosinstall set
$ wstool merge https://raw.githubusercontent.com/me/rosinstalls/master/my_custom_msg_repos.rosinstall
# Applying a single repo
$ wstool set my_custom_msgs --git https://github.com/me/my_custom_msgs --version=indigo-devel
# Build
$ cd ~/rosjava
$ catkin_make
```

[1]: http://wiki.ros.org/rosjava/Tutorials/kinetic/Source%20Installation



# PIP Installation

```
$ sudo apt install python-pip
$ sudo apt install python3-pip
```

# PYTHON3.5 Installation

```
$ sudo add-apt-repository ppa:jonathonf/python-3.5 
$ sudo apt-get update 
$ sudo apt-get install python3.5
```

# PYTHON3.5 Package Installation For ROS

```
$ sudo apt-get install libyaml-dev libpython3.5-dev
$ sudo python3.5 -m pip install PyYAML
$ sudo python3.5 -m pip install rospkg catkin_pkg
$ sudo python3.5 -m pip install netifaces
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

