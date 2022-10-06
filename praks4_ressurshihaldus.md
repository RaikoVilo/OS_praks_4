Raiko Valo praktikum 4 töö, esitan selle siin, sest wiki ei tööta enam. Selles praktikumis tutvume operatsioonisüsteemi ressurssidega. Selleks õpime tundma erinevaid tööriistu nii Linuxi kui Windowsi all.

|Küsimus|Linux|Windows|Linuxis kasutatud käsklus|Windowsis kasutatud tööriist|
| --- | --- | --- |  --- | --- |
|Mitu protsessi kokku arvutis käib?|218|263|ps -aux (kriips) wc -l|Task manager -> Performance|
|Milline on kõige esimesena käivitatud protsess?|/sbin/init splash|Secure System|ps axo pid,cmd,comm,etime|Process Explorer -> start time|
|Mitu ja milliste kasutajate protsesse arvutis käib?|USER, root, systemd-oom, systemd-resolve, systemd-timesync, messagebus, avahi, syslog, kernoops, raiko, rtkit, colord|DWM-2, LOCAL SERVICES, NETWORK SERVICES, USER, SYSTEM, UMFD-0|ps -eo user|Task manager -> details|
|Kui kaua on arvuti järjest töötanud (up time) ? (Alternatiivselt võib vastata ka millal (kuupäev ja kellaaeg) arvuti viimati käima pandi?)?|36 min|6:00:32:31|uptime|Task manager -> performance -> CPU|
|Milline protsess käivitati kõige hiljem (viimasena)?|ps -ef|opera.exe|ps -ef|Process explorer -> start time|
|Milline on kõige rohkem protsessoriaega võttev protsess?|/usr/bin/gnome-shell|System Idle Process 556:07:44.703|ps -aux --sort -pcpu|process explorer -> CPU time|
|Milline on kõige rohkem virtuaalmälu (aadressiruumi, commit, Virtual Size) võttev protsess?|/usr/bin/gnome-shell|opera.exe|ps -aux --sort -vsz|Process Explorer -> Virtual Size|
|Milline on kõige rohkem füüsilist mälu (working set) võttev protsess?|/usr/bin/gnome-shell|VirtualBoxVm.exe|ps -aux --sort -pcpu|Process Explorer -> working set|
|Kui palju füüsilisest mälust (Physical Memory) on vaba?|278Mi|6,6GB|free -h|Task Manager -> Performance -> Memory|
|Kui palju on põhikettal (C:, /) vaba ruumi mahult (GB) ja protsentuaalselt?|11GB 49%|234GB free of 476GB -> 49,57%|df -h|File explorer -> this pc|
|Milline on kõige suurem kõvakettal olev fail ja kõige suurem kaust?|Suurim kaust - /usr, suurim fail - /var/lib/snapd/seed/snaps/gnome-3-38-2004_112.snap|Suurim kaust - windows ja suurim fail - ext4.vhdx|sudo du -a / (kriips) sort -n -r (kriips) head -n 100|WinDirStat|
|Võrrelge terminali käskude: ```sha1sum /dev/zero  sha1sum /dev/zero``` ja sha1sum ```/dev/urandom  sha1sum /dev/urandom``` protsessori nõudlust. Avage teine terminaliaken ja top samaaegseks käivitamiseks. Uurige millisele CPU alamtegevusele us, sy, id, wa, st jne kulub enim protsessori aega ja mitu protsenti kulub kummagi käsu korral? (Ainult Linuxis)|```sha1sum /dev/zero  sha1sum /dev/zero``` kõike rohkem kulub aega us 94,9 ja seal sy 4,5. ```sha1sum /dev/urando  sha1sum``` /dev/uronado kulub kõige rohkem aega 48,5 id, seal on 22,2 us ja 29,4 sy| |top| |
|Milline protsess kõige rohkem salvestusseadmele kirjutab, kõige rohkem salvestusseadmelt loeb? Millisesse faili antud protsess kõige rohkem kirjutab, millisest failist kõige rohkem loeb? (Ainult Windowsis)| |Kõige rohkem kirjutab ja loeb system. Kõige rohkem kirjutab system protsess ja kõige rohkem loeb opera.exe protsess | |Resource manager -> disk -> disk activity|
|Millise protsessi poolt tekitatud võrguliiklus on suurima mahuga? Vali antud protsessi poolt kasutatavatest ühendustest üks ning kirjuta välja järgnev: kohalik IP-aadress, kohalik port, ühenduse teise poole IP-aadress, port, latents ja antud ühenduse poolt kasutatav võrguliikluse kogumaht.| |opera.exe PID:13640 kohalik aadress:192.186.3.8 kohalik port:54471 latency 43ms teise poole aadress: 157.240.205.1 port: 443 ja kogumaht 367B/sec | |Resource Monitor -> network|
|Sõber kurdab, et tema arvuti on oluliselt aeglasem kui varasemalt. Millise programmiga ja millise parameetrite abil saate tuvastada milline protsess või teenus muudab arvuti aeglaseks?|Paneks kinni protsessid mis pole tähtsad ja mis kasutavad liiga palju CPU-d.  |Suleks kõik üleliigsed rakendused mis taustal käivad. Vaataks üle startup settingud, ja keelaks rakendustel, mida igapäevaselt ei kasuta, käivituda.|top|Task manager|


12. küsimuse pildid: 
![sha1sum_zero](https://user-images.githubusercontent.com/34316385/194403419-06e3858a-68e2-4993-92b0-d9f7c061e0fa.png)
![sha1sum_random](https://user-images.githubusercontent.com/34316385/194403432-95a53de1-e661-4700-a00c-e9aeac9506a2.png)

14. küsimuse pilt
![real-network](https://user-images.githubusercontent.com/34316385/194403576-7199a6ab-46a9-4d92-bcc7-0f6409d4007c.png)
