# CAREBIT
Shell script to install a [Carebit Masternode](https://carebit.org) on a Linux server running Ubuntu 16.04. Use it on your own risk.
***

## Installation
```
wget -q https://raw.githubusercontent.com/zoldur/Carebit/master/carebit_install.sh  
bash carebit_install.sh
```
***

## Desktop wallet setup  

After the MN is up and running, you need to configure the desktop wallet accordingly. Here are the steps:  
1. Open the Carebit Desktop Wallet.  
2. Go to RECEIVE and create a New Address: **MN1**  
3. Send **30000** CBT to **MN1**. You need to send all 30000 coins in one single transaction.
4. Wait for 15 confirmations.  
5. Go to **Help -> "Debug Window - Console"**  
6. Type the following command: **masternode outputs**  
7. Go to **Masternodes** tab  
8. Click **Create** and fill the details:  
* Alias: **MN1**  
* Address: **VPS_IP:PORT**  
* Privkey: **Masternode Private Key**  
* TxHash: **First value from Step 6**  
* Output index:  **Second value from Step 6**  
* Reward address: leave blank  
* Reward %: leave blank  
9. Click **OK** to add the masternode  
11. Close and open the wallet again.
12. Go to **Masternodes** -> **My Master Nodes** tab
13. If you don't see your masternode, click **Update**
14. Unlock your wallet if it is encrypted
15. Select your masternode and click on **Start**
16. Login to your VPS and check your masternode status by running the following command. If you get **Status 9**, it means your masternode is active.
```
Carebitd masternode status
```
***

## Usage:
```
Carebitd masternode status  
Carebitd getinfo
```
Also, if you want to check/start/stop **Carebit**, run one of the following commands as **root**:

```
systemctl status Carebit #To check if Carebit service is running  
systemctl start Carebit #To start Carebit service  
systemctl stop Carebit #To stop Carebit service  
systemctl is-enabled Carebit #To check if Carebit service is enabled on boot  
```  
***

## Known issues

1. If your wallet does not sync, please add the following nodes to Carebit.conf. On Windows full path is **%APPDATA%\Carebit**.
```
addnode=159.65.84.183
addnode=167.99.204.45
addnode=167.99.204.49
addnode=167.99.204.53
addnode=167.99.91.226
```
***

## Donations

Any donation is highly appreciated  

**CBT**: CTijMUhgQFw6P9zq5UeeARB6TPXQq92iQD  
**BTC**: 3MQLEcHXVvxpmwbB811qiC1c6g21ZKa7Jh  
**ETH**: 0x26B9dDa0616FE0759273D651e77Fe7dd7751E01E  
**LTC**: LNZpK4rCd1JVSB3rGKTAnTkudV9So9zexB  

