# Palvelinten hallinta H6 kotitehtävä

## Tehtävä X lue ja tiivistä windows package manager

- Paketin määritys tiedosto kertoo paketin: koko nimen, version, lataus sijainnin, komentorivi vaihdot sekä käytetäänkö windows tehtävä aikataulutusta asennukseen.

- Windows pakettien hallintaan käytetään winrepo komentoja.

- mestari koneelta ohjattaessa käyetään winminion komentoja.

## Tehtävä A paketti windowsilla

Onnistuin kloonaamaan winrepon ohjeiden mukaan mutta asentaessani sain vain virheen Unable to loacte the package.

![image text](https://github.com/Disturbedcobra/Palvelinten-hallinta-2024/blob/71140aaf10beb9708d3efe0d4696e46cebe1b1e8/salt%20winrepo.jpg)

## Tehtävä B benchmark

En tiennyt mistä löytää lisenssin tehtävää varten jonka vuoksi en lisää sitä listoihin

### Terraria serveri

Tarkoitus: asentaa automaattisesti Terraria serveri tietokoneelle Salt tilalla.

Tekijä ja vuosi: Kristian Koponen 2020

Riippuvuudet: linux käyttöjärjestelmä ja Salt

Kiinnostavaa: hakemiston zippaaminen wget komennon ohitusta varten

huomiot: tmux on hyvä valinta palvelimen käyttöön

### LAMB-stack

Tarkoitus: Asentaa LAMB-stackin, ssh ja ufw sekä konfiguroi asetuksia

Tekijä ja vuosi: Otto Hanninen 2021

Riippuvuudet: Linux ja salt

Kiinnostavaa: tiedostojen luonti eri hakemistoihin, jotta ne on helpompi löytää myöhemmin.

huomiot: onko haaga helian kurssi? Lähteet vain linkkejä.

### steam:

Tarkoitus: Steam asennus automaattisesti

Tekijä ja vuosi: 2021 nemiä en nähnyt raportissa

Riippuvuudet: linux käyttöjärjestelmä ja salt

Kiinnostavaa: ehtojen hyväksyminen saltin avulla

huomiot: raportissa käytetään useaa aikamuotoa.

## TEhtävä C toisen moduulin ajo

päätin yrittää ajaa steam automaatti asennusta. Salt tila lisää tiedostoja sekä asentaa valmiita paketteja cmd.run ja pkg.installed komennoilla, mutta ei näytä lataavan tiedostoja paketinhallinnan ulkopuolelta. koodia ajaessa ongelmia ei tullut vastaan tiedostojen lisäyksessä, mutta asennukset eivät onnistuneet koska steam ja lib paketit ovat lukossa ymmärtääkseni.

![image text](https://github.com/Disturbedcobra/Palvelinten-hallinta-2024/blob/03709ab44eccef142a4ed6e810916041c2d41d55/toisen%20moduuli.jpg)

Tiloja oli yhteensä 13 joista kuusi epäonnistui. Kaikki epäonnistuneet tialt olivat asennus komentoja. 

Tehtävä D viisi ideaa omalle moduulille

1: Minecraft palvelimen automaattinen asennus saltin avulla. voidaan käyttää esimerkiksi minecraft palvelinten ylläpito palveluihin.

2: apache2 valmius automatisointi.

3: paketinhallinnan ulkopuolisen sovelluksen automaattinen asennus

4: automatisoitu salt tilan ajo

5: automatisoitu ylimääräisten sovelluksien poisto saltille

## Lähteet

saltproject. 2024. WINDOWS PACKAGE MANAGER. Luettavissa: https://docs.saltproject.io/en/latest/topics/windows/windows-package-manager.html#list-available Luettu: 5.5.2024.

Koponen. K. 2020. Oma moduli. Luettavissa: https://kopkr.github.io/task-palhal/pages/h7.html Luettu: 5.5.2024.

Hanninen. O. 2021. Configuration Management Systems – Palvelinten Hallinta – Spring 2021 – h7 Oma moduli. Luettavissa: https://ottohanninen.wordpress.com/2021/05/19/configuration-management-systems-palvelinten-hallinta-spring-2021-h7-oma-moduli/ Luettu: 5.5.2024.

S. A. 2021. Palvelinten hallinta harjoitus 7 oma moduli – Spring 2021. Luettavissa: https://myllys.wordpress.com/palvelinten-hallinta-harjoitus-7-oma-moduli-spring-2021/ Luettu: 5.5.2024.
