peli palvelimen automatisoitu valmisteleminen tekeminen saltilla moduuliin kuuluu:

- palvelimen käyttämien porttien avaaminen

- tarvittavien pakettien lataaminen

- server paketin lataus

- server konfiguraatio tiedostojen muokkaukset valmiina

- server käynnistys skripti

  moduulin riippuvuuksiin kuuluu linux käyttöjärjestelmä ja salt sovelluksen valmius

  kiinnostavia kohtia moduulissa on valmiin kansio paketin automatisointi saltille sekä porttien avaus

  file.recurse
  - source: 
  include_empty: True
