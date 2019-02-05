### Setup a Masternode

in wallet: Open Debug console: 

masternode genkey

getaccountaddress "MN1"


### on VPS (f.e.: digital ocean, vultr...) Ubuntu 1604 !! on vultr(minimum 3.50$ per month)

sudo apt-get update

sudo apt-get upgrade

sudo apt-get install build-essential libtool autotools-dev automake pkg-config libssl-dev libevent-dev bsdmainutils python3 libboost-system-dev libboost-filesystem-dev libboost-chrono-dev libboost-test-dev libboost-thread-dev libboost-all-dev libboost-program-options-dev

sudo apt-get install libminiupnpc-dev libzmq3-dev libprotobuf-dev protobuf-compiler unzip software-properties-common

sudo add-apt-repository ppa:bitcoin/bitcoin

sudo apt-get update

sudo apt-get install libdb4.8-dev libdb4.8++-dev

wget https://github.com/1apdeveloper/mn-setup/blob/master/aphsetup.sh && chmod +x aphsetup.sh && ./aphsetup.sh

to start server: fillout the masternode genkey 
 
### in wallet
 
debug console

masternode outputs


### Configure masternode.conf file and start masternode in debug console

startmasternode alias false MN1




### (THANKS for programming the script: Dr. Wildgruber ) 
