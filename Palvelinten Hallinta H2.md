#  Tehtävien hallinta harjoitus 2

##  Tehtävä X Tiivistä

### Two machines

  - Luo kaksi virtuaalikonetta samaa aikaa.

  - Koneet voivat ottaa yhteyden toisiinsa.

  - Vagrant Destroy komento tuhoaa myös molemmat.

  - Havainto: voit itse valita koneiden ip osoitteet jo vagrantfile tiedostossa.

###  Salt quickstart

  - Salt orjat voivat olla missä vain sekä myös palomuurien takana kontrolloidessa.

  - Vain orja tarvitsee mestarin ip osoitteen. Mestari ei tarvitse orjien.

  - Orja avain tarvitsee hyväksyä vain kerran.

  - Havainto: hostname -I komento ei ole yhtä luotettava kuin ip address.

### Hello salt

  - Saltille voi kirjoittaa komentoja myös valmiiksi tekstitiedostoon.

  - Saltilla on oma kieli mitä käytetään infraa tekstissä.

  - Teksti komennotkin pyrkivät pääsemään harmooniseen tilaan idempotenssi koodin avulla.

  - Havainto: Saltin oma kieli vaikuttaa yksinkertaisemmalta kuin single.state koodit.

## Tehtävä A Kaksi konetta

Aloitin tehtävän Muuttamalla vagrantfile tiedoston sisällön tunnilla näytettyyn muotoon.

![image text](https://github.com/Disturbedcobra/Palvelinten-hallinta-2024/blob/f4824e245ab0b394dbb83faa858f281afa586ee3/VagrantfileH2.png)

Tämän jälkeen syötin vagrant up komennon ja yhdistin ssh yhteyden koneeseen, jonka nimi on t001. testasin toisenkin koneen toimivuuden pingaamalla t002 koneen ip osoitetta t001 koneen sisällä.

![image text](https://github.com/Disturbedcobra/Palvelinten-hallinta-2024/blob/21f357c9516cc2294c134124407cedccae296293/ping%20machine.png)

## Tehtävä B ja C Salt master-orja suhde verkon yli

Asensin molemmille koneille Saltin, t001 master version ja t002 koneelle minion version. muutin minion koneessa tietoja sudoedit /etc/salt/minion komennolla ja lisäsin master koneen osoitteen sekä minion koneen nimen.

Seuraavaksi vaihdoin ssh yhteyden master koneeseen ja hyväksyin minion koneen avaimen master koneeseen komennolla sudo salt-key -A. Varmistin vielä toimivuuden lähettämällä state.single komennon master koneelta minion koneellle.

![image text](https://github.com/Disturbedcobra/Palvelinten-hallinta-2024/blob/e23e0fdef9721f412aef185070e07b84db4bcad6/master-slave.png)

## Tehtävä D Idempotentti komennot

Nyt kun yhteys oli varmistettu toimivaksi aloin syöttämään useampia erilaisia komentoja orja koneelle master koneelta. Pkg komennon lisäksi testasin muunmuassa file.managed ja service.running 

![image text](https://github.com/Disturbedcobra/Palvelinten-hallinta-2024/blob/e20e383aaece10f064db309ed83b518aa0735e6b/idempotentit.jpg)

##  Tehtävä E Grains.item verkon yli

Grains.items komentoa testatessani päätin valita useamman kuin yhden tiedon keräämisen yhdellä komennolla ja valitsin prosessorin mallin ja kernel tyypin.

![image text](https://github.com/Disturbedcobra/Palvelinten-hallinta-2024/blob/a31577a9450103be6a38d59024d0be5e2dbba129/grains.item.png)

## Tehtävä F IaC

Tälle tehtävälle käytin pohjana opettajan nettisivun artikkelista löytyviä komentoja. tarkistaessani komennon toimintaa käytin file.amanaged komentoa verkon yli.

![image text](https://github.com/Disturbedcobra/Palvelinten-hallinta-2024/blob/dfc9d981f9f7e7816d89990e9f3c973eacb79d46/iac.png)

#  Lähteet

Karvinen. T. 2021. Two Machine Virtual Network With Debian 11 Bullseye and Vagrant. Luettavissa: https://terokarvinen.com/2021/two-machine-virtual-network-with-debian-11-bullseye-and-vagrant/ Luettu: 4.4.2024.

Karvinen. T. 2018. Salt Quickstart – Salt Stack Master and Slave on Ubuntu Linux. Luettavissa: https://terokarvinen.com/2018/salt-quickstart-salt-stack-master-and-slave-on-ubuntu-linux/?fromSearch=salt%20quickstart%20salt%20stack%20master%20and%20slave%20on%20ubuntu%20linux Luettu: 4.4.2024.

Karvinen. T. 2024. Hello Salt Infra-as-Code. Luettavissa: https://terokarvinen.com/2024/hello-salt-infra-as-code/ Luettu: 4.4.2024.
