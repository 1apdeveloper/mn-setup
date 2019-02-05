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

sudo apt-get install libdb4.8-dev libdb4.8++-dev

wget https://github.com/1apdeveloper/mn-pos-Coin-APHolding/blob/master/apholding-cli

wget https://github.com/1apdeveloper/mn-pos-Coin-APHolding/blob/master/apholding-tx

wget https://github.com/1apdeveloper/mn-pos-Coin-APHolding/blob/master/apholdingd

chmod +x apholdingd

chmod +x apholding-tx

chmod +x apholding-cli

sudo mv apholdingd apholding-cli apholding-tx /usr/bin/

mkdir $HOME/.apholding

nano $HOME/.apholding/apholding.conf

#----

rpcuser=rpc_apholding

rpcpassword=replace_with_a_good_password_on_your_choice

rpcallowip=127.0.0.1

#----

listen=1

server=1

daemon=1

maxconnections=64

#----

masternode=1

masternodeprivkey=REPLACE_WITH_MASTERNODE_PRIVATE_KEY

externalip=REPLACE_WITH_EXTERNAL_IP_OF_VPS

#----

 to start the server : 
 
 apholdingd

 
### in wallet
 
debug console

masternode outputs


### Configure masternode.conf file and start masternode in debug console

startmasternode alias false MN1




### (THANKS for programming the script: Dr. Wildgruber ) 
