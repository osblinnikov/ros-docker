rosDocker
=========

Docker container for the ROS (Robot Operating System) indigo base.

get from docker hub:

    docker pull osblinnikov/rosdocker
    docker run -p 6080:6080 -v `pwd`/workspaceSrc:/home/ros/workspace/src -t -i osblinnikov/rosdocker

or to build container from dockerfile, type command in current directory:

    git clone https://github.com/osblinnikov/rosDocker.git
    cd rosDocker
    docker build -t osblinnikov/rosdocker .

To start the fresh built container simply type:

    ./run 

Now it's time to test ros installation

Browse http://127.0.0.1:6080/vnc.html

Connect to the desktop and open new terminal. Launch roscore:

    roscore

Open one another terminal and launch turtlesim:

    rosrun turtlesim turtlesim_node

Be Happy!


If you'd like to configure launch steps of the container, fix a `startcontainer`
script and rebuild the container

Commit:

    docker commit --author="FIXME" --message="FIXME" FIXME_75f05d8f7da3 osblinnikov/ros:FIXME

Note, for starting master and child nodes directly from the container console (not from vnc) you can use preinstalled `tmux` multiplexer of consoles

TODO
---

Figure out how to export ROS dynamic tcp/udp ports from docker container. Seems like [coreos-rudder](https://coreos.com/blog/introducing-rudder/) can help with providing virtual network
