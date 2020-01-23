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
