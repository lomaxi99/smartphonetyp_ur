# Getting started
## How to set up the network connection
Note: `Profinet` and `Ethernet/IP` need to be disabled in the robot instalation.\
The robot network settings should be configured like this:

**Network** (robot):
<pre>
IP:              192.168.1.102
Subnet mask:     255.255.255.0
Standard gatway: 0.0.0.0
Prefered DNS:    0.0.0.0
Alternative DNS: 0.0.0.0
</pre>

The computer network settings should be configured like this:

**Network** (computer):
<pre>
IPv4:            manual
IPv6:            disabled
IP:              192.168.1.101
Subnet mask:     255.255.255.0
Prefered DNS:    "empty"
</pre>
Tip: Test the connection by pinging the robot.

```
ping 192.168.1.102
```

## How to establish the ros2 connection
Note: Robot should be in home position!

**Robot**:\
Start `ros2.udf` on the robot. The appearing error message can be ignored.

**Computer**:\
Start `ur10.launch.py` in one terminal.

```
ros2 launch ur_bringup ur10.launch.py robot_ip:=192.168.1.102 launch_rviz:=true
```

## How to run a demo script
Starting a demo script to see if the conection was established

```
ros2 launch ur_bringup test_joint_trajectory_controller.launch.py
```

## How to controll the io ports
Enable the vaccum gripper by calling the `/io_and_status_contorller/set_io ur_msgs/` service and setting pin 5 either to 1 or to 0.
```
ros2 service call /io_and_status_contorller/set_io ur_msgs/srv/SetIO "{fun: 1, pin: 5, state: 1}"
```


## How to run the script for taking photos