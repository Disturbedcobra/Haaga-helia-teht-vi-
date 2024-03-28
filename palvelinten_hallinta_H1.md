# Tehtävä X

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

#    Tehtävä A Windows

Aloitin tehtävän lataamalla Salt Windows paketin Saltin kotisivustolta (saltproject.io) sivustolta. Seuraavaksi asensin Salt paketin ja testasin toimivuuden admin powershellin avulla käyttämällä versio komentoa salt-call --version.

![image text](https://github.com/Disturbedcobra/Palvelinten-hallinta-2024/blob/883565d351607b399a6f4050245806b87b3bddaf/salt%20windows%20working.png)

#    Tehtävä B & C Vagrant

En ollut asentanut vielä vagranttia pöytäkoneelleni, joten aloitin tehtävän lataamalla vagrant paketin vagrantin kotisivuilta (vagrantup.com). Tämän jälkeen asensin vagrantin ja käynnistin tietokoneeni uudelleen. Kun tietokone oli suorittanut uudelleen käynnistyksen testasin vagrantin toimivuuden init komennolla.

 ![image text](https://github.com/Disturbedcobra/Palvelinten-hallinta-2024/blob/b13ea827ca47c5c4b4965ec8d3d23ee043984f69/vagrant_working.png)

 Kun init komento oli suoritettu ja Vagrantfile tiedosto luotu oikeaan kansioon latasin ja asensin tiedostossa olevan debian virtuaalikoneen vagrant up komennolla. Lopuksi testasin luonnin onnistumisen vagrant ssh komennolla.

 ![image text](https://github.com/Disturbedcobra/Palvelinten-hallinta-2024/blob/1bb1550b41ede6425d14aca1943bd87386d4f893/vagrant%20new%20machine%20working.png)

 ¤    tehtävä A Linux salt

 Aloitin tehtävän avaamalla etäyhteyden debian virtuaalikoneeseen vagrantin kautta vagrant ssh komennolla. Tämän jälkeen päivitin uudet paketit apt-get update komennolla, jonka jälkeen asensin salt-minionin apt-get install salt-minion komennolla. Asennuksen jälkeen testasin toimivuuden tarkistamalla version        salt-call --version komennolla.

![image text](https://github.com/Disturbedcobra/Palvelinten-hallinta-2024/blob/f59c72384ae85487f378fe8f67a60b23dbf37211/salt%20minion%20working.png)

#    tehtävä B linux
