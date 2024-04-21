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

### 

f

## Tehtävä A Hello SLS

Aloitin tehtävän asentamalla Salt:in sudo apt-get install salt-minion komennolla. tämän jälkeen loin uuden kansion /srv/salt hakemiston alle nimellä apache seuraavia tehtäviä varten. seuraavaksi avasin uuden tekstitiedoston sudoedit /srv/salt/apache/init.sls komennolla ja kirjoitin Nanolla file.managed tilakomennon Hello nimellä.

![image text](https://github.com/Disturbedcobra/Palvelinten-hallinta-2024/blob/9a27bc5c7b3f4bf36fc07297729588ec068d6c47/hello%20sls.png)

# Lähteet

Karvinen. T. 2023. Salt Vagrant - automatically provision one master and two slaves. Luettavissa: https://terokarvinen.com/2023/salt-vagrant/#infra-as-code---your-wishes-as-a-text-file Luettu: 21.4.2024.

Salt Project. S.A. 2023. Salt overview. Luettavissa: https://docs.saltproject.io/salt/user-guide/en/latest/topics/overview.html#rules-of-yaml Luettu: 21.4.2024.

Karvinen. T. 2018. Pkg-File-Service – Control Daemons with Salt – Change SSH Server Port. Luettavissa: https://terokarvinen.com/2018/04/03/pkg-file-service-control-daemons-with-salt-change-ssh-server-port/?fromSearch=karvinen%20salt%20ssh Luettu: 21.4.2024.
