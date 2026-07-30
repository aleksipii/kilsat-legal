---
layout: page
title: Tietosuojaseloste (Android)
permalink: /android/tietosuojaseloste/
---

# Tietosuojaseloste (Kilsat / Ajopäiväkirja — Android)

**Viimeksi päivitetty:** 30.7.2026  
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

**Ei käytössä:** pilvisynkronointi, käyttäjätilit tai kehittäjän pilvitietokanta. Matkatiedot eivät synkronoidu Google Drive -varmuuskopioon (`allowBackup="false"`).

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

**Autoyhteys (Plus):** Sovellus voi paikallisesti tunnistaa Bluetooth-äänireitin tai Android Auto -tilan. Tieto ei poistu laitteelta.

**Ilmoitukset:** Aktiivisen matkan aikana näytetään etualan ilmoitus. Automaattimatkan aikana voidaan näyttää 4 min pysähdysmuistutus. Ilmoituksia ei käytetä mainontaan eikä lähetetä kehittäjän palvelimelta.

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

Kun et aja, sovellus pyrkii säästämään akkua (harvempi seuranta / GPS-primaus). Valmistajien akunsäästöasetukset voivat silti keskeyttää taustatyön — käyttäjälle näytetään ohjeistus (Xiaomi/Samsung/Huawei ym.).

---

## 4. Tietojen tallennus, siirrot ja kolmannet osapuolet

### Paikallinen tallennus

Kaikki matka-, suosikki- ja asetustiedot tallennetaan paikallisesti käyttäjän laitteelle Room-tietokantaan (SQLite). Kehittäjä ei saa niitä automaattisesti.

### Ei kehittäjän palvelimia

Matka- ja raporttidataa ei lähetetä kehittäjän omille palvelimille eikä jaeta kehittäjän toimesta kolmansille osapuolille.

### Käyttäjän oma jakaminen

CSV- ja PDF-raportit muodostetaan laitteella. Käyttäjä voi itse jakaa tiedostoja laitteen jakovalikon kautta (`Intent.ACTION_SEND`). Tästä vastaa käyttäjä.

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
- automaattisen matkan työ-/yksityisajon päättelyyn käyttäjän merkitsemien koti-/työpaikkaosoitteiden perusteella (Kilsat Plus)

---

## 7. Tietojen säilytysaika ja poisto

Tiedot säilyvät laitteella, kunnes käyttäjä:

- poistaa yksittäisiä matkoja
- poistaa sovelluksen laitteeltaan

Käyttäjä vastaa omien tietojensa varmuuskopioinnista. Kehittäjä ei voi palauttaa käyttäjän laitteelta poistuneita tietoja etänä.

---

## 8. Käyttäjän oikeudet ja toimenpiteet

Koska matkatiedot ovat käyttäjän laitteella, käyttäjä voi käytännössä:

- tarkastella tietoja sovelluksessa
- korjata tietoja
- poistaa tietoja yksittäin
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

---

## 12. Yhteydenotto

**Kehittäjä:** Kilsat  
**Sähköposti:** kilsat.tuki@gmail.com

Käyttäjä voi ottaa yhteyttä myös Google Play -sovellussivun kehittäjän yhteystietojen kautta.

Vastaamme tietosuoja- ja tukipyyntöihin 30 päivän kuluessa. Emme vastaanota matkalistojasi sähköpostitse. Käsittele matkadataa vain sovelluksessa tai omissa viennöissäsi.
