Toimiva versio
---

###### 23.11.2025.
###### 20:09 

Järjestelmä:

Järjestelmän malli: Aspire E5-573G

Käyttöjärjestelmä: Microsoft Windows 10 Home

Suoritin: Inter(R) Pentium(R) 3558U @ 1.70GHz. Mhz, 2 ydin(tä)

Muisti: 6.00 Gt asennettua fyysistä muistia

Oracle Virtualbox

Debian 13 (trixie)


---

Minun piti luoda uusi virtuaalikone, koska koneen C-asema oli täynnä. Poistin vanhat tiedostot, jotta koneeseen vapautuisi tilaa. Tämän yhteydessä huomasin, että virtuaalikone oli vienyt 18 gt tilaa. Lopulta poistin siis kaikki nämä, ja asensin uuden debianin (13). Tämän jälkeen varmistin, että koneessa on kaikki päivitykset ja asennukset ajantasalla.
(Korjattu: 30.11.2025)

Aloitan syöttämällä tutut komennot, kuten: 

```
sudo apt-get update
sudo dpkg --configure -a
sudo apt-get -y dist-upgrade
sudo apt-get -y install ufw \
sudo ufw enable 
```


Lopuksi aikavyöhykkeen asennus, jotta ohjelmat toimivat oikein:

```
sudo timedatectl set-timezone Europe/Helsinki
sudo timedatectl
set-ntp true
```
-----

###### 20:30 

x) Lue ja tiivistä. (Tässä x-alakohdassa ei tarvitse tehdä testejä tietokoneella, vain lukeminen tai kuunteleminen ja tiivistelmä riittää. Tiivistämiseen riittää muutama ranskalainen viiva. Kannattaa lisätä mukaan myös jokin oma havainto, idea tai kysymys.)



Chacon and Straub 2014: Pro Git, 2ed: 1.3 Getting Started - What is Git?

1.3 Getting Started - What is Git?

- Git ei tallenna muutoksia riveittäin kuten monet muut versionhallintajärjestelmät (CVS, Subversion), vaan ottaa snapshotteja.
- Napshot-ajattelu: jos tiedosto ei ole muuttunut, Git viittaa aiemmin tallennettuun versioon sen sijaan, että tallentaisi sen uudelleen.
- Git lisää dataa, ei poista: commitit tallentuvat pysyvästi, ja niiden menettäminen on vaikeaa, mikä tekee kokeilusta turvallista.


Gitin käyttö on lähinnä 'git add . && git commit; git pull && git push'. Selitä tuon komennon jokainen osa. Käytä apuna lähteitä ja viittaan nämä. 
(Korjattu: 30.11.2025)


Git add .  Tarkoittaa, että kaikki nykyisen hakemiston (ja alihakemistojen) muutetut ja uudet tiedostot staging areaan eli indeksiin. Piste (.) lopussa tarkoittaa nykyistä hakemistoa. Lähde: (https://github.com/git-guides/git-add) 
(Korjattu: 30.11.2025)


Git commitilla tarkoitus on luoda uusi commit, joka tallentaa snapshotin jokaisesta tiedostosta. Tämä (commit) sisältää tietdostojen metatiedot, kuten (tekijä(t), aikaleima, viesti ja parent commit). Tämä on tärkeää toimenpide, koska Commitit muodostavat projektin-historian, johon voi halutessaan palata. Lähde: (https://github.com/git-guides/git-commit)
(Korjattu: 30.11.2025)


Git pull on hakee etärepon (esim. GitHub) uusimmat muutokset ja yhdistää nämä. Toimii kahdessa vaiheessa: git fetch – lataa uudet commitit etäreposta.
git merge (tai rebase) – yhdistää ne omaan branchiin. Tämä on tärkeä toimenpide, koska se varmistaa, että oma branch on ajan tasalla ennen pushia. Lähde: (https://github.com/git-guides/git-pull)
(Korjattu: 30.11.2025)


Varaston terokarvinen/suolax/ historia, eli loki ja muutokset. Kätevimmin komentokehotteesta 'git clone https://github.com/terokarvinen/suolax.git; cd suolax/; git log --patch --color|less -R'. Wepistäkin saattaa onnistua kliksuttelemalla "Commits".


```
all:

sudo salt-call --local -l info --state-output=terse --file-root srv/salt/ state.apply
```


- Salt‑tilat sovelletaan paikallisesti root‑oikeuksilla, käyttäen srv/salt/ hakemistoa tilatiedostojen lähteenä, ja tulostus on tiivis info‑tasolla.
- Makefile‑kohde on tapa automatisoida koneen konfigurointi Saltilla ilman master‑palvelinta.


###### 21:10 


a) Online. Tee uusi varasto GitHubiin (tai Gitlabiin tai mihin vain vastaavaan palveluun). Varaston nimessä ja lyhyessä kuvauksessa tulee olla sana "snow". Aiemmin tehty varasto ei kelpaa. (Muista tehdä varastoon tiedostoja luomisvaiheessa, esim README.md ja GNU General Public License 3)

Aloitetaan asentamalla:

```
sudo apt update
sudo apt install git
```
Tarkistetaan versio:

```
git --version
```

Luodaan avain:

```
ssh-keygen
cd .ssh/
cat id_25519.pub
```
Laitoin julkisen avaimen Githubiin. Repo luominen.

```
git clone git@github.com:JoonasJanttonen/Uusi-projekti_Snow.git
cd Uusi-projekti.Snow.git/
```


<img width="240" height="39" alt="Screenshot From 2025-11-23 21-38-42" src="https://github.com/user-attachments/assets/1e6872d3-930a-4d35-a7d7-b0a2068b8eb8" />

<img width="893" height="134" alt="Screenshot From 2025-11-23 21-51-54" src="https://github.com/user-attachments/assets/30cc9889-c0e4-4d33-8379-ddd2b9e2db82" />


Tässä vaiheessa piti asentaa micro, jotta pystyin suorittamaan/kirjoittamaan: README.md ja LICENSE.md

```
sudo apt update
sudo apt install micro
```

Tämän jälkeen lisäsin ohjeiden mukaisesti ´snow´ kuvaukseksi, ja jonka jälkeen ajoin seuraavat komennot:

```
git add .
git commit
git pull
git push
git log --patch
```

<img width="920" height="523" alt="Screenshot From 2025-11-23 22-26-44" src="https://github.com/user-attachments/assets/56144e5d-0fe1-4ab6-9e62-8c97870059df" />

Lopputulos! 

Tämä oli hyvää harjoitusta oppimisen kannalta. Tämän läksyn suorittamisessa auttoi muistiinpanot, joita olin kirjannut tunnilla, kuten kuvankaappaukset.

###### 22:38
Tauko.
###### 23:33

b) Dolly. Kloonaa edellisessä kohdassa tehty uusi varasto itsellesi, tee muutoksia omalla koneella, puske ne palvelimelle, ja näytä, että ne ilmestyvät weppiliittymään.

Kloonataan kotihakemistoon:

```
cd ~
git clone git@github.com:JoonasJanttonen/Uusi-projekti_Snow.git
cd Uusi-projekti_Snow
```


<img width="627" height="203" alt="Screenshot From 2025-11-23 23-38-08" src="https://github.com/user-attachments/assets/a2165b90-29e7-42fd-a713-93b69b0fd24e" />


Tämän jälkeen muokkasin nano -tiedostoa:

```
nano README.md
```

Lisäsin tiedoston sisälle:

```
# Uusi projekti Snow
Lisätty testimuutos Dolly‑tehtävää varten.
```

Tallennetaan muutokset!

```
git add README.md
git commit -m "Lisätty Dolly‑testimuutos README:hen"
```

Lähetetään muutokset Githubiin:

```
git push origin main
```



<img width="626" height="253" alt="Screenshot From 2025-11-23 23-43-07" src="https://github.com/user-attachments/assets/36a301a4-112e-4f52-9b58-570ac5d9145d" />



<img width="912" height="506" alt="Screenshot From 2025-11-23 23-48-38" src="https://github.com/user-attachments/assets/0a187ef0-cfcc-4fd4-8aa1-cfb309fe4f37" />

Näkymä Githubissa!


###### 23:49 

c) Doh! Tee tyhmä muutos gittiin, älä tee commit:tia. Tuhoa huonot muutokset ‘git reset --hard’. Huomaa, että tässä toiminnossa ei ole peruutusnappia.

Avataan README.MD tiedosto, ja kirjoitetaan sinne tekstiä. Ei välttämättä tärkeää.
(Korjattu: 30.11.2025)

nano README.md


<img width="688" height="263" alt="Screenshot From 2025-11-23 23-58-44" src="https://github.com/user-attachments/assets/506440e7-0d1d-4270-9e63-9aab9fa7cba8" />




<img width="687" height="207" alt="Screenshot From 2025-11-24 00-00-17" src="https://github.com/user-attachments/assets/21beea90-c10e-47a6-8cb0-72c286e488c6" />

Tilanne, ilman commitia.

Tuhotaan muutos, komennolla:

```
git reset --hard
```

<img width="687" height="166" alt="Screenshot From 2025-11-24 00-03-01" src="https://github.com/user-attachments/assets/4550ec57-6e9c-4576-b3d5-0c34de2dca01" />

Tiedosto palautettu edelliseen tilaan.

###### 24.11.2025.
###### 0:04 


d) Tukki. Tarkastele ja selitä varastosi lokia. Tarkista, että nimesi ja sähköpostiosoitteesi näkyy haluamallasi tavalla ja korjaa tarvittaessa.

Tarkastan login:

git log

<img width="800" height="259" alt="Screenshot From 2025-11-24 00-09-32" src="https://github.com/user-attachments/assets/475e223a-c98a-4a4d-84a5-e6477ea4a40b" />

Näkymassä on commit-historia:


Seuraavaksi katsoin nimellä että sähköpostilla:

<img width="628" height="95" alt="Screenshot From 2025-11-24 00-11-10" src="https://github.com/user-attachments/assets/8b97cf45-7598-4e0b-bee9-1acd3910a774" />


Kaikki näyttävät olevan oikein, joten en suorita muutoksia globaalisti tai paikallisesti tähän repoon

Globaalisti voisin suorittaa tämän seuraavanlaisesti:

```
git config --global user.name "Joonas Janttonen"
git config --global user.email "bhl862@myy.haaga-helia.fi"
```


Tai tarvittaessa tähän projektiin:

```
git config user.name "Joonas Janttonen"
git config user.email "bhl862@myy.haaga-helia.fi"
```


###### 0:19 


e) Suolattu rakki. Aja Salt-tiloja omasta varastostasi. (Salt tiedostot mistä vain hakemistosta "--file-root teronSaltHakemisto". Esimerkiksi 'sudo salt-call --local --file-root srv/salt/ state.apply', huomaa suhteellinen polku.)

En saanut asennettua Saltia koneelle. Pyydän konsultointia tähän ongelmaan kurssikaverilta.
(Korjattu: 30.11.2025)

f) Vapaaehtoinen: Hae paria projektiin Moodlen keskustelusta. (Parin saa valita, arvon muille parin)

Projektipari on hankittu Moodlen kautta: Oskari Häkämies.



###### 1:15 


g) Vapaaehtoinen: Se toinen järjestelmä: kokeile Gittiä eri käyttöjärjestelmällä kuin sillä, millä teit muut harjoitukset. Selitä niin, että kyseistä järjestelmää osaamatonkin onnistuu. Mahdollisuuksia on runsaasti: Debian, Fedora, Windows, OSX...



<img width="899" height="179" alt="Screenshot From 2025-11-24 01-46-56" src="https://github.com/user-attachments/assets/bb44e98c-fb17-4be5-b030-5589a8884ed9" />


###### 2:07 

<img width="827" height="182" alt="Screenshot From 2025-11-24 02-31-20" src="https://github.com/user-attachments/assets/ea64a8f5-1ff8-4904-8cd6-bf10d35f88cc" />

Tältä näyttä GitHubissa!


Uusi repo Githubiin. Alkuun sisällytin tiedoston tähän, mutta poistin sen. Avain oli jo olemassa Githubissa, joten kloonaaminen onnistui kätevästi.
(Korjattu: 30.11.2025)


```
git clone git@github.com:JoonasJanttonen/yhteisty--repo.git
cd yhteisty--repo
```
h) Vapaaehtoinen: yhteistyötä: anna kaverillesi (tai alter egollesi) oikeus kirjoittaa varastoosi (commit access). Tehkää molemmat muutoksia varastoon gitillä.
Suoritan pääkayttäjan muutoksen:

```
echo "Tämä on pääkäyttäjän muutos" > paakayttaja.txt
git add paakayttaja.txt
git commit -m "Lisätty pääkäyttäjän tiedosto"
git push origin main
```

Tämän jälkeen alter egon:
(Kurssi: 30.11.2025)


```
echo "Tämä on alter egon muutos" > alterego.txt
git add alterego.txt
git commit -m "Lisätty alter egon tiedosto"
git push origin main
```

Pääkayttäjän kävin hakemassa alter egon muutokset:

```
git pull origin main
git log --oneline
```


<img width="751" height="112" alt="Screenshot From 2025-11-24 02-38-42" src="https://github.com/user-attachments/assets/79592cb2-0ebf-4791-af95-0c4d75aed057" />

###### 2:39 
Raportin viimeistelyä
###### 3:14




Lähteet
===

Github 2025. Joonas Janttonen Luettavissa: https://github.com/JoonasJanttonen/Palvelinten-hallinta/blob/main/h4%20Pkg-file-service.md. Luettu: 23.11.2025.

Github 2025. Git add. Luettavissa: https://github.com/git-guides/git-add. Luettu: 23.11.2025. 

Github 2025. Git commit. Luettavissa: https://github.com/git-guides/git-commit. Luettu: 23.11.2025. 

Github 2025. Git Pull. Luettavissa: https://github.com/git-guides/git-pull. Luettu: 23.11.2025.

Github 2025. Luettavissa: https://github.com/terokarvinen/suolax/blob/main/Makefile. Luettu: 23.11.2025. 

Git - distributed-is-the-new-centralized 2025. 1.3 Getting Started - What is Git? Luettavissa: https://git-scm.com/book/en/v2/Getting-Started-What-is-Git%3F. Luettu: 23.11.2025.

Tero Karvinen 2025. Luettavissa: https://terokarvinen.com/palvelinten-hallinta/#laksyt. Luettu: 23.11.2025.

Tero Karvinen 2025. Luettavissa: https://github.com/terokarvinen/suolax/. Luettu: 23.11.2025.
