# CryptoPriceAlert-Bot

**How To Set Up AWS Connection**

[Tutorial](https://www.youtube.com/watch?v=MApTRT37B0k)

**Important Note**
Uptime: ~13 Days
Downtime: ~ 2 Days
After 2 days, the bot will autorecover and be able to make calls to the CryptoCompare API. 


*Rough Steps*
1) Create EC2 Instance using t2-Micro
2) Generate your putty private file (.ppk) using puttyGen.exe
3) Connect to your EC2 Instance with putty.exe using ubunutu@IPv4 address
4) Create an extra screenn session using "screen -S New"
6) After running your python file, detach the screen using "Ctrl + A + D"
7) Logout of terminal using "Ctrl + A + D"
8) To reconnect to your Bot console, use "screen -r {window name that you created before}
9) Ctrl + C to terminate the bot and update it (remember to git pull/push)

**Function of Bot**
1) Get current price of Coins with its respective candle chart (various timeframes)
2) Get alert notification when price of desired coin is above or below your target level

**Possible Errors**

Error: Running py file
> python3 -m tg_bot_service (without .py extension)

Error: Importing ParseMode from Telegram
> pip install python-telegram-bot --upgrade

Error: KeyError"Coin"

This is due to hitting the Rate Limit of CryptoCompare API. 
> Add throttle function to before each API function to reduce the frequency of calls. I use this [ratelimit](https://pypi.org/project/ratelimit/) library

Error: pip3 module not found

This happens if you terminate your EC2 instance and relaunch a new server. You need to re-setup your ubuntu installation.

> sudo apt-get update
> 
> sudo apt-get install python3-pip
> 
> git clone "github repo"
> 
> cd "folder"
> 
> pip3 install -r requirements.txt
> 
> pip install "any other missing modules"
> 
> python3 -m tg_bot_service

**Putty Shotcuts**
1) Ctrl + A + D (to detach screen)
2) screen -list (to see all sessions)
3) screen -dr SCREENID (to reattached screen)
