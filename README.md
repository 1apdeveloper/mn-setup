# Masternode Setup - Step by step guide

Requirements: 	
1.) VPS for example on vultr or AWS on Amazon Services or Digital Ocean (on digitalocean you can get bonus 100$ for 60 days)
2.) for 1 Masternode you need a wallet with 50001 APH Coins

Feel free to use our reflinks to signup: 
vultr:  <a href="https://www.vultr.com/?ref=7811287"><img src="https://www.vultr.com/media/banner_2.png" width="468" height="60"></a>

Feel free to use our reflinks to signup: 
DigitalOcean ( to get the Bonus of 100$ ) you can use this link: https://m.do.co/c/620c3ac29a40
 
## change into the wallet 
in wallet: Open Debug console: 

```bash
masternode genkey
```

<table>
<tr><td>example</td></tr>
<tr><td>6ehsxiEwmLzeT4EaCuX9v2euuYQNGSjjBKxRUTrmbdXG</td></tr>
</table>

```bash
getaccountaddress "MN1"
```

<table>
<tr><td>example</td></tr>
<tr><td>HRbcQmmJUUPJ9RKZfa1ariykE1z774156P</td></tr>
</table>

send exact 50000 Coins to the address (confirmation need: 15) 


# Installation: for Security use SSH on your vps!!

setup start with security on vps in putty (firewall)

```bash
sudo ufw allow 22
```
```bash
sudo ufw allow 80
```
```bash
sudo ufw allow 5662
```
```bash
sudo ufw enable
```
```bash
sudo ufw default deny
```

start install the requirements on VPS:

```bash
sudo apt-get update
```
```bash
sudo apt-get upgrade -y
```
```bash
sudo apt-get install build-essential libtool autotools-dev automake pkg-config libssl-dev libevent-dev bsdmainutils python3 libboost-system-dev libboost-filesystem-dev libboost-chrono-dev libboost-test-dev libboost-thread-dev libboost-all-dev libboost-program-options-dev -y
```
```bash
sudo apt-get install libminiupnpc-dev libzmq3-dev libprotobuf-dev protobuf-compiler unzip software-properties-common -y
```
```bash
sudo add-apt-repository ppa:bitcoin/bitcoin
```
```bash
sudo apt-get update
```

start install another user:

```bash
sudo adduser yourusername
```

Setup a safe password for your username and fillout the requested details or click enter for default

```bash
./sudo usermod -aG sudo yourusername
```

change to user 

```bash
su - yourusername
```

download the sourcecode for the daemon 

```bash
sudo wget https://github.com/1apdeveloper/mn-setup/raw/master/apholding-cli
```
fillout the password of your username


```bash
sudo wget https://github.com/1apdeveloper/mn-setup/raw/master/apholding-tx
```
```bash
sudo wget https://github.com/1apdeveloper/mn-setup/raw/master/apholdingd
```
```bash
sudo chmod +x apholdingd
```
```bash
sudo chmod +x apholding-tx
```
```bash
sudo chmod +x apholding-cli
```
```bash
sudo mv apholdingd apholding-cli apholding-tx /usr/bin/
```
```bash
sudo apt-get install libdb4.8-dev libdb4.8++-dev -y
```
```bash
mkdir $HOME/.apholding
```
```bash
nano $HOME/.apholding/apholding.conf
```

```bash
#----
rpcuser=rpc_apholding
rpcpassword=chooseagoodpassword
rpcallowip=127.0.0.1
#----
listen=1
server=1
daemon=1
maxconnections=64
#----
masternode=1
masternodeprivkey=your-MASTERNODE-GENKEY-from-debugconsole
externalip=IP-address
#----
```

# start the vps server with

```bash
apholdingd
```



### back in wallet
 
go to debug console

```bash
masternode outputs
```

<table>
<tr><td>example</td></tr>
 <tr><td>{</td></tr>
<tr><td>    "txhash": "c8ab8aa43d50cae6bf2b89b09f124bd83beaec00537884be8ec6585d1922", </td></tr>
<tr><td>     "outputidx": 1 {</td></tr>
<tr><td>   }</td></tr>
</table>


# Configure masternode.conf file (look at the example in file), reopen wallet and start masternode in debug console

<table>
<tr><td>example for masternode in masternode.conf file </td></tr>
<tr><td>mn1 IP_OF_THE_SERVER:5662 MASTERNODE_GENKEY TX_HASH TX_OUTPUTS</td></tr>
<tr><td>mn1 123.12.15.14:5662 6ehsxiEwmLzeT4EaCuX9v2euuYQNGSjjBKxRUTrmbdXG c8ab8aa43d50cae6bf2b89b09f124bd83beaec00537884be8bae6585d1922 1</td></tr>
</table>

save file, reopen wallet and start in debug console !

```bash
startmasternode alias false MN1
```

