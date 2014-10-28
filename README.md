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
  * channel scan

### How to Update

#### Uninstall the Chinachu Beta
```sh
sudo -i
/etc/init.d/chinachu-wui stop` or `service chinachu-wui stop
/etc/init.d/chinachu-operator stop` or `service chinachu-operator stop
insserv -r chinachu-wui
insserv -r chinachu-operator
rm -v /etc/init.d/chinachu-wui /etc/init.d/chinachu-operator
exit
```

#### Install the Chinachu Usushio

##### A) using Chinachu Version Manager
```sh
cd ~/chinachu/ # your Chinachu installed directory
rm -rfv .git
curl https://cvm.chinachu.moe/install.sh | bash
./cvm.sh install latest
ln -s ./chinachu ~/bin/chinachu // optional
```

##### B) using Git for Advanced / Developers
```sh
cd ~/chinachu/ # your Chinachu installed directory
git reset --hard HEAD^
git fetch
git checkout master-usushio
make && make clean
```

#### Migration to Usushio from Beta
```sh
curl https://cvm.chinachu.moe/migration-scripts/beta-config.js | bash
curl https://cvm.chinachu.moe/migration-scripts/beta-rules.js | bash
curl https://cvm.chinachu.moe/migration-scripts/beta-recorded.js | bash
```

#### Install the Chinachu Usushio Services
```sh
./chinachu service mirakurun initscript > /tmp/chinachu-mirakurun
./chinachu service operator initscript > /tmp/chinachu-operator
./chinachu service server initscript > /tmp/chinachu-server
sudo chown root:root /tmp/chinachu-*
sudo chmod +x /tmp/chinachu-*
sudo mv -v /tmp/chinachu-mirakurun /tmp/chinachu-operator /tmp/chinachu-server /etc/init.d/
sudo insserv chinachu-mirakurun
sudo insserv chinachu-operator
sudo insserv chinachu-server
```
