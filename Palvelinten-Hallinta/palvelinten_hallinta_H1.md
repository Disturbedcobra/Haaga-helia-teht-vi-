#    Raportti palvelinten hallinta kurssin tehtävä H1

## Tehtävä X lue ja tiivistä

###    Salt
    
- Salt komentoja voi suorittaa lokaalisti ja nähdä tulokset välittömästi.

- Samat Salt komennot toimivat Windows- sekä Linux:illa.

- Tärkeimmät tila funktiot ovat pkg, file, service, user sekä cmd.

- Salt:ia käytetään yleensä kontrolloimaan suuria määriä orja tietokoneita internetin välityksellä.

###    Nettisivu Github:issa

- Rekisteröidy Github:iin ja luo uusi arkisto (repository) sekä uusi .md tiedosto.

- Sivua kirjoittaessa yksi # tekstin edessä luo pää otsikon kaksi # otsikko kakkosen ja niin edelleen.

- Tyhjät rivit luovat kappale välin.

- Commit on sama kuin julkaisu/tallennus.
  
###    Raportin kirjoittaminen

- Toistettuus: Raportissa on tärkeää saada sama lopputulos raportin ohjeita noudettaessa sekä kertoa missä ympäristössä raportti on tehty esim. mikä tietokone

- Täsmällisyys: mitä yksityiskohtaisempi raportti, sitä parempi. Kellonajat, komennot/polut, tulokset vaiheittan, ongelmat, käytetyt työkalut, sekä menneen aikamuodon käyttäminen ovat hyvän raportin merkkejä. 

- Helppolukuisuus: kukaan ei halua lukue tekstiä, jossa ei ole käytetty välejä tai sisältää paljon kirjoitusvirheitä. huomio kirjoitus alusta, tiivistelmä raportin alussa on plussaa.

- Lähteet: Akateeminen ja hyvä käytäntö on lisätä viitauksia raporttiin, näillä myös osoitat että olet perehtynyt alueeseen.

- Vakiotekstit: Lisenssit kuten GNU (General Public License) ja mahdollisten pohjien ilmoitus on suositeltavaa.

- Pahoja mokia: suurimpia virheitä mitä voit tehdä ovat raportointi työstä mitä et ole tehnyt ja muiden kuin oman materiaalin käyttäminen luvatta eli plagioiminen.

##    Tehtävä A Windows Salt

Aloitin tehtävän lataamalla Salt Windows paketin Saltin kotisivustolta (saltproject.io) sivustolta. Seuraavaksi asensin Salt paketin ja testasin toimivuuden admin powershellin avulla käyttämällä versio komentoa salt-call --version.

![image text](https://github.com/Disturbedcobra/Palvelinten-hallinta-2024/blob/883565d351607b399a6f4050245806b87b3bddaf/salt%20windows%20working.png)

##    Tehtävät B & C Vagrant

En ollut asentanut vielä vagranttia pöytäkoneelleni, joten aloitin tehtävän lataamalla vagrant paketin vagrantin kotisivuilta (vagrantup.com). Tämän jälkeen asensin vagrantin ja käynnistin tietokoneeni uudelleen. Kun tietokone oli suorittanut uudelleen käynnistyksen testasin vagrantin toimivuuden init komennolla.

 ![image text](https://github.com/Disturbedcobra/Palvelinten-hallinta-2024/blob/b13ea827ca47c5c4b4965ec8d3d23ee043984f69/vagrant_working.png)

 Kun init komento oli suoritettu ja Vagrantfile tiedosto luotu oikeaan kansioon latasin ja asensin tiedostossa olevan debian virtuaalikoneen vagrant up komennolla. Lopuksi testasin luonnin onnistumisen vagrant ssh komennolla.

 ![image text](https://github.com/Disturbedcobra/Palvelinten-hallinta-2024/blob/1bb1550b41ede6425d14aca1943bd87386d4f893/vagrant%20new%20machine%20working.png)

##   tehtävä A Linux salt

 Aloitin tehtävän avaamalla etäyhteyden debian virtuaalikoneeseen vagrantin kautta vagrant ssh komennolla. Tämän jälkeen päivitin uudet paketit apt-get update komennolla, jonka jälkeen asensin salt-minionin apt-get install salt-minion komennolla. Asennuksen jälkeen testasin toimivuuden tarkistamalla version        salt-call --version komennolla.

![image text](https://github.com/Disturbedcobra/Palvelinten-hallinta-2024/blob/f59c72384ae85487f378fe8f67a60b23dbf37211/salt%20minion%20working.png)

##   tehtävä B Salt viisi tärkeintä

###    pkg

Tehtävää aloittaessa tuli minulla vastaan ongelma, jonka mukaan käyttämmäni debian/bullseye64 virtuaali kone on epäkelvollinen päivityksille vielä kuusi tuntia. En ollut varma miten korjata asiaa, joten päätin kokeilla luoda uuden virtuaali koneen opettajan Vagrant tiedostolla, joka löytyy hänen kotisivujen artikkelista: Two Machine Virtual Network With Debian 11 Bullseye and Vagrant (Karvinen 2021). 

![image text](https://github.com/Disturbedcobra/Palvelinten-hallinta-2024/blob/2cc1f2547f14b6fb2f869ab13a9cd2fbfbb0dd91/vagrant%20salt%20error.jpg)

Tuhottuani vanhan koneen, vaihdoin Vagrantfile tiedoston sisällön ja asensin uuden koneen vagrant up komennolla. päivitin koneen apt-get komennolla ja asensin uudestaan Salt paketin. Tämän jälkeen Salt komento pkg:lle alkoi toimia ilman ongelmia.

Tässä komennossa Salt etsi onko pyydettyä pakettia tree asennettu koneelle, koska paketti löytyi mitään muutoksia ei tehty.

![image text](https://github.com/Disturbedcobra/Palvelinten-hallinta-2024/blob/c252109056b087a115d222cc8657ea20f720df6e/pkg.jpg)

Paketin puuttuessa Salt asensi pyydetyn paketin.

![image text](https://github.com/Disturbedcobra/Palvelinten-hallinta-2024/blob/71a995ab254c050f0c192483a5bf59378ef9e582/pkg%20java.jpg)

###    file

Tehtävässä päätin käyttää esimerkkinä edellisellä tunnilla käytettyä Salt file komentoa. Tässä komennossa paketin asentamisen sijaan pyydetyn tiedon puuttuessa Salt loi uuden tiedoston ja lisä komennolla täyttää tiedoston komennossa annetuilla arvoilla.

![image text](https://github.com/Disturbedcobra/Palvelinten-hallinta-2024/blob/da09532af7694e5660f0b13b59edb68e9470782e/salt%20file.jpg)

###    service

Seuraavaa tehtävää varten asensin apache2 paketin ja ajoin sitten service.running komennon. Tämä komento tarkistaa onko pyydetty palvelu päällä vai pois päältä, koska palvelu onjo päällä mitään ei tapahtunut. Suljettuani palvelun itse ja ajamalla saman komennon uudelleen, Salt käynnisti palvelun.

![image text](https://github.com/Disturbedcobra/Palvelinten-hallinta-2024/blob/9c24c5b6ce2d89a0c83bd2d68c58b20cf738101c/service.running.jpg)

###    user

Salt komennossani user.present, Salt tarkistaa onko pyydettyä käyttäjää olemassa. Käyttäjän löytyessä Salt ei tehnyt mitään, mutta käyttäjän puuttuessa loi Salt pyydetyn käyttäjän.

![image text](https://github.com/Disturbedcobra/Palvelinten-hallinta-2024/blob/481d1da55e4601cf435ea511d93bf5e2814b88d9/user.jpg)

###    cmd

cmd.run komennon toimintaa en ymmärtänyt. kokeilin käyttää erilaisia komentoja kuten ls -la ja touch sekä lisä komentoja creates sekä onlyif, mutta en päässyt jyvälle miten ensimmäinen komento vaikuttaa lisäkomentoon tai toisinpäin.

![image text](https://github.com/Disturbedcobra/Palvelinten-hallinta-2024/blob/acc8ebe0354cb7a8a84948a8d65540741264dc74/cmd.run.jpg)

##    Idempotenssi

Idempotenssin esimerkiksi valitsin sudo salt-call --local -l info state.single file.managed /home/vagrant/moi.txt. tämä komento tarkistaa löytyykö vagrant hakemistosta moi.txt tiedostoa. Ensimmäisellä ajolla tiedostoa ei välttämättä löydy, joten Salt luo tiedoston. Koska tiedosto on nyt luotu ei uusia muutoksia  tulla tekemään vaikka komento ajettaisiin montakin kertaa peräkkäin, ellei tiedostoa poisteta tai muuteta muusta syystä. Näin ollen komento on saavuttanut idempotenssi tilan.

##    Grains

Grains.items tehtävää tehdessäni sain aina vastaukseksi:

[ERROR   ] DNS lookup or connection check of 'Cobra' failed.

[ERROR   ] Master hostname: 'Cobra' not found or not responsive. Retrying in 30 seconds

En ollut varma miten tämä virhe korjataan ja päätin kysyä opettajalta aiheesta seuraavalla tunnilla.

##    Lähteet

Karvinen. T. 2021. Run Salt Command Locally. Luettavissa: https://terokarvinen.com/2021/two-machine-virtual-network-with-debian-11-bullseye-and-vagrant/?fromSearch=debian Luettu: 28.3.2024.

Karvinen. T. 2023. Create a Web Page Using Github. Luettavissa: https://terokarvinen.com/2021/two-machine-virtual-network-with-debian-11-bullseye-and-vagrant/?fromSearch=debian Luettu: 28.3.2024.

Karvinen. T. 2006. Raportin kirjoittaminen. Luettavissa: https://terokarvinen.com/2021/two-machine-virtual-network-with-debian-11-bullseye-and-vagrant/?fromSearch=debian Luettu: 28.3.2024.

Karvinen. T. 2021. Two Machine Virtual Network With Debian 11 Bullseye and Vagrant. Luettavissa: https://terokarvinen.com/2021/two-machine-virtual-network-with-debian-11-bullseye-and-vagrant/?fromSearch=debian Luettu: 29.3.2024.
