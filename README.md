# Control Kuka manipulator with robonomics.
Video with an example of work can be found 
***
## Requirements
* ROS melodic, Gazebo (installation instraction [here](http://wiki.ros.org/melodic/Installation/Ubuntu)
* Some extra packages
```bash
sudo apt-get install ros-melodic-gazebo-ros-control ros-melodic-effort-controllers ros-melodic-joint-state-controller
```
* IPFS 0.4.22 (download from [here](https://www.npackd.org/p/ipfs/0.4.22) and install)
```bash
tar -xvzf go-ipfs_v0.4.22_linux-386.tar.gz
cd go-ipfs/
sudo bash install.sh
ipfs init
```
* ipfshttpclient
```bash
pip install ipfshttpclient
```
* Robonomics node (binary file) (download latest release [here](https://github.com/airalab/robonomics/releases))
* IPFS browser extension (not necessary)
***
## Installation
Install Kuka manipulator and control packages
```bash
cd catkin_wc/src/
git clone https://github.com/orsalmon/kuka_manipulator_gazebo
git clone https://github.com/LoSk-p/kuka_controller
cd ..
catkin_make
```
***
## Running gazebo model
```bash
roslaunch manipulator_gazebo manipulator_empty_world.launch
```
In a new window
```bash
rosrun manipulator_gazebo move_arm_server
```
![model](https://github.com/LoSk-p/media/blob/master/1.png)
***
## Running robonomics
Go to the folder with robonomics file ad create a local robonomics network:
```bash
./robonomics --dev --rpc-cors all
```
![robonomics](https://github.com/LoSk-p/media/blob/master/2.png)
Go to https://parachain.robonomics.network and switch to local node
![local](https://github.com/LoSk-p/media/blob/master/3.png)
Then go to Accounts and create KUKA and WORK accounts. Save account's names and keys, you will need them later
![acc](https://github.com/LoSk-p/media/blob/master/4.png)
![accs](https://github.com/LoSk-p/media/blob/master/Screenshot%20from%202020-09-18%2001-07-56.png)




