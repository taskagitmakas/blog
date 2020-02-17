title: "versa"
date: 2020-01-21T08:34:33+08:00
draft: false
featuredImg: ""
tags: 
  - VERSA
  - 101
  - SDWAN
  - Ubuntu
  - Linux
---

Setup xrdp on Lubuntu

Install xrdp

sudo apt-get install xrdp
Edit or create ~/.xsession with the following content

lxsession -e LXDE -s Lubuntu
Restart xrdp

sudo service xrdp restart



sudo docker run -p 8080:8080 -e NEKO_PASSWORD=neko --shm-size=2gb nurdism/neko:latest


docker pull dmouse/browser
docker run -ti --rm -e DISPLAY=$DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix dmouse/browser # or
docker run --security-opt seccomp:/home/user/chrome.json -ti --rm -e DISPLAY=$DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix dmouse/browser google-chrome


sudo docker run -p 59000-59100:59000-59100/udp -e NEKO_PASSWORD=neko -e NEKO_ADMIN='secret' --shm-size=1gb nurdism/neko:latest 

-p 59000-59100:59000-59100/udp



I have installed WANem 3.0 Beta 2 on a physical machine with 2 interfaces, and I have 2 Linux boxes connected to it. Like so:

Linux1:100.100.100.2 <--> 100.100.100.1:WANem:200.200.200.1 <--> 200.200.200.2 Linux2

I have set each Linux box to use the WANem interface they are connected to as their gateway. Each Linux box can ping the addresses of both WANem interfaces (ie, Linux1 can ping both 100.100.100.1 and 200.200.200.1). However neither of them can ping each other. From reading tutorials, it seems that it should work by default, but it is not working. Does anyone know how to set up WANem to do this kind of routing? I'm not familiar with the WANem shell.

Thanks!

EDIT: It seems that in this configuration you need to manually add IP forwarding - in the WANem shell I typed:

echo 1 > /proc/sys/net/ipv4/ip_forward
and I was able to ping both endpoints from each other. This is just a temporary change, so if you reboot it will revert to not forwarding. I haven't tried it yet but apparently this is controlled by the file /etc/network/options, so you can edit this and change ip_forward=no to ip_forward=yes and the change should be permanent.