# Tehtävä X lue ja tiivistä

##    Salt
    
- Salt komentoja voi suorittaa lokaalisti ja nähdä tulokset välittömästi.

- Samat Salt komennot toimivat Windows- sekä Linux:illa.

- Tärkeimmät tila funktiot ovat pkg, file, service, user sekä cmd.

- Salt:ia käytetään yleensä kontrolloimaan suuria määriä orja tietokoneita internetin välityksellä.

##    Nettisivu Github:issa

- Rekisteröidy Github:iin ja luo uusi arkisto (repository) sekä uusi .md tiedosto.

- Sivua kirjoittaessa yksi # tekstin edessä luo pää otsikon kaksi # otsikko kakkosen ja niin edelleen.

- Tyhjät rivit luovat kappale välin.

- Commit on sama kuin julkaisu/tallennus.
  
##    Raportin kirjoittaminen

- Toistettuus: Raportissa on tärkeää saada sama lopputulos raportin ohjeita noudettaessa sekä kertoa missä ympäristössä raportti on tehty esim. mikä tietokone

- Täsmällisyys: mitä yksityiskohtaisempi raportti, sitä parempi. Kellonajat, komennot/polut, tulokset vaiheittan, ongelmat, käytetyt työkalut, sekä menneen aikamuodon käyttäminen ovat hyvän raportin merkkejä. 

- Helppolukuisuus: kukaan ei halua lukue tekstiä, jossa ei ole käytetty välejä tai sisältää paljon kirjoitusvirheitä. huomio kirjoitus alusta, tiivistelmä raportin alussa on plussaa.

- Lähteet: Akateeminen ja hyvä käytäntö on lisätä viitauksia raporttiin, näillä myös osoitat että olet perehtynyt alueeseen.

- Vakiotekstit: Lisenssit kuten GNU (General Public License) ja mahdollisten pohjien ilmoitus on suositeltavaa.

- Pahoja mokia: suurimpia virheitä mitä voit tehdä ovat raportointi työstä mitä et ole tehnyt ja muiden kuin oman materiaalin käyttäminen luvatta eli plagioiminen.

#    Tehtävä A Windows Salt

Aloitin tehtävän lataamalla Salt Windows paketin Saltin kotisivustolta (saltproject.io) sivustolta. Seuraavaksi asensin Salt paketin ja testasin toimivuuden admin powershellin avulla käyttämällä versio komentoa salt-call --version.

![image text](https://github.com/Disturbedcobra/Palvelinten-hallinta-2024/blob/883565d351607b399a6f4050245806b87b3bddaf/salt%20windows%20working.png)

#    Tehtävät B & C Vagrant

En ollut asentanut vielä vagranttia pöytäkoneelleni, joten aloitin tehtävän lataamalla vagrant paketin vagrantin kotisivuilta (vagrantup.com). Tämän jälkeen asensin vagrantin ja käynnistin tietokoneeni uudelleen. Kun tietokone oli suorittanut uudelleen käynnistyksen testasin vagrantin toimivuuden init komennolla.

 ![image text](https://github.com/Disturbedcobra/Palvelinten-hallinta-2024/blob/b13ea827ca47c5c4b4965ec8d3d23ee043984f69/vagrant_working.png)

 Kun init komento oli suoritettu ja Vagrantfile tiedosto luotu oikeaan kansioon latasin ja asensin tiedostossa olevan debian virtuaalikoneen vagrant up komennolla. Lopuksi testasin luonnin onnistumisen vagrant ssh komennolla.

 ![image text](https://github.com/Disturbedcobra/Palvelinten-hallinta-2024/blob/1bb1550b41ede6425d14aca1943bd87386d4f893/vagrant%20new%20machine%20working.png)

#    tehtävä A Linux salt

 Aloitin tehtävän avaamalla etäyhteyden debian virtuaalikoneeseen vagrantin kautta vagrant ssh komennolla. Tämän jälkeen päivitin uudet paketit apt-get update komennolla, jonka jälkeen asensin salt-minionin apt-get install salt-minion komennolla. Asennuksen jälkeen testasin toimivuuden tarkistamalla version        salt-call --version komennolla.

![image text](https://github.com/Disturbedcobra/Palvelinten-hallinta-2024/blob/f59c72384ae85487f378fe8f67a60b23dbf37211/salt%20minion%20working.png)

#    tehtävä B Salt viisi tärkeintä

##    pkg

tehtävää aloittaessa tuli minulla vastaan ongelma, jonka mukaan käyttämmäni debian/bullseye64 virtuaali kone on epäkelvollinen päivityksille vielä kuusi tuntia. En ollut varma miten korjata asiaa, joten päätin kokeilla luoda uuden virtuaali koneen opettajan Vagrant tiedostolla, joka löytyy hänen kotisivujen artikkelista: Two Machine Virtual Network With Debian 11 Bullseye and Vagrant (Karvinen 2021). 

![image text](https://github.com/Disturbedcobra/Palvelinten-hallinta-2024/blob/2cc1f2547f14b6fb2f869ab13a9cd2fbfbb0dd91/vagrant%20salt%20error.jpg)

Tuhottuani vanhan koneen, vaihdoin Vagrantfile tiedoston sisällön ja asensin uuden koneen vagrant up komennolla. päivitin koneen apt-get komennolla ja asensin uudestaan Salt paketin. tämän jälkeen Salt komento pkg:lle alkoi toimia ilman ongelmia.

![image text](https://github.com/Disturbedcobra/Palvelinten-hallinta-2024/blob/c252109056b087a115d222cc8657ea20f720df6e/pkg.jpg)

tässä komennossa Salt etsii onko pyydettyä pakettia tree asennettu koneelle, jos paketti löytyy mitään muutoksia ei tehdä, mutta paketin puuttuessa 

#    Lähteet

Karvinen. T. 2021. Run Salt Command Locally. Luettavissa: https://terokarvinen.com/2021/two-machine-virtual-network-with-debian-11-bullseye-and-vagrant/?fromSearch=debian Luettu: 28.3.2024.

Karvinen. T. 2023. Create a Web Page Using Github. Luettavissa: https://terokarvinen.com/2021/two-machine-virtual-network-with-debian-11-bullseye-and-vagrant/?fromSearch=debian Luettu: 28.3.2024.

Karvinen. T. 2006. Raportin kirjoittaminen. Luettavissa: https://terokarvinen.com/2021/two-machine-virtual-network-with-debian-11-bullseye-and-vagrant/?fromSearch=debian Luettu: 28.3.2024.

Karvinen. T. 2021. Two Machine Virtual Network With Debian 11 Bullseye and Vagrant. Luettavissa: https://terokarvinen.com/2021/two-machine-virtual-network-with-debian-11-bullseye-and-vagrant/?fromSearch=debian Luettu: 29.3.2024.
