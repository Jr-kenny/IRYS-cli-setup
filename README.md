# IRYS-CLI-SETUP
# Guide on Irys Storage CLI Node Using ETH sepolia
Irys CLI is just a tool to interact with irys decentralized data layer, letting you upload, manage and access files or metadata on the test chain or off chain with permanent storage

# REQUIREMENTS
Ubuntu (20.04 / 22.04 / 24.04)
4GB RAM Min
Burner wallet (do not use your main wallet!)
ETH Sepolia testnet RPC ([chainlist](https://chainlist.org/))
ETH Sepolia faucet (get free tokens from [Alchemy](https://www.alchemy.com/faucets/ethereum-sepolia) Faucet)

# STEP 1. Installations:
## install dependencies
```bash
sudo apt-get update && sudo apt-get upgrade -y
```
```bash
sudo apt install curl iptables build-essential git wget lz4 jq make protobuf-compiler cmake gcc nano automake autoconf tmux htop nvme-cli libgbm1 pkg-config libssl-dev libleveldb-dev tar clang bsdmainutils ncdu unzip libleveldb-dev screen ufw -y
```
## Install nodejs & npm :
```bash
curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash - && sudo apt install -y nodejs
```
for mac

      brew install node

## Check version :
```bash
node -v
npm -v
```
Install CLI :
```bash
sudo npm i -g @irys/cli
```
Verify installation :

      irys 
# STEP – Fund Wallet, Check Balance & Upload File
## Fund wallet 

```bash
irys fund 100000000 \
  -n devnet \
  -t ethereum \
  -w PRIVATE_KEY \
  --provider-url https://eth-sepolia.public.blastapi.io
```
The fund amount is in wei, so you can adjust it if you need by adding more zeros or reducing. adding to increase the funding ammount like that
Replace PRIVATE_KEY  with your actual key (without 0x)
I already added a RPC URL but you can Replace [RPC_URL](https://eth-sepolia.public.blastapi.io) with the one you wan't if its giving you errors

## Check Balance
```bash
irys balance WALLET_ADDRESS \
  -t ethereum \
  -n devnet \
  --provider-url https://testnet-rpc.irys.xyz/v1/execution-rpc
```
Replace WALLET_ADDRESS with your actual address

## Upload a File
