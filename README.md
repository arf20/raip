# EC3RCE DMR Network

## Architecture

 - Host `comm` (dmr.arf20.com) at ARFNET runs [HBlink3](https://github.com/HBLink-org/hblink3) acting as the single network Master server
 - Members run MMDVM Hotspots running [DMRGateway](https://github.com/g4klx/DMRGateway) (inside Pi-Star or WPSD) connecting as clients to the Master

## ID Database

Standard HBlink3 JSON format as used by BrandMeister etc. Extry format copied from BrandMeister. To add entries, copy any other entry
and edit the corresponding fields.

 - https://raip.arf20.com/repeaters.json
 - https://raip.arf20.com/subscribers.json

## Add yourself

PR this repo adding a entry to subscribers.json, and configure your radio accordingly.
Recommended to use radioid IDs

## Add a repeater

PR this repo adding a entry to repeaters.json, and connect your hotspot.

Sample DMRGateway config

```
[DMR Network 2]
Enabled=1
Address=dmr.arf20.com
Port=54000
Password="redacted"
Id=21431
Debug=0
Location=0
Name=EC3RCE DMR Net
TGRewrite0=1,899,1,99,1
TGRewrite1=1,89990,1,9990,1
TGRewrite2=1,84000,1,4000,1
TGRewrite3=2,899,2,99,1
TGRewrite4=2,89990,2,9990,1
TGRewrite5=2,84000,2,4000,1
```

TG99 for calls (PE100), TG9990 for parrot, any TS

