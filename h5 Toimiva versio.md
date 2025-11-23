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


git add .  Tarkoittaa, etta kaikki nykyisen hakemiston (ja alihakemistojen) muutetut ja uudet tiedostot staging areaan eli indeksiin. Piste (.) lopussa tarkoittaa nykyista hakemistoa. Lahde: (Git add)


git commitilla tarkoitus on luoda uusi commit, joka tallentaa snapshotin kaista tiedostoista. Tama (commit) sisaltaa tietdostojen, kuten metatiedot (tekia, aikaleima, viesti ja parent commit). Tama on tarkeaa, koska Commitit muodostavat projektin historian, johon voi halutessaan palata. Lahde: (Git Commit)


git pull on hakee etärepon (esim. GitHub) uusimmat muutokset ja yhdistää nama. Toimii kahdessa vaiheessa: git fetch – lataa uudet commitit etäreposta.
git merge (tai rebase) – yhdistää ne omaan branchiin. Tama on vitaalia, koska se varmistaa, että oma branch on ajan tasalla ennen pushia. Lahde: (Git Pull)




Lähteet
===

Github 2025. Joonas Janttonen Luettavissa: https://github.com/JoonasJanttonen/Palvelinten-hallinta/blob/main/h4%20Pkg-file-service.md. Luettu: 23.11.2025.

Github 2025. Git add. Luettavissa: https://github.com/git-guides/git-add. Luettu: 23.11.2025. 

Github 2025. Git commit. Luettavissa: https://github.com/git-guides/git-commit. Luettu: 23.11.2025. 

Github 2025. Git Pull. Luettavissa: https://github.com/git-guides/git-pull. Luettu: 23.11.2025.

Git - distributed-is-the-new-centralized 2025. 1.3 Getting Started - What is Git? Luettavissa: https://git-scm.com/book/en/v2/Getting-Started-What-is-Git%3F. Luettu: 23.11.2025.

Tero Karvinen 2025. Luettavissa: https://terokarvinen.com/palvelinten-hallinta/#laksyt. Luettu: 23.11.2025.
