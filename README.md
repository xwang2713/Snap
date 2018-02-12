# Snap
Build HPCC Snap package

## Requirement
* Ubuntu 16.04 amd64
* Snap package which should be already installed by OS


## Snap build code
* There is snap/hooks/install script which acts like an install code. It will run automatically when snap install the HPCC package. Remember this install script will only run in the initial install.  

* snap package will be installed to  /snap as readonly. The config/runtime/log data are under /var/snap/hpcc-ce/common/

## Build
* Get HPCC-Platform from https://github.com/xwang2713/HPCC-Platform  branch: HPCC-15738_snap
* Get this repository. Assume the project directory is "Snap"
* Go to Snap directory.  If the HPCC-Plaform directory is different modify snapcraft.yaml file "source: ../HPCC-Platform"
* Add/Remove any cmake options in "configflags"
* Remove "prime", "parts" and "stage" if there is a previous build and you want rebuild everything.
* To build run: snapcraft 
* If everything run OK a hpcc-ce-0.1.snap file will be created



## Install/Uninstsall
*Install:  sudo snap install <HPCC snap package> --devmode --dangrous
*Uninstall: sudo snap remove <HPCC snap package>



## Run
* To start HPCC: sudo snap run hpcc-ce.hpcc-init start 


