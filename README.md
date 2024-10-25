# Laboratory 4

The repository contains an Docker description and files required for the laboratory 4 in the course of Autonomous Robots at the Universidad de Zaragoza.

## Download

For downloading this repository you have to use

```
git clone https://github.com/dvdmc/arob_lab4_docker --recursive
```
**Note:** The recursive flag will also pull from the subrepository.

## Instructions

To run the Docker you can just execute:

```
xhost + # this will enable gazebo visualization
docker compose up -d # use the -d for keep the container alive in background
```

The image will build if it is not already built. Then, an instance of the container is running now with the display configuration set and the directory `pXX_arob_lab4` mounted on `/root/catkin_ws/src/pXX_arob_lab4_drones`. Now you can run as many terminals as needed with:
 ```
 docker exec -it aroblab4 /bin/bash
 ```

We don't recommend running more than one terminal but rather start a `tmux` session with:

 ```
 tmux new -t arob4
 ```
 
 This terminal server also allows multiplexation of panes as `terminator` and, additionally, session persistence (the tmux session will stay up unless you close it or stop the Docker). However, the learning curve is steeper. Here is a [cheat sheet](https://tmuxcheatsheet.com/). For selecting text for copying, you have to keep the `shift` key pressed.

For stopping the container run on the **repo** root folder (not inside the container):
 ``` 
 xhost -
 docker compose down
 ```
 ## Instructions for the exercises
 
 1. You can modify the code outside of Docker with VSCode and build/run inside the Docker. The disadvantage is that you won't have the linter with the ROS C++ libraries.
 
 > **NOTE:** If you are executing on Windows, there are different things you might have to do in the docker-compose.yml:
 > 1. Install XLaunch and configure it correctly: dissable access control (check a box) and, maybe deactivate "Native opengl" if there are problems with OpenGL inside the Docker. 
 >
 > 2. The volumes might have to be specified with global path.
 >
 > 3. Modify the following line in the docker-compose.yml:  `DISPLAY: host.docker.internal:0.0`
