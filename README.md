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
open your file explorer on your pc 
copy any image or file of your choice 
visit ubuntu ( Linux)
open the folder 
click on home 
then the name of your folder like mine is jrkenny 
then paste 
also rename the file to what you can easily type out ( eg. car,calculator etc )
<img width="1284" height="920" alt="image" src="https://github.com/user-attachments/assets/ce75aa9e-b37a-4a3b-a98f-1a6909981456" />

## Now paste
```bash
irys upload FILE_NAME \
  -n devnet \
  -t ethereum \
  -w PRIVATE_KEY \
  --tags FILE_NAME FILE_FORMAT \
  --provider-url https://testnet-rpc.irys.xyz/v1/execution-rpc
```
change FILE_NAME to the actual name of the file. like for example if its a screenshot of a calculator and you renamed it calculator initially its saved as calculator.png on your pc so thats what youre copying ( calculator.png) 
 
change PRIVATE_KEY to your private key (without 0x) - Remember to use a burner wallet

change FILE_NAME and FILE_FORMAT (JPG,MP4,MKV). now that calculator you wrote as calculator.png now write it as calculator on the FILE_NAME and now write PNG on the FILE _FORMAT

change RPC_URL to your RPC

use this setup below as refrence

irys upload calculator.png \
  -n devnet \
  -t ethereum \
  -w PRIVATE KEY \
  --tags calculator PNG \
  --provider-url https://testnet-rpc.irys.xyz/v1/execution-rpc

should see something like this 
<img width="1198" height="159" alt="image" src="https://github.com/user-attachments/assets/581e31cb-5460-46ff-a815-9b36c7864157" />

  ## DONE
  Made with ❤️ by [Jrkenny](https://x.com/Jrken_ny)
