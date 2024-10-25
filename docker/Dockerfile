FROM osrf/ros:noetic-desktop-full

# Install dependencies
# python-tk is used by hector rotors GUI
# libtool libtool-bin is used by glog in mav_trajectory_generation
RUN apt-get update && apt-get install -y git tmux vim xterm curl ssh tree python3-catkin-tools python3-tk nano libtool libtool-bin gdb

RUN echo "set -g mouse on" > /root/.tmux.conf

# Create catkin workspace
RUN mkdir -p /root/catkin_ws/src/

