# Oma moduuli H7 minecraft palvelin

## Tarkoitus

Luodaan Minecraft palvelin paketti, jonka ajettua käyttäjä olisi valmis pelaamaan minecraftiä välittömästi.

Tekijä: Kristian Turkki. Lisenssi GNU v.3

Linkki moduulin tiedostoihin: https://github.com/Disturbedcobra/oma-moduuli/tree/main

## vaatimukset

Linux käyttöjärjestelmä sekä mieluusti vähintään 4GB vapaata ram muistia.

### Manuaalinen asennus

Ensinmmäisenä asensin ufw palomuurin sudo apt-get install ufw komennolla sekä avasin portin 25565. Minecraft käyttää kyseistä porttia palvelimillaan. (käytä find -printf '%T+ %p\n'|sort komentoa nähdäksesi mitä tiedostoja komento muokkaa. Näitä tarvitaan myöhemmin.)

![image text](https://github.com/Disturbedcobra/Palvelinten-hallinta-2024/blob/0c05292c0e1e8380b14dc719283839055790c79e/ufw%20port.jpg)

Tarvitaan myös Java Runtime Environment, asensin sen komennolla sudo apt-get install openjdk-17-jre-headless.

Seuraavaksi latasin minecraft palvelimen. Halusin ladata sen valmiiksi automaation kansioon, joten latasin sen hakemistoon /srv/salt/minecraft/server. lataus komento on wget https://launcher.mojang.com/v1/objects/a37bdd5210137354ed1bfe3dac0a5b77fe08fe2e/server.jar tai sudo wget https://launcher.mojang.com/v1/objects/a37bdd5210137354ed1bfe3dac0a5b77fe08fe2e/server.jar jos lataat muualle kuin käyttäjän hakemistoon.

Koska palvelimen mukana ei ole käynnistys komentoa loin uuden skriptin, joka käyttää javaa palvelimen ajamiseen sekä haluamaani määrää muistia.

![image text](https://github.com/Disturbedcobra/Palvelinten-hallinta-2024/blob/d03ef98de49a954c74a63051984dd13d4bcca50d/skripti%20server.jpg)

Ajoin komennon kerran, jotta sain palvelimen purettua. Seuraavaksi avasin eula.txt ja muutin false kohdan True

![image text](https://github.com/Disturbedcobra/Palvelinten-hallinta-2024/blob/5cd1a9b2f5d89bcd0d40118fa84cebd53671be46/eula.jpg)

Tämän jälkeen serverin olisi pitänyt toimia, mutta kun yritin löytää palvelinta minecraftissä, alkoi palvelin lähettämään minulle loputtomasti samaa virhettä "java.lang.runtimeexception unable to access address of buffer". Sain sen kumminkin korjattua muuttamalla use-native-transport kohdan falseksi.

![image text](https://github.com/Disturbedcobra/Palvelinten-hallinta-2024/blob/49dae75a9a0ab7eb678d5b811c2b8f9a72378ffa/server.properties.jpg)

Nyt palvelin toimii.

![image text](https://github.com/Disturbedcobra/Palvelinten-hallinta-2024/blob/99f7535998b6d70befffbdd670c5fbe8c15a2b64/server%20works.jpg)

### Automatisointi Saltilla

Nyt tehdään asennuksesta automatisoitu Saltin avulla.

Ensimmäisenä kirjoitin mitkä paketit halutaan asentaa palvelimelle.

![image text](https://github.com/Disturbedcobra/Palvelinten-hallinta-2024/blob/8b79a34230541ec1d5720b895047936e70c4557d/h7%20packages.jpg)

Seuraavaksi kopioin muokatut ufw säännöt salt kansioon. nämä saatiin selville uutta porttia avatessa. 

![image text](https://github.com/Disturbedcobra/Palvelinten-hallinta-2024/blob/cd0183f78fb618414a86cae917c98a3c8cee8440/user%20rules.jpg)

Sitten lisätään kopioidut säännöt file.managed komennolla Salt tilaan.

![image text](https://github.com/Disturbedcobra/Palvelinten-hallinta-2024/blob/fb2895e76b546af37933fba15485b81f3b716efc/h7%20rules.jpg)

Lopuksi lisäsin minecraft palvelin hakemiston salt tilaan. 

![image text](https://github.com/Disturbedcobra/Palvelinten-hallinta-2024/blob/74b00b40141d6d8ab01c10a30ce303993c3a4a38/h7%20minecraft%20init.jpg)

Tältä salt tila näytti muutaman ajon jälkeen.

![image text](https://github.com/Disturbedcobra/Palvelinten-hallinta-2024/blob/2b8c927354e67143cb9adc4822488d742e3bf780/h7%20state.apply.jpg)

Varmistukseksi ajoin vielä uudessa hakemistossa olevan palvelimen ja liityin palvelimelle minecraftin sisällä

![image text](https://github.com/Disturbedcobra/Palvelinten-hallinta-2024/blob/2b8c927354e67143cb9adc4822488d742e3bf780/h7%20project%20done.jpg)

## Lähteet

Ionos. 2023. How to setup minecraft server on linux. Luettavissa: https://www.ionos.com/digitalguide/server/know-how/minecraft-server-linux/ Luettu: 12.5.2024.

MCversions.net. S.A. download minecraft 1.8.2. Luettavissa: https://mcversions.net/download/1.8.2 Luettu: 12.5.2024.

Karvinen. T. 2024. Infra as code- Palvelinten Hallinta 2024. Luettavissa: https://terokarvinen.com/2024/configuration-management-2024-spring/ Luettu: 12.5.2024.
