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

- 









1.3 Getting Started - What is Git?




Lähteet
===

Github 2025. Joonas Janttonen Luettavissa: https://github.com/JoonasJanttonen/Palvelinten-hallinta/blob/main/h4%20Pkg-file-service.md. Luettu: 23.11.2025.

Git - distributed-is-the-new-centralized 2025. 1.3 Getting Started - What is Git? Luettavissa: https://git-scm.com/book/en/v2/Getting-Started-What-is-Git%3F. Luettu: 23.11.2025.

Tero Karvinen 2025. Luettavissa: https://terokarvinen.com/palvelinten-hallinta/#laksyt. Luettu: 23.11.2025.
