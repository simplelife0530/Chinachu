Chinachu [![Build Status](https://secure.travis-ci.org/kanreisa/Chinachu.png)](http://travis-ci.org/kanreisa/Chinachu) [![tip for next commit](http://tip4commit.com/projects/689.svg)](http://tip4commit.com/projects/689)
========
Chinachu is an Open Source Digital Video Recorder System for Linux.

Visit the Chinachu website for more information: <https://chinachu.moe/>

Introducing Chinachu Usushio
----------------------------
* Work in progress. This does **NOT** work yet.

![](https://yabumi.cc/1480f9929280d2ba07c8ac12.png)

### What's new?
* **Mirakurun** Service
  * tuner pooler / manager
  * tuner failover
  * tuner grouping
  * TCP / UNIX domain socket M2TS packet streaming
* Operator Service
  * continuous EPG updater
  * transcoder
  * internet radio recorder *(TBD)*
* Server Service
  * REST API v2
  * DLNA (UPnP AV)
  * plugin system *(TBD)*
  * access control *(TBD)*
* WUI Client
  * TV view
  * frame cutter

### How to update
1. `/etc/init.d/chinachu-wui stop`
2. `/etc/init.d/chinachu-operator stop`
