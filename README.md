# homeoffice-asus-merlin
asus merlin setup, due to the covid condition, people now spend more time work from home, this include me as well. I am currently using Asus ax86u and ac68u for my home office. Createing this documents, in order to keep the changes and backups , so i can always restore them quickly</br>

Here is what it looks now, as you can see , I am using the aimesh for this two routers at this moment

<img width="808" alt="image" src="https://user-images.githubusercontent.com/3851844/174714582-bcd0fd2e-7d72-4919-9604-e87915a0a0d8.png">


## Firmware download
here is the two place that I used for downloading the new firmwares normally </br>
https://www.asuswrt-merlin.net/download </br>
https://fw.koolcenter.com/ </br>

## Plugins for Merlin
Since I am in China, in order to bypass GFW, you need some special plugins, here is the link for this plugin,I've also download it here , in case for some reason the upstream is blocked or removed. (this happens before, i guess you konw the reason)
https://github.com/hq450/fancyss </br>

## My router config backup
This will be encrpyted, in case it has some sentive informations

## Other Special setup
Enable IPTV in the main router (ax86u), plugin it to the modem port#3, not sure why, but others doesn't work.
<img width="754" alt="image" src="https://user-images.githubusercontent.com/3851844/174714828-0cc834df-769a-40b6-a730-3ad73a092e06.png">

On my second router which is aimesh worker router(ac68u), you have to add this command in order to let the vlan aware the iptv traffics. 
```
syuadmin@RT-AC68U-55A8:/jffs/scripts# pwd
/jffs/scripts
syuadmin@RT-AC68U-55A8:/jffs/scripts# cat wan-start
#!/bin/sh
/koolshare/bin/ks-wan-start.sh start
robocfg vlan 51 ports "0t 1t 2t 3t 4t" vlan 85 ports "0t 1t 2t 3t 4t"
syuadmin@RT-AC68U-55A8:/jffs/scripts#
```



