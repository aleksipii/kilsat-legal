---
layout: page
title: Tietosuojaseloste (Android)
permalink: /android/tietosuojaseloste/
---

# Tietosuojaseloste (Kilsat / Ajopäiväkirja — Android)

**Viimeksi päivitetty:** 8.8.2026  
**Versio:** Android v1.2.1  
**Tukiosoite:** kilsat.tuki@gmail.com

---

## 0. Ei yhteyttä Verohallintoon tai muihin viranomaisiin

**Kilsat ei ole Verohallinnon, muun veroviranomaisen tai julkisen tahon sovellus, eikä sillä ole mitään virallista, kaupallista tai muuta yhteyttä, kumppanuutta, hyväksyntää tai suositusta Verohallinnolta tai muulta viranomaiselta.** Sovellus on yksityisen kehittäjän riippumattomasti tuottama työkalu. Käyttäjä vastaa itse siitä, että hänen kirjaamansa tiedot ja niiden käyttö verotuksessa tai kirjanpidossa täyttävät sovellettavat vaatimukset.

---

## 1. Rekisterinpitäjä ja roolit

| Rooli | Kuka |
|-------|------|
| Matka- ja ajotiedot | Käyttäjä itse. Tiedot tallennetaan käyttäjän laitteelle; käyttäjä päättää poistosta, muokkauksesta ja viennistä. |
| Sovellus ja tietosuoja-asiat | Kilsat-sovelluksen kehittäjä (yksityinen kehittäjä). Kehittäjä ei ylläpidä pilvipalvelua eikä vastaanota käyttäjän matkalistaa omille palvelimilleen. |

Kilsat on paikallinen työkalu ajopäiväkirjan pitoon. Kehittäjä käsittelee vain sellaisia tietoja, joita käyttäjä välittää tukiyhteydenottoa koskien.

---

## 2. Mitä tietoja käsitellään

Sovellus voi tallentaa ja näyttää käyttäjän laitteella seuraavia tietoja:

- ajon aloitus- ja lopetusaika
- ajettu matka kilometreinä (GPS-mittaus tai manuaalinen syöttö)
- matkan luokittelu (työajo tai yksityisajo), matkan tarkoitus ja valinnainen lisätieto
- matkan alku- ja loppukoordinaatit (GPS-matkoilla)
- manuaalisesti syötetyt lähtö- ja kohdeosoitteet
- käyttäjän suosikkiosoitteet (nimi, osoite, koordinaatit, valinnainen koti- tai työpaikka-merkintä)
- käyttäjän suosikkiautot (nimi, rekisterinumero)
- matkaan lukittu kilometrikorvaus ja siitä johdettu korvaussumma
- matkaan lukittu rekisterinumero (tallennetaan matkaan tallennushetkellä)
- käyttäjän itse syöttämät raportointitiedot (esim. kuljettajan nimi, oletusrekisterinumero, oletustarkoitus)
- valinnainen matkamittarin lukema manuaalisessa matkassa (käyttäjän itse syöttämä muistiinpano; **ei vaikuta korvauslaskentaan**)

Lisäksi sovellus tallentaa laitteelle asetusarvoja (esim. oletuskilometrikorvaus, onboarding-hyväksyntä, Plus-/auto-trip-asetukset). Näitä ei lähetetä kehittäjän palvelimelle.

**Ei käytössä:** pilvisynkronointi, käyttäjätilit tai kehittäjän pilvitietokanta. Matkatiedot eivät synkronoidu Google Drive -varmuuskopioon.

**Widget:** Kotinäytön Glance-widget näyttää paikallisen ajotilan (km / korvaus). Tiedot jaetaan pääsovelluksen ja widgetin välillä **vain laitteella**.

**Kilsat Plus (valinnainen tilaus):** Valinnainen **Kilsat Plus** -kuukausitilaus (Google Play). Plus sisältää mm. automaattisen matkan tunnistuksen, ajon aikaisen etualan ilmoituksen ja 4 min pysähdysmuistutuksen. Tilaus käsitellään Google Play Billingin kautta; kehittäjä ei vastaanota maksukorttitietoja.

**Kilsat Plus -tilaus ja tietosuoja:**

| Tieto | Käsittely |
|-------|-----------|
| Maksu ja laskutus | Google Play. Kehittäjä ei näe maksukortti-, pankki- tai Google-tilin salasanatietoja. |
| Tilausoikeus | Sovellus tarkistaa paikallisesti Play Billingistä, onko Plus aktiivinen. |
| Ostotapahtumat | Google käsittelee maksut. Kehittäjä ei ylläpidä erillistä tilausrekisteriä omilla palvelimillaan. |
| Palauta ostokset | Käyttää Google Play Billing -palvelua. |

Tilauksen ehdot (hinta, kokeilu, uusiminen, peruutus): ks. [Käyttöehdot](Kayttoehdot.md) kohta **8.2**.

**Liike- ja automatiikka (Plus):** Automaattisen matkan tunnistus voi käyttää Google Play **Activity Recognition** -signaalia GPS-nopeuden tukena, jos Google Play -palvelut ovat saatavilla. Ilman GMS:ää tilakone toimii pelkällä GPS-nopeudella. Data käsitellään vain laitteella.

**Autoyhteys (Plus):** Sovellus voi paikallisesti tunnistaa Bluetooth-äänireitin tai Android Auto -tilan. Tieto ei poistu laitteelta. Tätä käytetään yhdessä liiketunnistuksen kanssa GPS-primauksen päätöksiin (ks. kohta 3).

**Käynnistyksen ja pysäytyksen tarkennukset (Plus):** Automaattisen matkan käynnistys- ja lopetuslogiikkaa on tarkennettu liikennetilanteita paremmin huomioivaksi. Kaikki päättely tapahtuu laitteella; mitään näistä tiedoista ei lähetetä kehittäjälle.

- **Kumulatiivinen käynnistys:** Lyhyet pysähdykset (esim. punaiset liikennevalot, ruuhka) eivät nollaa kertynyttä liikeaikaa matkan käynnistyksessä.
- **Autoyhteys nopeuttaa käynnistystä:** Kun puhelin on yhteydessä autoon (Bluetooth-audio tai Android Auto / USB), matka voi käynnistyä nopeammin kuin ilman yhteyttä.
- **Käynnistys ilman autoyhteyttä (selkeä ajo):** Jos Activity Recognition tai Android Auto ei ole käytettävissä (yleistä monilla Samsung- ja muilla OEM-laitteilla), sovellus voi silti käynnistää matkan GPS:n perusteella, kun ajat selvästi — tyypillisesti noin **12 km/h vähintään noin 1,5 minuuttia**, tai **heti noin 25 km/h** nopeudella. Kävely ei yleensä täytä tätä kynnystä.
- **Yhteyskatkoksen pikatallennus:** Kun automaattinen matka on käynnissä ja vahva autoyhteys (esim. Android Auto / auton Bluetooth) katkeaa alhaisella nopeudella (esim. pysäköinti ja auton sammutus), sovellus voi tallentaa matkan tavanomaista nopeammin (noin 45–90 sekunnissa) sen sijaan, että odotettaisiin täyttä 5 minuutin pysähdystä. Liikenteessä (ruuhka, valot) autoyhteys ei yleensä katkea, joten normaali 5 minuutin turva-aika säilyy.
- **Peruutus julkisessa liikenteessä:** Jos tunnistus käynnistää matkan väärin (esim. bussi, juna, raitiovaunu, taksi), käyttäjä voi perua matkan sovelluksesta tai ilmoituksesta. Sovellus voi kysyä, oletko **matkustaja** vai peruutitko vahingossa: matkustajavalinta pitää tunnistuksen tauolla pidempään (noin 60 min tai kunnes kävelet pois), lyhyempi tauko (noin 10 min) riittää vahinkoperuutukseen. Päättely ja tauko tapahtuvat vain laitteella.

**Lähtöosoitteen ankkuri (paikallinen):** Sovellus voi tallentaa viimeisimmän luotettavan pysähdyspaikan (koordinaatit, tarkkuus, ajankohta — ei osoitetekstiä) laitteen paikalliseen säiliöön, jotta automaattisen matkan lähtöosoite voidaan muodostaa tarkemmin myös silloin, kun jatkuvaa GPS-seurantaa ei ole ollut päällä juuri ennen matkan alkua. Ankkuri päivittyy harvan taustasijainnin ja paikallaanolotunnistuksen avulla ja vanhenee automaattisesti 24 tunnin kuluttua. Tieto pysyy laitteella.

**Automaattinen työ-/yksityisajoluokittelu (Plus):** Jos käyttäjä on merkinnyt suosikkiosoitteisiin kodin ja/tai työpaikkoja, sovellus voi automaattisen matkan tallennuksen yhteydessä päätellä työ- tai yksityisajon vertaamalla lähtöpistettä näihin osoitteisiin (noin 150 m). Jos osumaa ei löydy, käytetään käyttäjän asettamaa oletusta. Päättely tehdään vain laitteella.

**Ilmoitukset:** Aktiivisen matkan aikana näytetään etualan ilmoitus. Automaattimatkan aikana voidaan näyttää 4 min pysähdysmuistutus (toiminnallinen, ei mainontaa). **Viikoittainen yhteenveto** on valinnainen ja oletuksena pois päältä — lasketaan laitteella omista matkoista, ei markkinointia. Ilmoituksia ei lähetetä kehittäjän palvelimelta.

---

## 3. Sijaintitietojen käyttö

Sovellus käyttää laitteen GPS:ää (Google Play Services / Fused Location Provider) ajomatkojen mittaamiseen. Sijaintia ei käytetä mainontaan, profilointiin, myyntiin tai käyttäjän seurantaan markkinointitarkoituksessa.

### Luvat

- **Käytön aikana (fine/coarse location):** matkan aloitus, reaaliaikainen mittaus.
- **Taustasijainti (valinnainen):** vain jos käyttäjä myöntää erillisen taustasijaintiluvan, matkan mittaus voi jatkua näytön ollessa lukittuna tai sovelluksen ollessa taustalla. Taustaseurannan aikana näytetään näkyvä etualan ilmoitus (foreground service), kuten Android vaatii.
- **Activity Recognition (valinnainen, Plus):** täydentävä liiketunnistus automaattiselle matkalle.
- **Bluetooth Connect (valinnainen, Plus):** auton äänireitin paikallinen tunnistus.
- **Ilmoitukset:** etualan ilmoitus ja pysähdysmuistutus.
- **Akun optimointipoikkeus (valinnainen):** luotettavampi automaattinen matka; ohjeistus valmistajakohtaisesti.

### Tarkkuus ja virheet

GPS voi heikentyä tunneleissa, sisätiloissa tai lentotilassa. Ilman kelvollista GPS:ää matkan tallennus voidaan estää tai käyttäjä voi syöttää matkan manuaalisesti.

### Automaattinen matka (Kilsat Plus)

Automaattinen matka on **valinnainen Plus-ominaisuus**. Se voi vaatia taustasijaintiluvan. Ilmainen manuaalinen matka toimii edelleen etualan sijaintiluvalla.

**GPS-primaus ja akun säästö:** Kun automaattinen matka on käytössä mutta aktiivista matkaa ei ole käynnissä, sovellus **ei pidä jatkuvaa GPS-seurantaa päällä** koko ajan. Lyhyt tiheämpi GPS-ikkuna käynnistyy, kun esim. liiketunnistus tunnistaa ajoneuvossa liikkumisen, autoyhteys (Bluetooth / Android Auto) ilmestyy, tai harva taustasijainti herättää sovelluksen. Jos ajoa ei vahvisteta, ikkuna suljetaan (tyypillisesti noin 1,5–3 minuutin kuluttua). Valmistajien akunsäästöasetukset voivat silti keskeyttää taustatyön — käyttäjälle näytetään ohjeistus (Xiaomi/Samsung/Huawei ym.).

**Force stop:** Jos käyttäjä **Force stop** -pysäyttää sovelluksen (tai sulkee sen aggressiivisesti viimeisistä sovelluksista), Activity Recognition ja harva taustasijainti **eivät yleensä herätä** prosessia uudelleen ennen kuin käyttäjä avaa Kilsatin. Tämä poikkeaa iOS:n App Switcher -käyttäytymisestä. Luotettavin käyttö: jätä sovellus taustalle ja poista akkuoptimointi käytöstä.

Automaattinen tunnistus perustuu GPS-nopeuteen, liiketunnistukseen (jos saatavilla) ja sovelluksen sääntöihin. Se ei takaa virheetöntä tunnistusta kaikissa tilanteissa (esim. julkinen liikenne). Käyttäjä voi perua väärän matkan; ks. kohta 2 (peruutus julkisessa liikenteessä).

**Ajon aikainen ilmoitus (Plus):** Aktiivisen matkan aikana näytetään etualan ilmoitus (Android 16: ProgressStyle / Live Updates tuetuilla laitteilla; muuten tavallinen progress-ilmoitus). Tiedot pysyvät laitteella.
---

## 4. Tietojen tallennus, siirrot ja kolmannet osapuolet

### Paikallinen tallennus

Kaikki matka-, suosikki- ja asetustiedot tallennetaan paikallisesti käyttäjän laitteelle Room-tietokantaan (SQLite). Kehittäjä ei saa niitä automaattisesti.

### Ei kehittäjän palvelimia

Matka- ja raporttidataa ei lähetetä kehittäjän omille palvelimille eikä jaeta kehittäjän toimesta kolmansille osapuolille.

### Käyttäjän oma jakaminen

CSV- ja PDF-raportit muodostetaan laitteella. Käyttäjä voi itse jakaa tiedostoja laitteen jakovalikon kautta. Tästä vastaa käyttäjä.

### Kolmannen osapuolen palvelut

| Palvelu | Tarkoitus |
|---------|-----------|
| Google Play Services (sijainti) | GPS-matkan mittaus |
| Google Play Services (Activity Recognition) | Täydentävä liiketunnistus (Plus, jos saatavilla) |
| Google Play Billing | Valinnainen Kilsat Plus -tilaus; vapaaehtoinen Tarjoa kahvi -kertaosto (**ei lahjoitus / ei hyväntekeväisyys**) |
| Android Geocoder | Osoitteiden muodostus (kun käytössä) |
| Laitteen jakovalikko | CSV/PDF-tiedostojen jakaminen käyttäjän valitsemille sovelluksille |

Näiden palveluiden tietosuojakäytännöt määräytyvät kyseisten toimijoiden omien ehtojen mukaan.

---

## 5. Seuranta ja analytiikka

Sovellus ei käytä mainosseurantaa eikä myy käyttäjätietoja. Sovelluksessa ei ole kolmannen osapuolen analytiikka- tai mainosohjelmistoja.

---

## 6. Tietojen käyttötarkoitus

Tietoja käytetään ainoastaan käyttäjän omassa ajopäiväkirjassa:

- ajomatkojen kirjaamiseen ja muokkaamiseen
- kilometrikorvausten laskentaan
- CSV- ja PDF-vientiin käyttäjän omaa kirjanpitoa varten
- kuukausittaisiin tilastoihin (työ-/yksityisajot, ajoneuvokohtaiset yhteenvedot)
- matkan rekisterinumeron tallentamiseen ja raportointiin
- ajotilan näyttämiseen widgetissä
- valinnaiseen viikoittaiseen yhteenvetoilmoitukseen (lasketaan laitteella omista matkoista)
- automaattisen matkan työ-/yksityisajon päättelyyn käyttäjän merkitsemien koti-/työpaikkaosoitteiden perusteella (Kilsat Plus)
- automaattisen matkan käynnistys-/lopetuspäätöksiin ja käyttäjän peruutuksen jälkeiseen tunnistustaukoon (ks. kohta 2)

---

## 7. Tietojen säilytysaika ja poisto

Tiedot säilyvät laitteella, kunnes käyttäjä:

- poistaa yksittäisiä matkoja
- poistaa kaikki matkatiedot asetuksista (*Poista kaikki matkat*)
- poistaa sovelluksen laitteeltaan

Käyttäjä vastaa omien tietojensa varmuuskopioinnista. Kehittäjä ei voi palauttaa käyttäjän laitteelta poistuneita tietoja etänä.

---

## 8. Käyttäjän oikeudet ja toimenpiteet

Koska matkatiedot ovat käyttäjän laitteella, käyttäjä voi käytännössä:

- tarkastella tietoja sovelluksessa
- korjata tietoja
- poistaa tietoja (yksittäin tai kerralla asetuksista)
- viedä tiedot omaan arkistoonsa (CSV/PDF) ennen poistoa

EU:n yleisen tietosuoja-asetuksen (GDPR) mukaisesti käyttäjällä on oikeus pyytää selvitystä tietojensa käsittelystä ottamalla yhteyttä kehittäjään.

Kehittäjä ei voi etänä poistaa käyttäjän laitteella olevia matkoja.

---

## 9. Tietoturva

Sovellus on suunniteltu toimimaan ensisijaisesti ilman verkkoa. Tietoturva perustuu laitteen suojaukseen (lukitus, Androidin tiedostosuojaus). Käyttäjän kannattaa pitää laite ajan tasalla ja käyttää laitteen lukitusta.

Kehittäjä ei vastaa tietojen häviämisestä tilanteissa, joissa käyttäjän laite katoaa, varastetaan, rikkoutuu tai nollataan.

### 9.1 Kehittäjän vastuuvapaus tietosuojan osalta

Koska matka- ja sijaintitiedot käsitellään käyttäjän laitteella eikä kehittäjän palvelimilla, kehittäjä:

- ei voi etänä tarkastella, korjata tai palauttaa matkatietoja
- ei vastaa tietojen häviämisestä laitteen menetyksen, varkauden, rikkoutumisen, nollauksen tai käyttäjän poistotoimien vuoksi
- ei vastaa siitä, miten käyttäjä jakaa CSV/PDF-raportteja kolmansille
- ei vastaa käyttäjän itse syöttämien tietojen oikeellisuudesta eikä siitä, hyväksyykö Verohallinto, työnantaja tai kirjanpitäjä näitä tietoja
- ei ole Verohallinnon tai muun viranomaisen edustaja, kumppani tai alihankkija — ks. kohta 0

Pakottavat GDPR-oikeudet säilyvät. Käyttäjä voi pyytää selvitystä käsittelystä tukiosoitteeseen.

---

## 10. Alaikäiset

Sovellus on tarkoitettu täysi-ikäisille käyttäjille (18+).

---

## 11. Muutokset tietosuojaselosteeseen

Tätä selostetta voidaan päivittää (esim. uudet ominaisuudet). Ajantasainen versio on saatavilla sovelluksen **Asetukset** -osiosta offline-tilassa.

**Android v1.0 (27.7.2026):** Ensimmäinen Android-versio. Paikallinen Room-tallennus, manuaalinen GPS-matka, historia, tilastot, CSV/PDF-vienti, suosikit, onboarding.

**Android v1.2.1 (30.7.2026):** Kilsat Plus (Google Play Billing), automaattinen matka, Activity Recognition / Bluetooth-täydennys, etualan ilmoitus, widget, akkuohjeistus. Tarjoa kahvi = kulutettava IAP, ei lahjoitus. Ei pilvisynkronointia.

**Android v1.2.1 (8.8.2026):** Täsmennetty automatiikkaa: käynnistys ilman autoyhteyttä (selkeä ajo GPS:llä), yhteyskatkoksen pikatallennus, lähtöosoiteankkuri, peruutus julkisessa liikenteessä (matkustaja / vahinko). Lisätty viikoittainen yhteenveto ja *Poista kaikki matkat* kohtaan 7. Force stop -ero iOS:ään säilyy kohdassa 3.

---

## 12. Yhteydenotto

**Kehittäjä:** Kilsat  
**Sähköposti:** kilsat.tuki@gmail.com

Käyttäjä voi ottaa yhteyttä myös Google Play -sovellussivun kehittäjän yhteystietojen kautta.

Vastaamme tietosuoja- ja tukipyyntöihin 30 päivän kuluessa. Emme vastaanota matkalistojasi sähköpostitse. Käsittele matkadataa vain sovelluksessa tai omissa viennöissäsi.
