---
title: "Using VNC"
teaching: 10
exercises: 0
questions:
- "How are pages published?"
objectives:
- "Start your own VNC server"
- "Connect to a VNC server using an SSH tunnel"
keypoints:
- "VNC lets us see the graphical output from a remote system."
- "To connect to VNC on Sunbird we need to use an SSH tunnel due to firewall restrictions."
- "The VNC server needs to be started from an SSH session."
- "Programs using the VNC session will keep running when we disconnect."
---


# VNC

## Running a VNC server

~~~
$ ssh a.abc1@vnc.sunbird.swansea.ac.uk
[a.abc1@sl3 ~]$ vncserver

New 'sl3:4 (a.abc1)' desktop is sl3:4

Starting applications specified in /home/a.abc1/.vnc/xstartup
Log file is /home/a.abc1/.vnc/sl3:4.log
{ .bash}
~~~

We've launched a new VNC server and its server number 4. Keep note of this number, you'll need it again in a minute.

## Opening an SSH tunnel

VNC is now listening on port 5900 + our server number, so in this example we have server number 4 and the port number is 5904. Unfortunately the firewall configuration blocks incoming requests on these ports, we have to use an SSH tunnel to access it. An SSH tunnel puts all the data from a remote server through an SSH connection and then re-presents it on a different port on our local system. If we run:

~~~
ssh a.abc1@vnc.sunbird.swansea.ac.uk -L 5901:localhost:5904
~~~

It will map port 5901 on the local system in Aberystwyth to port 5904 on Sunbird. Our VNC client can now connect to port 5901 on the local system and it will actually get access to port 5904 on Sunbird.

When connecting a helpful message will be displayed telling you about your VNC session(s) and reminding you of the command to connect:

~~~
TigerVNC server sessions:

X DISPLAY #     PROCESS ID
:4              142658
Your VNCServer port is set to 5904
Connect with a tunnel using ssh:  ssh -L 5900:localhost:5904 a.abc1@vnc.sunbird.swansea.ac.uk
~~~
{: .bash}

~~~
### VNC clients with built in port fowarding
~~~

## Launching a VNC client

Run a VNC viewer and connect to localhost port 1 or 5901. 

~~~
vncviewer localhost:1
~~~

### VNC only launches a terminal with no window controls




{% include links.md %}
