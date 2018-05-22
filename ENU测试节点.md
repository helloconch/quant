```
git clone https://github.com/enumivo/enumivo.git
cd enumivo
git fetch origin enumivo
git checkout -b enumivo origin/enumivo
git submodule update --init --recursive
./enumivo_build.sh
cd build
make install
```
### Register your node information, and apply node account/keys
1. Domain name or IP address
1. http port for monitor RPC access (default: 8888)
1. P2P port (default: 9876)
1. Host location
1. Organization name (the organization name displayed in monitor page)

### Fetch ENUAvengers public configurations

```
git clone https://github.com/d13o/ENUAvengers.git
```
### Make your own node data directory, copy the configurations and scripts
```
mkdir data
cd ENUAvengers
cp genesis.json config.ini start.sh stop.sh ~/data
```
### Fill in your node information
- Replace DATADIR in scripts start.sh stop.sh with <YOUR_DATA_DIR_PATH> 
- Fill in your node information and keys into config.ini

```
nano start.sh
change DATADIR=/root/mainnode to DATADIR=~/data

nano stop.sh
change DATADIR="/root/mainnode" to DATADIR="~/data"

nano config.ini
Modify the following

genesis-json = "/<path-to-genesis>/genesis.json"  if in the same directory as config.ini change change to "genesis.json" 
p2p-server-address = <your-domain-name>:9876
agent-name = "<organization>"
producer-name = <producer-name>
private-key = ["<producer-public-key>","<producer-private-key>"]

```

### Run enunode, check whether it works by watching the log file

```
cd data
./start.sh
tail -f stderr.txt
```
### Produce the blocks
If enunode works well, please contact the administrator to grant your the privilege of producing blocks.


## Monitor Website
http://avengers-monitor.enuism.com

