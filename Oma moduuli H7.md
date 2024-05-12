# Oma moduuli H7 minecraft palvelin

## Tarkoitus

Luodaan Minecraft palvelin paketti, jonka ajettua käyttäjä olisi valmis pelaamaan minecraftiä välittömästi.

Tekijä: Kristian Turkki. Lisenssi GNU v.3

## vaatimukset

Linux käyttöjärjestelmä sekä mieluusti vähintään 4GB vapaata ram muistia.

### Manuaalinen asennus

Ensinmmäisenä asensin ufw palomuurin sudo apt-get install ufw komennolla sekä avasin portin 25565. Minecraft käyttää kyseistä porttia palvelimillaan.

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

Seuraavaksi tehdään asennuksesta automatisoitu Saltin avulla.

Ensimmäisenä kopiodaan muokatut ufw säännöt salt kansioon. nämä saatiin selville uutta porttia avatessa

![image text](https://github.com/Disturbedcobra/Palvelinten-hallinta-2024/blob/5cd1a9b2f5d89bcd0d40118fa84cebd53671be46/eula.jpg)
![image text](https://github.com/Disturbedcobra/Palvelinten-hallinta-2024/blob/5cd1a9b2f5d89bcd0d40118fa84cebd53671be46/eula.jpg)
## Lähteet

Ionos. 2023. How to setup minecraft server on linux. Luettavissa: https://www.ionos.com/digitalguide/server/know-how/minecraft-server-linux/ Luettu: 12.5.2024.

MCversions.net. S.A. download minecraft 1.8.2. Luettavissa: https://mcversions.net/download/1.8.2 Luettu: 12.5.2024.

Karvinen. T. 2024. Infra as code- Palvelinten Hallinta 2024. Luettavissa: https://terokarvinen.com/2024/configuration-management-2024-spring/ Luettu: 12.5.2024.
