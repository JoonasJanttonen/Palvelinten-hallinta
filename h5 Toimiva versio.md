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

Virtuaalikone ei kaynnistynyt, joten minun piti luoda kaikki alusta. Kun lahdin poistamaan turhia tiedostoja koneelta, huomasin, etta edellinen Oracle oli kayttanyt yli 18 gt edesta tilaa. Poistin kaikki nama, ja latasin kaikki uudestaan seka tein tarvittavat asennukset ja paivitykset.


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


Gitin käyttö on lähinnä 'git add . && git commit; git pull && git push'. Selitä tuon komennon jokainen osa. Käytä apuna itse valitsemiasi lähteitä ja viittaa niihin.


Git add .  Tarkoittaa, etta kaikki nykyisen hakemiston (ja alihakemistojen) muutetut ja uudet tiedostot staging areaan eli indeksiin. Piste (.) lopussa tarkoittaa nykyista hakemistoa. Lahde: (Git add)



Git commitilla tarkoitus on luoda uusi commit, joka tallentaa snapshotin kaista tiedostoista. Tama (commit) sisaltaa tietdostojen, kuten metatiedot (tekia, aikaleima, viesti ja parent commit). Tama on tarkeaa, koska Commitit muodostavat projektin historian, johon voi halutessaan palata. Lahde: (Git Commit)



Git pull on hakee etärepon (esim. GitHub) uusimmat muutokset ja yhdistää nama. Toimii kahdessa vaiheessa: git fetch – lataa uudet commitit etäreposta.
git merge (tai rebase) – yhdistää ne omaan branchiin. Tama on vitaalia, koska se varmistaa, että oma branch on ajan tasalla ennen pushia. Lahde: (Git Pull)



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


Tassa vaiheessa piti asentaa micro koneelle, jotta voin kirjoittaa README.md ja LICENSE.md

```
sudo apt update
sudo apt install micro
```

Taman jalkeen lisasin ohjeiden mukaisesti snow kuvaukseksi, ja jonka jalkeen ajoin seuraavat komennot:

```
git add .
git commit
git pull
git push
git log --patch
```

<img width="920" height="523" alt="Screenshot From 2025-11-23 22-26-44" src="https://github.com/user-attachments/assets/56144e5d-0fe1-4ab6-9e62-8c97870059df" />

Lopputulos! 

Tama oli hyvaa harjoitusta oppimisen kannalta - toisojen kautta! Taman laksyn apuna kaytin tunnilla ottamini muistiinpanot.

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


Taman jalkeen muokkasin Nanon tiedostoa:

```
nano README.md
```

Lisasin tiedoston sisalle:

```
# Uusi projekti Snow
Lisätty testimuutos Dolly‑tehtävää varten.
```

Tallennetaan muutokset!

```
git add README.md
git commit -m "Lisätty Dolly‑testimuutos README:hen"
```

Lahetetaan muutokset Githubiin:

```
git push origin main
```



<img width="626" height="253" alt="Screenshot From 2025-11-23 23-43-07" src="https://github.com/user-attachments/assets/36a301a4-112e-4f52-9b58-570ac5d9145d" />




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
