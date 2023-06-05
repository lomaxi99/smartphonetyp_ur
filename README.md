# Getting started
## How to set up the network connection
Note: `Profinet` and `Ethernet/IP` need to be disabled in the robot instalation.\
The robot network settings should be configured like this:

**Network** (robot):\
IP:              192.168.1.102\
Subnet mask:     255.255.255.0\
Standard gatway: 0.0.0.0\
Prefered DNS:    0.0.0.0\
Alternative DNS: 0.0.0.0\
\
The computer network settings should be configured like this:

**Network** (computer):\
IPv4 (manual)\
IP:              192.168.1.101\
Subnet mask:     255.255.255.0\
Prefered DNS:    "empty"

Tip: Test the connection by pinging the robot.

```
ping 192.168.1.102
```

## How to establish the ros2 connection


```
Testcode
```