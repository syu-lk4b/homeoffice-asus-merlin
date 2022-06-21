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

## Enable IpSec VPN
the reason to enabled the IPsec VPN is that you can easily enabled this VPN client in any devices. There are many other vpn options, however some of them require install special software, but for the ipsec VPN , most of the client has installed it by default. </br>

Why you need the VPN in the router, here is two reason for myself.</br>
1, VPN back to home network, so I coudl WoL my NAS get anything from it </br>
2. I could relay on my home router for bypassing the GFW
3. When I travel outside of China, I could VPN back to use some services which only allowed the China IPs, eg Netease, Youku...
<img width="884" alt="image" src="https://user-images.githubusercontent.com/3851844/174716543-c30da649-c80e-42b8-9854-b523aeb294be.png">

### Enable the DDNS
Since it's not easy to get a fixed IP in your home, so we need the helps from the DDNS service, It will query your public IP address and automatic update the DNS record. I am currently using the namecheap DDNS "namecheap.com"

<img width="1236" alt="image" src="https://user-images.githubusercontent.com/3851844/174716791-34e61f77-ed1f-4e60-adbd-921fe087ed45.png">

### Enable the DDNS client

<img width="792" alt="image" src="https://user-images.githubusercontent.com/3851844/174716879-22b1b1c3-c0cf-4b25-afe4-daf2b2d60d53.png">

### Enable the DMZ or PortMapping in your ISP modem
If you are using bridge mode , please ignore this step </br>
I personally recommended the port-mapping, as DMZ is mapping entire ports to your router , that's not secure. 

![IMG_3297](https://user-images.githubusercontent.com/3851844/174717143-8334f164-c6b6-4990-952f-05572b6c3bce.jpg)

![IMG_3298](https://user-images.githubusercontent.com/3851844/174717153-fe13f45e-cf81-458d-ae38-ed481a2a40c6.jpg)


## IPTV Special setup
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
## others
you could also find more related merlin software center infos from this repo </br>
https://github.com/koolshare/rogsoft </br>
<img width="1150" alt="image" src="https://user-images.githubusercontent.com/3851844/174716081-befdf3d9-755e-4cd2-aa68-282e9d837cde.png">



