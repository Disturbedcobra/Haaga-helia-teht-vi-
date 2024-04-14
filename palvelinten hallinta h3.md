#  Tehtävä X lue ja tiivistä

##  Chacon and Straub

  Git ajattelee dataa eri tavalla kuin muut versionhallinta ohjelmat kuten perforce ja subversion.

  Git ajattelua voi verrata sarjaan kuvia tiedostoista.

  Suurin osa Git toiminnasta toimii lokaalisti.

  Git tarkistaa kaiken säilettävän tiedon ennen tallennusta, näin muutoksia ei voi tehdä ilman että Git tietää asiasta.

  Git toimii kolmessa tasossa; modified, staged ja committed.

  Onko Git:illä maksimi depository koko rajaa?

  ##  Git Komennot

  Git add: Lisää nykyisen sisällön staged tasoon seuraavaa committia varten.

  Git commit: Luo uuden commitin, joka sisältää indexin kaiken sisällön sekä viestin kaikista muutoksista sisällössä.

  Git pull: Lisää muutokset etä varastoihin nykyiseen haaraan (branch). 

  Git push: Päivittää etä varaston referenssit käyttäen lokaaleja referenssejä, sekä lähettää tarvittavat objektit referenssin valmistumiselle.

  ##  Varaston Historia

  ensimmäinen muutos yksi poista ja kaksi lisäystä.

  toinen muutos kahteen tiedostoon yhteensä 6 lisäystä.

  neljäs muutos lisää info lisäkomennon sudo salt call komentoon.

  viides muutos lisää favourites tiedoston.

  viimeinen muutos päivittää ohje tiedostoa.

  # Tehtävä A Online

  Loin uuden varaston Githubiin, jonka nimeen ja descriptioon lisäsin sanan summer.

  ![image text](https://github.com/Disturbedcobra/Palvelinten-hallinta-2024/blob/085763f51f15e13b0eafabab6914fffec61ecd80/varasto.png)

  # Tehtävä B Dolly

  Kloonasin luomani varaston omalla tietokoneelleni Git bash sovelluksella. loin uuden teksti tiedoston ja yritin puskea sen Githubiin, mutten ollut vielä tehnyt Author tiliä. käytin komento git config --global user.email sekä user.name luodakseni itselleni author
  käyttäjän ja puskin muutokset Githubiin.

  ![image text](https://github.com/Disturbedcobra/Palvelinten-hallinta-2024/blob/f55a058cffbd661e2ebc461b407bef6b75628ac1/push.png)

#  Tehtävä C Doh!

Tein muutoksen salt.txt tiedostoon ja poistin muutoksen git reset --hard komennolla.

![image text](https://github.com/Disturbedcobra/Palvelinten-hallinta-2024/blob/1ae101a0c1f0399949f67145d3162f8045c5cb86/doh!.jpg)

# Tehtävä D log

Käytin komentoa git log --patch katsoakseni tehtyjä muutoksia. komento kertoo jokaisen muutoksen mitä varastoon on tehty, milloin muutos on tehty sekä kuka on tehnyt muutoksen. esimerkissä käyttäjänimi krizu teki muutoksen sunnuntaina klo 14:33. ilmoitti muutoksen olevan testi puskemiseen. tiedosto jota muutettiin oli salt.txt, johon oli lisätty rivi i made this using git bash.

![image text](https://github.com/Disturbedcobra/Palvelinten-hallinta-2024/blob/5d5a57f9249cb30fe99bcf6430275b8a4de55a86/log.png)

# Tehtävä E suolattu rakki

Tähän tehtävään lainasin opettajan luomaa varastoa. Asensin uudestaan vagrant virtuaalikoneen ja asensin siihen Saltin ja Gitin. Seuraavaksi kloonasin opettajan varaston git clone komennolla. Tämän jälkeen testasin Salt komennon toimivuuden state.single komennolla.

![image text](https://github.com/Disturbedcobra/Palvelinten-hallinta-2024/blob/a7bc6a2d59be279e1c6990f55fcde8c9f31b96e3/saltdog.jpg)

  #  Lähteet

  Git. S.A. 1.3 Getting Started - What is Git?. Luettavissa: https://git-scm.com/book/en/v2/Getting-Started-What-is-Git%3F Luettu: 14.4.2024.

  Git. S.A. git-add - Add file contents to the index. Luettavissa: https://git-scm.com/docs/git-add Luettu: 14.4.2024.

  Git. S.A. git-commit - Record changes to the repository. Luettavissa: https://git-scm.com/docs/git-commit Luettu: 14.4.2024.

  Git. S.A. git-pull - Fetch from and integrate with another repository or a local branch. Luettavissa: https://git-scm.com/docs/git-pull Luettu: 14.4.2024.

  Git. S.A. git-push - Update remote refs along with associated objects. Luettavissa: https://git-scm.com/docs/git-push Luettu: 14.4.2024.

  Karvinen. T. 2024. Commits. Luettavissa: https://github.com/terokarvinen/suolax/commits/main/ Luettu: 14.4.2024.

  Karvinen. T. 2024. Commits. Luettavissa: https://github.com/terokarvinen/suolax/commits/main/ Luettu: 14.4.2024.
  
