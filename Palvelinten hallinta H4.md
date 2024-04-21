# Demoni

## Tehtävä X lue ja tiivistä

### IaC & Top.sls

IaC eli infraa koodilla voidaan käyttää useiden tila komentojen suoritukseen kaikille orjille samaan aikaan valmiiksi kirjoitetun tekstitiedoston avulla nopeasti. Top tiedostolla voidaan myös määrittää kaikki IaC tiedostot, jotka halutaan suoritettavaksi ilman että komentorivissä tarvitsee niitä mainita.

### YAML

- YAML on Saltin oletus renderöinti kieli.
- Kirjoituksessa ei saa käyttää TAB:ia vain välilyöntejä.
- Kommentit alkavat # merkillä

YAML perustuu kolmeen perus elementtiin, jotka ovat:

Skalaarit: Yksi avain, jonka arvo voi olla numero, merkkijono tai boolean arvo.

Listat: Avainta seuraa lista arvoja, jonka jokainen arvo merkitään omalle rivilleen kahdella välilyönnillä sekä yhdellä väliviivalla.

Sanakirjat: Kokoelma skalaareita sekä listoja.

YAML on organisoitu palikka rakenteeseen, jossa kaksi välilyöntiä on standardi, mutta yksi tai enemmän toimii myös.

### PKG-File-Service

Yleinen kaava konfiguraatio hallinta järjestelmälle. Asenna sovellus, korvaa konfigurointi tiedosto ja käynnistä demoni uudestaan käyttääksesi uutta konfigurattiota.

### Silmäile Tilafunktiota pkg, file ja service

- pkg.installed varmistaa onko paketti asennettu. pkg.purged varmistaa että paketti on poistettu kaikkien tiedostojensa kanssa. pkgs lisä arvoa voidaan käyttää useamman sovelluksen asentamiseen yhtä listaa käyttäen.
- file.managed käytetään tarkistamaaan että halutut tiedostot luodaan/on luotu sekä sisältävät vaaditun tiedon. file.absent varmistaa että pyydetty tiedosto on poistettu/poistetaan. file.symlink käytetään kun halutaan luoda linkkitiedosto.
- service.running tarkistaa/käynnistää onko haluttu palvelu päällä. service.dead varmistaa että palvelu on suljettu. service.enabled varmistaa että palvelu käynnistetään kun tietokone käynnistetään.

## Tehtävä A Hello SLS

Aloitin tehtävän asentamalla Salt:in sudo apt-get install salt-minion komennolla. tämän jälkeen loin uuden kansion /srv/salt hakemiston alle nimellä apache seuraavia tehtäviä varten. seuraavaksi avasin uuden tekstitiedoston sudoedit /srv/salt/apache/init.sls komennolla ja kirjoitin Nanolla file.managed tilakomennon Hello nimellä.

![image text](https://github.com/Disturbedcobra/Palvelinten-hallinta-2024/blob/9a27bc5c7b3f4bf36fc07297729588ec068d6c47/hello%20sls.png)

## Tehtävä B Top.SLS

Loin uuden kansion nimeltä "tree" salt hakemiston alle, jonka jälkeen loin uuden tila tiedoston pkg.installed komennolla. Tämän jälkeen käytin komentoa sudoedit /srv/salt/top.sls luodakseni tpo tiedoston johon kirjoitin suoritettaviksi komennoiksi apache ja tree kansiot.

![image text](https://github.com/Disturbedcobra/Palvelinten-hallinta-2024/blob/5384dff47dddc62c1d0cc87290332b46a1f27c65/top%20sls.jpg)

## Tehtävä C Asenna apache, korvaa testisivu ja varmista että demoni käynnistyy

Tyhjensin luomani init.sls tiedoston apache kansiossa ja kirjoitin pkg.isntalled, file.managed sekä service.running komennot. Testasin jokaisen rivin jälkeen koodin toimivuuden.

![image text](https://github.com/Disturbedcobra/Palvelinten-hallinta-2024/blob/7b4888c2ff4ca16ababda3b37c379188d19f62cf/apache%20init.jpg)

Loin myös /srv/salt/apache hakemistoon index.html tiedoston, johon hain template koodin verkosta päästäkseni testaamaan koodia nopeammin. tämän jälkeen testasin koodin toimivuuden

![image text](https://github.com/Disturbedcobra/Palvelinten-hallinta-2024/blob/7b4888c2ff4ca16ababda3b37c379188d19f62cf/easy%20apache.jpg)

## Tehtävä D SSHouto

Tein uuden kansion /srv/salt hakemiston alle nimellä sshd. Tämän jälkeen tarkistin sshd_config tiedoston sijainnin. Loin uuteen hakemistoon uuden init.sls tiedoston ja kirjoitin seuraavat rivit ja testasin.

![image text](https://github.com/Disturbedcobra/Palvelinten-hallinta-2024/blob/24461835b9c497651115433ab9841194ec738454/ssh%20init.jpg)

![image text](https://github.com/Disturbedcobra/Palvelinten-hallinta-2024/blob/9969e0975fd776d50a973095505f58f2abfb7044/ssh%20wrok.jpg)

# Lähteet

Karvinen. T. 2023. Salt Vagrant - automatically provision one master and two slaves. Luettavissa: https://terokarvinen.com/2023/salt-vagrant/#infra-as-code---your-wishes-as-a-text-file Luettu: 21.4.2024.

Salt Project. S.A. 2023. Salt overview. Luettavissa: https://docs.saltproject.io/salt/user-guide/en/latest/topics/overview.html#rules-of-yaml Luettu: 21.4.2024.

Karvinen. T. 2018. Pkg-File-Service – Control Daemons with Salt – Change SSH Server Port. Luettavissa: https://terokarvinen.com/2018/04/03/pkg-file-service-control-daemons-with-salt-change-ssh-server-port/?fromSearch=karvinen%20salt%20ssh Luettu: 21.4.2024.
