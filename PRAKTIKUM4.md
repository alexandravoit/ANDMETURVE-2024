# PRAKTIKUM 4

1)
<img width="515" alt="Screenshot 2024-03-17 at 22 19 14" src="https://github.com/alexandravoit/ANDMETURVE-2024/assets/145194484/aea22d8d-be7d-4f26-bb5e-7331b17d949b">
<img width="1112" alt="Screenshot 2024-03-17 at 22 18 48" src="https://github.com/alexandravoit/ANDMETURVE-2024/assets/145194484/9c4ee536-c35b-4617-a81f-87e5270a3ca1">
<img width="1181" alt="Screenshot 2024-03-17 at 22 18 34" src="https://github.com/alexandravoit/ANDMETURVE-2024/assets/145194484/247aea0d-6de0-4dba-8f97-fa076156d6d6">

2)   
<img width="816" alt="image" src="https://github.com/alexandravoit/ANDMETURVE-2024/assets/145194484/721e659c-92fe-4cb5-9c1c-894242632f1a">

3)  **Uuri praktikumi esimeses osas saadetud/vastuvõetud erinevaid e-kirju ja esita praktikumi arvestuseks tekstiliselt viis (5) näidet koos lühikese tehnilise seletusega kuidas vastav parameeter/rida jne e-kirja detailses vaates aitab tuvastada kas kiri on õige või vale.**

- X-Mailer rida: näitab, millist rakendust või programmi kasutati e-kirja saatmiseks. Kui see näitab midagi ebatavalist, võib see vihjata, et e-kiri on olnud võltsitud või loodud ebausaldusväärse allika poolt. Näiteks emailis, mis ma "Alo Peetsilt" sain oli x-maileri rida selline: X-Mailer: telnet.
- SPF
- ja DKIM staatuse kinnitused: SPF (Sender Policy Framework) ja DKIM (DomainKeys Identified Mail) on e-posti autentimise protokollid, mis aitavad tuvastada, kas e-kiri oli saadetud volitatud saatjalt, ent need ei pruugi alati korrektsed olla. Alo Peetsi võltsmeili puhul olid mõlemad väljad PASS.
- Received rida: näitab, mis servereid e-kiri läbinud on, Alo Peetsi meili puhul oli see *Received: from adalberg.ut.ee (adalberg.ut.ee [IPv6:2001:bb8:2002:500::36])*, kui serverid on väga tundmatud või ei vasta meiliaadressile, siis tasub meili autentsust üle kontrollida.
- Authentication-Results rida: Sisaldab ka DMARC (Domain-based Message Authentication, Reporting, and Conformance) kontrolli välja, mis määrab kuidas e-posti teenusepakkujad peaksid käituma e-kirjadega, mis ei vasta SPF ja DKIM autentimise nõuetele. DMARC poliitika saab olla üks kolmest: "p=none", "p=quarantine" või "p=reject".  

  
4) Krüpteeritud e-mail

5.1) Sõnum Signalis  
  
5.2)   
**Too praktikumi esituses välja vähemalt kolm (3) selget erinevust turvalisuse seisuskohast Signal sõnumite ja klassikaliste SMS-ide vahel ning esita lahendus praktikumi aruandesse.**

- *Krüpteerimine:* Signal kasutab krüpteerimist (E2EE), mis tagab, et ainult sõnumi saatja ja vastuvõtja saavad kirja sisu lugeda. Klassikalised SMS-id ei kasuta tavaliselt end-to-end krüpteerimist, mis tähendab, et sõnumid võivad olla loetud väliste isikute poolt.
- *Extra turvameetmed:* Signal pakub täiustatud turvalisusfunktsioone, nagu two-factor authentication, mis kaitseb kontot volitamata juurdepääsu eest ning annab võimalus kontrollida, millised seadmed on kontoga parajasti sisselogitud. Tavalistel SMS-idel üldiselt selline funktsioon puudub.
- *Sõnumite automaatse kustumise funktsioon:* Signaliga saab määrata aja, peale mida sinu sõnumid kettalt eemaldatakse (aeg hakkab jooksma hetkest, millal sina/inimene, kellele sõnumi kirjutasid sõnumit näeb), tavalistel SMS-idel üldiselt selline funktsioon puudub.

   
6.1)      
.onion veebileht, kust saab vist endale personaalse häkkeri värbata.
<img width="814" alt="image" src="https://github.com/alexandravoit/ANDMETURVE-2024/assets/145194484/434a5dff-3c68-4671-832c-b7e13d537383">

wholesome .onion veebileht, mis räägib erinevatest turvaohtudest ja kuidas nendega toime tulla.
<img width="814" alt="image" src="https://github.com/alexandravoit/ANDMETURVE-2024/assets/145194484/29c82d56-147c-4360-9023-f3a31d035388">

6.2)  
**Kirjuta aruandesse, milliste andmete lekkimise eest riiklikele jälgimisasutustele TOR Browser veebilehitseja kasutamine aitab** 
- IP-aadress: TOR Browser suunab internetiliikluse läbi juhuslikult valitud võrgustikku kuuluvate serverite, mis laseb varjata kasutaja päris-IP-aadressi. See pärsib kasutaja tuvastamist ja jälgimist internetis. TORi põhiline eesmärk on kasutajad üksteisest eristamatuks muuta. 

