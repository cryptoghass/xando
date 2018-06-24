# Installing masternode XDO for Windows and Linux on VPS server

## In this guide you will find a step-by-step description on how to install and configure masternode on VPS server Linux Ubuntu 16.04 Server for 64-bit systems. This can be configured through a console terminal using commands without GUI.

## To ensure the masternode's safety and stability, note the basic requirements for launching it:

### At least 6000 XDO coins on "hot" VPS wallet.
### Installed "cold" wallet. From this wallet the required amount will be transferred to the wallet masternode and to be remotely controlled node with running hot wallet.
### A modern computer. The masternode operations do not require a powerful computer, but you must use high quality and modern hardware and SSD.
### A separate IP address for hosting the masternode.

## If all these conditions are met, proceed to configuring masternode.

# Set up the "cold" wallet
## Install the latest version of the wallet xando for your OS and synchronize it with the network. To ensure security of your data and avoid loss of funds, perform the following conditions:

### Update the antivirus so that the computer remains under reliable protection.
### Set wallets only from trusted and official sources.
### Create a backup of your wallet and store it in a safe place, to restore access in case of file loss. Wallet file Wallet.dat you can find in the directories: 
###	Windows:	%APPDATA%\Xando\
###	Linux:		~/.xando/

### Enable wallet encryption wallet, so nobody could access your data and steal your coins.

# Configure masternode and set parameters
## Open the "cold" wallet. If the sync is successful, the next step is to configure masternode. To do this, go to the Tools tab in the main menu and start the console.

## You should perform some commands to obtain the key parameters for configuring the masternode. Save these settings in a separate document, in order not to lose them. Proceed to command execution.

### 1. Get the masternode key. To get MASTERNODE_PRIVATKEY, enter the command:
```
masternode genkey
```

### 2. Get the masternode address. To obtain MASTERNODE_ADDRESS type:
```
getaccountaddress MASTERNODE or getaccountaddress MASTERNODE_ALIAS_NAME.
```

### 3. Get transaction outputs. To obtain MASTERNODE_PRIVATKEY first send to your MASTERNODE_ADDRESS 6000 XDO. This can be done in the tab Send main wallet. Then type the command:
```
masternode outputs
```

### 4. Open the file masternode.conf in a text editor and add the line:
```
MASTERNODE_ALIAS_NAME VPS_IP:28599 MASTERNODE_PRIVATKEY TX_ID TX_INDEX
```
### Now save the file and set up the VPS server.

### 5. Run the SSH client and authorise as superuser (root). Complete installation and enter the following commands:

```
wget https://raw.githubusercontent.com/xando-club/xando/master/docs/MNsetup.sh
chmod 755 MNsetup.sh
./MNsetup.sh
```

### During execution the script will request the masternode key. Enter your MASTERNODE_PRIVATKEY. Installation takes less than 20 minutes. After installation is completed, proceed to the final stage.
### Launch masternode
### Return to "cold" wallet and run it. Next, go to the tab Masternodes and run installed masternode. To check if everything is working, enter console command 

```
xando-cli masternode status
```

### If the test is completed successfully, masternode works. Watch out for the stability of your Internet connection and do not forget to regularly check the masternode for errors. 
