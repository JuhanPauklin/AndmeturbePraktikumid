# Praktikum 15 - ID-kaart ja e-hääletamine  

Ül 1  

![image](https://github.com/JuhanPauklin/AndmeturbePraktikumid/assets/90179916/ae7dba06-ac7b-41fb-855e-229ff0e38a84)  
Ül 2  

![image](https://github.com/JuhanPauklin/AndmeturbePraktikumid/assets/90179916/6244362c-72fd-4e02-bcb9-6b8b60a21e01)  
Ül 3  

![image](https://github.com/JuhanPauklin/AndmeturbePraktikumid/assets/90179916/08f497f9-5d79-4cb3-a8b9-ef4ca634841e)  

Ül 4

1) E-hääle saladus on tagatud n-ö kahe ümbriku skeemi kaudu, kus kõigepealt krüpteerib valija oma hääle valimiste avaliku võtmega, mille ta saa korraldajalt ning siis allkirjastab valija saadud krüptogrammi oma privaatvõtme abil, mis moodustab siis teise ümbriku.
  Serveris eemaldatakse kõikidelt häältelt kõigepealt välimine ümbrik ja verifitseeritakse nende allkirjad, seejärel saadetakse sisemised ümbrikud edasi serverisse, kus need valimiste privaatvõtme abil dekrüpteeritakse ja hääled kokku loetakse.  
  
2) See, et nutiseadmega oma hääle kontrollimine ei avalikusta oma häält, on tagatud sellega, et kontrollimine ei jäta seadmesse konkreetse hääle kohta mingit jälge. Samuti on kontrollimiseks vaja QR-koodi, mis on kuvatud ainult hääletuses toime pandud masinas ning kontroll on teostatav kuni poole tunni jooksul ja kuni kolmel korral.

3) See et nutiseadme ega smart-ID'ga ei saa e-hääletada on vähesel määral tehiniline aga peamiselt poliitiline otsus.  
   Tehniline, sest Lätis ja Leedus on kasutusel vähem turvaline samrt-ID variant ja kuna seda on suudetud edukalt rünnata, siis turvalisuse huvides ei taheta lasta smart-ID valimisteks kasutada.  
   Peamiselt aga on otsuse taga poliitika, sest smart-ID pole riigi poolt väljastatav isikut tõendav dokument, vaid on eraettevõttele kuuluv isikutuvastuse ja digitaalse allkirjastamise rakendus, ning seetõttu ka smart-ID tulevik ei ole riigi kontrolli all

4) Arvan, et e-hääletamine on turvalisem kui valimiskasti juures paberhääletamine. Kindlasti vähemalt Eesti puhul, kus see on turvaliselt ning õiglaselt implementeeritud. Selle ülesehitus muudab hääle raskesti võltsitavaks ; hääle kontrollimise võimalus aitab tuvastada ründeid või hääle pahatahtliku muutmist.
   Paberhäält on hulga kergem võltsida/rikkuda ning sellel puudub ka võimalus oma häält kontrollida.
