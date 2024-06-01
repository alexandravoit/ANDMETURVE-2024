# PRAKTIKUM 15

1)  
![image](https://github.com/alexandravoit/ANDMETURVE-2024/assets/145194484/30294a84-de66-405a-bdd4-92530835ff92)
2)  
![image](https://github.com/alexandravoit/ANDMETURVE-2024/assets/145194484/af46ae0f-1cfc-4c14-9e8d-7f08907879c5)
3)  
![image](https://github.com/alexandravoit/ANDMETURVE-2024/assets/145194484/60730c92-9590-4bb1-9f22-04b584d247a1)
**.asice konteiner on Moodleisse lisatud**

4)
- **Kirjeldage võimalikult detailselt ja tehniliselt kuidas on tagatud hääle salajasus (kelle poolt sa hääletasid):**  Valija krüpteerib oma hääle valimiste avaliku võtmega, moodustades esimese ümbriku. Seejärel allkirjastab valija krüptogrammi oma privaatvõtmega ning moodustab teise ümbriku. Krüpteeritud ja allkirjastatud hääl saadetakse serverisse, mis eemaldab häältelt välise ümbriku, tuvastades hääletajad ja verifitseerides allkirjad.
Sisemised krüptitud hääled saadetakse edasi teise serverisse, millel on valimiste privaatvõti. Häälte lugemise server on eraldatud ja ei oma internetiühendust. Alates 2017. aastast implementeeriti miksimissüsteem, mille põhiselt digiallkirjad eemaldatakse ja hääled krüpteeritakse uuesti ning segatakse, et katkestada hääle ja allkirja seos.

- **Kuidas on tagatud, et nutiseadmega oma hääle kontrollimine ei avalikusta sinu häält:** Kui valija kasutab hääle kontrollimiseks nutitelefonis olevat verifitseerimisrakendust, siis kontrollib see nii hääle registreerimist registreerimisteenuse poolt kui ka seda, et hääl on korrektselt häälte kogumise serverisse kohale jõudnud. See protsess kasutab tugevaid krüptograafilisi meetodeid, mis tagavad, et kontrollkood ei sisalda otsest seost valiku sisuga.

- **Nutiseadmega ega Smart-ID'ga e-hääletamine ei ole võimalik. Kas vastav otsus on tehniline või poliitiline:** Arvan, et eelkõige tehniline. Muidugi leidub lahendus, kuidas mobiilselt hääletada. Cybernetica riskianalüüsis oli aga mainitud, et mobiilse operatsioonisüsteemi või selle konkreetse versiooni turvataset on väga raske hinnata. Veel keerulisem on võrrelda omavahel IOS ja Androidi turvaaspekte.
  
- **Kas e-hääletamine on ebaturvalisem, sama turvaline või turvalisem võrreldes valimiskasti juures paberhääletamisega:** Kaldun arvama, et see on ebaturvalisem kui klassikaline hääletamine, sest see soodustab kolmandate isikute sekkumist rohkem kui traditsiooniline lähenemine. 
