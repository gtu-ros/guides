# ROS Communication with 2 Docker Container

1. Create new network

`docker network create ros-net`

2. Run simulation with the network:

`docker run --rm -it --net=ros-net -v /tmp/.X11-unix:/tmp/.X11-unix -e DISPLAY --gpus all -e NVIDIA_DRIVER_CAPABILITIES=all --privileged --name erc_sim erc_navigation_sim`

3. Run navigation container with the network:

`docker run --rm -it --net=ros-net -v /tmp/.X11-unix:/tmp/.X11-unix --privileged -e DISPLAY --env='QT_X11_NO_MITSHM=1' --name gtu --gpus all -e NVIDIA_DRIVER_CAPABILITIES=all ghcr.io/gtu-ros/erc-remote-navigation bash`

4. Find out simulation container's ip address

`docker inspect erc_sim | grep IPAddress`

`"IPAddress": "172.18.0.2"`

5. Find out navigation container's ip address

`docker inspect gtu | grep IPAddress`

`"IPAddress": "172.18.0.3"`

5. In navigation container set ip's:

`export ROS_MASTER_URI=http://172.18.0.2:11311`
`export ROS_IP=172.18.0.3`
