Chinachu [![Build Status](https://secure.travis-ci.org/kanreisa/Chinachu.png)](http://travis-ci.org/kanreisa/Chinachu) [![tip for next commit](http://tip4commit.com/projects/689.svg)](http://tip4commit.com/projects/689)
========
Chinachu is an Open Source Digital Video Recorder System for Linux.

Visit the Chinachu website for more information: <https://chinachu.moe/>

Introducing Chinachu Usushio
----------------------------
* Work in progress. This does **NOT** work yet.

![](https://yabumi.cc/1480f9929280d2ba07c8ac12.png)

### What's New?
* **Mirakurun** Service
  * tuner pooler / manager
  * tuner failover
  * tuner grouping
  * TCP / UNIX domain socket M2TS packet streaming
* Operator Service
  * continuous EPG updater
  * transcoder
  * network tuner access
  * internet radio recorder *(TBD)*
* Server Service
  * REST API v2
  * DLNA (UPnP AV)
  * plugin system *(TBD)*
  * access control *(TBD)*
* WUI Client
  * TV view
  * frame cutter

### How to Update

#### Uninstall the Chinachu Beta
1. `sudo -i`
2. `/etc/init.d/chinachu-wui stop` or `service chinachu-wui stop`
3. `/etc/init.d/chinachu-operator stop` or `service chinachu-operator stop`
4. `insserv -r chinachu-wui`
5. `insserv -r chinachu-operator`
6. `rm -v /etc/init.d/chinachu-wui /etc/init.d/chinachu-operator`
7.  `exit`

#### Install the Chinachu Usushio

##### A) using Chinachu Version Manager
1. `cd ~/chinachu/` (your Chinachu installed directory)
2. `rm -rfv .git`
3. `curl https://cvm.chinachu.moe/cvm.sh > cvm.sh && chmod +x cvm.sh`
4. `./cvm.sh install latest`
5. `ln -s ./chinachu ~/bin/chinachu` (optional)

##### B) using Git for Advanced / Developers
1. `cd ~/chinachu/` (your Chinachu installed directory)
2. `git reset --hard HEAD^`
3. `git fetch`
4. `git checkout master-usushio`
5. `make && make clean`

#### Migration to Usushio from Beta
1. `curl https://cvm.chinachu.moe/migration-scripts/beta-config.js | ./chinachu test node` *(TBD)*
2. `curl https://cvm.chinachu.moe/migration-scripts/beta-rules.js | ./chinachu test node` *(TBD)*
3. `curl https://cvm.chinachu.moe/migration-scripts/beta-recorded.js | ./chinachu test node` *(TBD)*

#### Install the Chinachu Usushio Services
1. `./chinachu service mirakurun initscript > /tmp/chinachu-mirakurun`
2. `./chinachu service operator initscript > /tmp/chinachu-operator`
3. `./chinachu service server initscript > /tmp/chinachu-server`
4. `sudo chown root:root /tmp/chinachu-*`
5. `sudo chmod +x /tmp/chinachu-*`
6. `sudo mv -v /tmp/chinachu-mirakurun /tmp/chinachu-operator /tmp/chinachu-server /etc/init.d/`
7. `sudo insserv chinachu-mirakurun` *(TBD)*
8. `sudo insserv chinachu-operator` *(TBD)*
9. `sudo insserv chinachu-server` *(TBD)*
