---
layout: page
title: Tietosuojaseloste (iOS)
permalink: /ios/tietosuojaseloste/
---

# Tietosuojaseloste (Kilsat / Ajopäiväkirja)

**Viimeksi päivitetty:** 8.8.2026  
**Versio:** 1.2.1  
**Tukiosoite:** kilsat.tuki@gmail.com

---

## 0. Ei yhteyttä Verohallintoon tai muihin viranomaisiin

**Kilsat ei ole Verohallinnon, muun veroviranomaisen tai julkisen tahon sovellus, eikä sillä ole mitään virallista, kaupallista tai muuta yhteyttä, kumppanuutta, hyväksyntää tai suositusta Verohallinnolta tai muulta viranomaiselta.** Sovellus on yksityisen kehittäjän riippumattomasti tuottama työkalu. Mahdolliset viittaukset Verohallinnon julkaisemiin ajopäiväkirjavaatimuksiin (esim. matkamittarin lukema) ovat pelkkää yleistä, käyttäjän avuksi tarkoitettua tietoa — ei virallista ohjeistusta, tulkintaa eikä takuuta siitä, että sovelluksella kirjatut tiedot täyttävät Verohallinnon tai muun viranomaisen vaatimukset. Käyttäjä vastaa itse siitä, että hänen kirjaamansa tiedot ja niiden käyttö verotuksessa tai kirjanpidossa täyttävät sovellettavat vaatimukset; tarvittaessa käyttäjän on varmistettava asia Verohallinnolta tai muulta asiantuntijalta.

---

## 1. Rekisterinpitäjä ja roolit

| Rooli | Kuka |
|-------|------|
| Matka- ja ajotiedot | Käyttäjä itse. Tiedot tallennetaan käyttäjän laitteelle; käyttäjä päättää poistosta, muokkauksesta ja viennistä. |
| Sovellus ja tietosuoja-asiat | Kilsat-sovelluksen kehittäjä (yksityinen kehittäjä). Kehittäjä ei ylläpidä pilvipalvelua eikä vastaanota käyttäjän matkalistaa omille palvelimilleen. |

Kilsat on paikallinen työkalu ajopäiväkirjan pitoon. Kehittäjä käsittelee vain sellaisia tietoja, joita Apple tai käyttäjä välittää tukiyhteydenottoa tai vapaaehtoista sovellusostoa koskien.

---

## 2. Mitä tietoja käsitellään

Sovellus voi tallentaa ja näyttää käyttäjän laitteella seuraavia tietoja:

- ajon aloitus- ja lopetusaika
- ajettu matka kilometreinä (GPS-mittaus tai manuaalinen syöttö)
- matkan luokittelu (työajo tai yksityisajo), matkan tarkoitus ja valinnainen lisätieto (esim. "Muu"-tyypin tarkennus)
- matkan alku- ja loppukoordinaatit (GPS-matkoilla)
- alku- ja loppuosoite (muodostetaan Applen geokoodauspalvelun kautta; muoto esim. katu ja kaupunki)
- manuaalisesti lisätyt lähtö- ja kohdeosoitteet
- käyttäjän suosikkiosoitteet (nimi, osoite, koordinaatit, valinnainen koti- tai työpaikka-merkintä)
- käyttäjän suosikkiautot (nimi, rekisterinumero)
- matkaan lukittu kilometrikorvaus ja siitä johdettu korvaussumma
- matkaan lukittu rekisterinumero (tallennetaan matkaan tallennushetkellä)
- käyttäjän itse syöttämät raportointitiedot (esim. kuljettajan nimi, oletusrekisterinumero asetuksissa)
- valinnainen matkamittarin lukema ajon alkaessa ja/tai päättyessä manuaalisessa matkassa (käyttäjän itse syöttämä muistiinpano; **ei vaikuta korvauslaskentaan** eikä sitä tarkisteta tai vahvisteta millään tavalla — ks. kohta 0)

Lisäksi sovellus voi tallentaa laitteelle asetusarvoja (esim. oletuskilometrikorvaus, ulkoasu, onboarding-hyväksyntä, työ-/yksityisajon oletusvalinta Siri-shortcuteja varten). Näitä ei lähetetä kehittäjän palvelimelle.

**Widget (lukitusnäyttö / kotinäyttö):** Widget näyttää vain paikallisen ajotilan (onko matka käynnissä, ajettu matka kilometreinä). Nämä tiedot jaetaan pääsovelluksen ja widgetin välillä **vain laitteella**. Kehittäjä ei vastaanota widgetin tietoja.

**Ei käytössä:** iCloud-synkronointi, käyttäjätilit tai kehittäjän pilvitietokanta. iCloud ei ole osa nykyistä Kilsat Plus -tilausta.

**Kilsat Plus (valinnainen tilaus):** Valinnainen **Kilsat Plus** -kuukausitilaus (App Store). Plus sisältää mm. automaattisen matkan tunnistuksen, Live Activity -näytön ja 4 min pysähdysmuistutuksen. Tilaus käsitellään Applen App Storen kautta; kehittäjä ei vastaanota maksukorttitietoja.

**Kilsat Plus -tilaus ja tietosuoja:**

| Tieto | Käsittely |
|-------|-----------|
| Maksu ja laskutus | Apple / App Store. Kehittäjä ei näe maksukortti-, pankki- tai Apple ID -salasanatietoja. |
| Tilausoikeus | Sovellus tarkistaa paikallisesti Applen järjestelmästä, onko Plus aktiivinen. Tämä tieto tarvitaan Plus-ominaisuuksien avaamiseen. |
| Ostotapahtumat | Applen järjestelmä käsittelee maksut. Kehittäjä ei ylläpidä erillistä tilausrekisteriä omilla palvelimillaan. |
| Palauta ostokset | Toiminto käyttää Applen App Store -palvelua; kehittäjä ei vastaanota käyttäjän Apple ID -tunnistetta erillisesti. |

Tilauksen ehdot (hinta, kokeilu, uusiminen, peruutus): ks. [Käyttöehdot](Kayttoehdot.md) kohta **8.2**.

**Liike- ja automatiikka:** Automaattisen matkan tunnistus voi käyttää laitteen **liike- ja kunto -tietoja** (esim. ajoneuvossa liikkuminen) GPS:n tukena. Data käsitellään vain laitteella automatiikan päätöksiin; kehittäjä ei vastaanota liikedataa.

**Autoyhteyden tunnistus (akun säästö):** Automaattisen matkan taustavalvonta voi kuunnella laitteen **äänireittiä** (esim. CarPlay tai auton Bluetooth-audio) paikallisesti sen arvioimiseksi, onko käyttäjä autoyhteydessä. Tieto ei poistu laitteelta eikä lähetetä kehittäjälle. Tätä käytetään yhdessä liiketunnistuksen kanssa GPS-primauksen päätöksiin (ks. kohta 3).

**Käynnistyksen ja pysäytyksen tarkennukset:** Automaattisen matkan käynnistys- ja lopetuslogiikkaa on tarkennettu liikennetilanteita paremmin huomioivaksi:

- **Kumulatiivinen käynnistys:** Lyhyet pysähdykset (esim. punaiset liikennevalot, ruuhka) eivät nollaa kertynyttä liikeaikaa matkan käynnistyksessä.
- **CarPlay-pikakäynnistys:** Kun laite on yhdistetty CarPlayhyn tai auton äänijärjestelmään, automaattinen matka voi käynnistyä nopeammin (matalampi nopeus- ja aikaraja) kuin ilman yhteyttä.
- **Yhteyskatkoksen pikatallennus:** Kun automaattinen matka on käynnissä ja CarPlay- tai auton Bluetooth-yhteys katkeaa alhaisella nopeudella (esim. käyttäjä pysäköi ja sammuttaa auton), sovellus voi tallentaa matkan tavanomaista nopeammin (noin 45–90 sekunnissa laitteen liiketunnistuksen varmuuden mukaan) sen sijaan, että odotettaisiin täyttä 5 minuutin pysähdystä. Liikenteessä (ruuhka, punaiset valot) autoyhteys ei katkea, joten normaali 5 minuutin turva-aika säilyy näissä tilanteissa muuttumattomana.

Kaikki päättely tapahtuu laitteella GPS-, äänireitti- ja liiketiedon perusteella; mitään näistä tiedoista ei lähetetä kehittäjälle.

**Lähtöosoitteen ankkuri (paikallinen):** Sovellus voi tallentaa viimeisimmän luotettavan pysähdyspaikan (koordinaatit, tarkkuus, ajankohta — ei osoitetekstiä) laitteen paikalliseen jaettuun säiliöön, jotta automaattisen matkan lähtöosoite voidaan muodostaa tarkemmin myös silloin, kun jatkuvaa GPS-seurantaa ei ole ollut päällä juuri ennen matkan alkua. Ankkuri päivittyy iOS:n harvoin päivittyvän **merkittävät sijainninmuutokset** -toiminnon ja laitteen liiketunnistuksen (paikallaanolo) avulla, ja se vanhenee automaattisesti 24 tunnin kuluttua. Tieto pysyy aina laitteella eikä sitä lähetetä kehittäjälle.

**Automaattinen työ-/yksityisajoluokittelu (Kilsat Plus):** Jos käyttäjä on merkinnyt suosikkiosoitteisiin kodin ja/tai yhden tai useamman työpaikan, sovellus voi automaattisen matkan tallennuksen yhteydessä päätellä, onko kyseessä työ- tai yksityisajo, vertaamalla matkan lähtöpistettä näihin merkittyihin osoitteisiin (noin 150 metrin tarkkuudella). Päättely tehdään kokonaan laitteella tallennettujen koordinaattien perusteella; jos osumaa ei löydy, sovellus käyttää käyttäjän asettamaa oletusarvoa (työajo/yksityisajo). Ominaisuus on valinnainen ja toimii vain, jos käyttäjä on itse merkinnyt osoitteet koti- tai työpaikka-tyyppisiksi.

**Paikalliset ilmoitukset:** Automaattisen matkan aikana (Plus, valinnainen asetus päällä) sovellus voi lähettää **yhden toiminnallisen muistutuksen** pysähdyksen jälkeen (esim. "Jatkatko matkaa?" ennen automaattista tallennusta). Ilmoitus on sidottu aktiiviseen automatkaan; sitä ei käytetä mainontaan. **Viikoittainen yhteenveto** on valinnainen ja oletuksena pois päältä — lasketaan laitteella omista matkoista, ei markkinointia. Ilmoituksia ei lähetetä kehittäjän palvelimelta.

---

## 3. Sijaintitietojen käyttö

Sovellus käyttää laitteen GPS:ää ajomatkojen mittaamiseen ja karttanäyttöön. Sijaintia ei käytetä mainontaan, profilointiin, myyntiin tai käyttäjän seurantaan markkinointitarkoituksessa.

### Luvat

- **Käytön aikana:** matkan aloitus, reaaliaikainen mittaus ja kartta.
- **Aina (valinnainen):** vain jos käyttäjä myöntää *Sijainti aina* -luvan, matkan mittaus voi jatkua näytön ollessa lukittuna tai sovelluksen ollessa taustalla.

Taustaseuranta on käytössä vain, kun käyttäjä on myöntänyt *Sijainti aina* -luvan.

### Siri-shortcutit

Käyttäjä voi valinnaisesti käyttää Sirin pikakomentoja (esim. "Aloita matka Kilsat", "Lopeta matka Kilsat"). Komennot käyttävät samaa paikallista matkan seuranta- ja tallennuslogiikkaa kuin sovelluksen napit. Siri ja pikakomennot käsitellään Applen järjestelmän kautta; kehittäjä ei vastaanota ääni- tai puhedataa.

### Tarkkuus ja virheet

GPS voi heikentyä tunneleissa, sisätiloissa tai lentotilassa. Sovellus suodattaa heikkotarkkuuksisia pisteitä. Ilman kelvollista GPS:ää matkan tallennus voidaan estää.

### Automaattinen matka ja taustasijainti (Kilsat Plus)

Automaattinen matka on **valinnainen Plus-ominaisuus**. Se voi vaatia *Sijainti aina* -luvan, jotta seuranta voi jatkua näytön ollessa lukittuna. Lupa pyydetään vain, kun käyttäjä kytkee automaattisen matkan päälle. Ilmainen manuaalinen matka toimii edelleen *Sijainti käytön aikana* -luvalla.

**GPS-primaus ja akun säästö:** Kun automaattinen matka on käytössä mutta aktiivista matkaa ei ole käynnissä, sovellus **ei pidä jatkuvaa GPS-seurantaa päällä kotona tai toimistolla**. Kun et aja, käytetään harvaa *merkittävät sijainninmuutokset* -valvontaa, joka voi herättää sovelluksen taustalla merkittävän sijaintimuutoksen yhteydessä. Lyhyt jatkuva GPS-ikkuna käynnistyy, kun yksi seuraavista täyttyy: **merkittävä sijaintimuutos (herätys)**, **laitteen liiketunnistus tunnistaa ajoneuvossa liikkumisen**, tai **CarPlay-/Bluetooth-äänireitti**. Jos ajoa ei vahvisteta, GPS-ikkuna suljetaan (tyypillisesti noin 1,5–3 minuutin kuluttua). CarPlay ei ole pakollinen. Sininen sijainti-indikaattori näkyy vain, kun taustasijaintia käytetään aktiivisesti.

**Sovelluksen sulkeminen sovellusvaihtajasta:** *Merkittävät sijainninmuutokset* -valvonta on iOS:n järjestelmätason toiminto, joka voi herättää sovelluksen lyhyeksi hetkeksi taustalla **myös silloin, kun käyttäjä on sulkenut Kilsatin kokonaan sovellusvaihtajasta**. Tällöin GPS-ikkuna voi käynnistyä samalla tavalla kuin sovelluksen ollessa tavallisesti taustalla. Sen sijaan laitteen liiketunnistus ja CarPlay-/Bluetooth-äänireitin tunnistus eivät ole aktiivisia ennen kuin käyttäjä avaa sovelluksen seuraavan kerran manuaalisesti. Kaikki päättely tapahtuu tälläkin polulla laitteella; mitään tietoa ei lähetetä kehittäjälle.

Automaattinen tunnistus perustuu GPS-nopeuteen, liikeanalyysiin ja sovelluksen sääntöihin. Se ei takaa virheetöntä tunnistusta kaikissa tilanteissa (esim. julkiset kulkuneuvot, kävely tai juoksu — näissä nopeus jää yleensä automaattisen matkan käynnistysrajan alle).

### Live Activity (Kilsat Plus)

Kun Plus-käyttäjällä on aktiivinen matka (manuaalinen tai automaattinen), sovellus voi näyttää **Live Activity** -näytön lukitusnäytöllä ja Dynamic Islandilla. Näytetään vain matkaan liittyvät tiedot (esim. kilometrit, kesto). Tiedot jaetaan pääsovelluksen ja Live Activity -näytön välillä **vain laitteella**. Kehittäjä ei vastaanota Live Activity -dataa.

**Live Activityn päättyminen:** Live Activity näytetään vain aktiivisen matkan aikana. Kun matkaa ei ole käynnissä, sovellus pyrkii sulkemaan mahdollisen jumissa olevan Live Activityn sovelluksen käynnistyksessä ja etualalle palatessa.

---

## 4. Tietojen tallennus, siirrot ja kolmannet osapuolet

### Paikallinen tallennus

Kaikki matka-, suosikki- ja asetustiedot tallennetaan paikallisesti käyttäjän laitteelle. Kehittäjä ei saa niitä automaattisesti.

### Widget ja Live Activity (laitteen sisäinen jako)

Pääsovellus, widget ja Live Activity jakavat tarvittavat ajotiedot (esim. matka käynnissä / ei, kilometrimäärä) vain laitteen sisällä. Tieto ei poistu laitteelta eikä synkronoidu pilveen kehittäjän toimesta.

### Ei kehittäjän palvelimia

Matka- ja raporttidataa ei lähetetä kehittäjän omille palvelimille eikä jaeta kehittäjän toimesta kolmansille osapuolille.

### Käyttäjän oma jakaminen

CSV- ja PDF-raportit muodostetaan laitteella. Käyttäjä voi itse jakaa tiedostoja laitteen jakovalikon kautta. Tästä vastaa käyttäjä.

### Kolmannen osapuolen palvelut

| Palvelu | Tarkoitus |
|---------|-----------|
| Applen kartat / osoitteet | Osoitteiden muodostaminen GPS-koordinaateista, karttanäyttö |
| Applen osoitehaku | Vain kun kirjoitat osoitetta manuaalisessa matkassa tai suosikissa |
| Applen reittiehdotus | Manuaalisen matkan ja matkan muokkauksen ajomatkan (km) automaattinen ehdotus lähtö- ja kohdeosoitteen perusteella; vaatii verkkoyhteyden; data ei tallennu kehittäjän palvelimelle |
| Applen Siri / pikakomennot | Valinnaiset pikakomennot matkan aloittamiseen ja lopettamiseen |
| App Store | Vapaaehtoinen *Tarjoa kahvi* -osto; valinnainen **Kilsat Plus** -kuukausitilaus. Maksu ja tilausoikeus Applen kautta; ks. kohta 2. |
| Applen arvostelupyyntö | Sovelluksen arvostelu App Storessa (harvoin, Applen sääntöjen mukaan) |
| Selain (julkiset legal-sivut) | Tämän selosteen ja käyttöehtojen lukeminen asetuksista; vaatii verkkoyhteyden |

Näiden palveluiden tietosuojakäytännöt määräytyvät kyseisten toimijoiden omien ehtojen mukaan.

---

## 5. Seuranta ja analytiikka

Sovellus ei käytä mainosseurantaa eikä myy käyttäjätietoja. Sovellus ilmoittaa tietosuojatiedoissaan, ettei seurantaa ole käytössä.

Sovelluksessa ei ole kolmannen osapuolen analytiikka- tai mainosohjelmistoja.

---

## 6. Tietojen käyttötarkoitus

Tietoja käytetään ainoastaan käyttäjän omassa ajopäiväkirjassa:

- ajomatkojen kirjaamiseen ja muokkaamiseen
- kilometrikorvausten laskentaan
- CSV- ja PDF-vientiin käyttäjän omaa kirjanpitoa varten
- kuukausittaisiin tilastoihin (työ-/yksityisajot, ajoneuvokohtaiset yhteenvedot)
- matkan rekisterinumeron tallentamiseen ja raportointiin
- valinnaisen matkamittarilukeman tallentamiseen käyttäjän omaksi muistiinpanoksi kirjanpitoa/verotusta varten (käyttäjän vastuulla, ei vaikuta korvauslaskentaan)
- ajomatkan pituuden ehdotukseen manuaalisissa matkoissa osoitteiden perusteella (reittiehdotus; käyttäjä voi aina korjata km:n käsin)
- ajotilan näyttämiseen widgetissä, kun käyttäjä on lisännyt widgetin
- automaattisen matkan työ-/yksityisajon päättelyyn käyttäjän merkitsemien koti-/työpaikkaosoitteiden perusteella (Kilsat Plus)

---

## 7. Tietojen säilytysaika ja poisto

Tiedot säilyvät laitteella, kunnes käyttäjä:

- poistaa yksittäisiä matkoja
- poistaa kaikki matkatiedot asetuksista (*Poista kaikki matkatiedot*)
- poistaa sovelluksen laitteeltaan

Käyttäjä vastaa omien tietojensa varmuuskopioinnista. Kehittäjä ei voi palauttaa käyttäjän laitteelta poistuneita tietoja etänä.

---

## 8. Käyttäjän oikeudet ja toimenpiteet

Koska matkatiedot ovat käyttäjän laitteella, käyttäjä voi käytännössä:

- tarkastella tietoja sovelluksessa
- korjata tietoja
- poistaa tietoja (yksittäin tai kerralla)
- viedä tiedot omaan arkistoonsa (CSV/PDF) ennen poistoa

EU:n yleisen tietosuoja-asetuksen (GDPR) mukaisesti käyttäjällä on oikeus pyytää selvitystä tietojensa käsittelystä ottamalla yhteyttä kehittäjään.

Kehittäjä ei voi etänä poistaa käyttäjän laitteella olevia matkoja.

---

## 9. Tietoturva

Sovellus on suunniteltu toimimaan ensisijaisesti ilman verkkoa. Tietoturva perustuu laitteen suojaukseen (lukitus, iOS:n tiedostosuojaus). Käyttäjän kannattaa pitää laite ajan tasalla ja käyttää laitteen lukitusta.

Kehittäjä ei vastaa tietojen häviämisestä tilanteissa, joissa käyttäjän laite katoaa, varastetaan, rikkoutuu tai nollataan.

### 9.1 Kehittäjän vastuuvapaus tietosuojan osalta

Koska matka- ja sijaintitiedot käsitellään käyttäjän laitteella eikä kehittäjän palvelimilla, kehittäjä:

- ei voi etänä tarkastella, korjata tai palauttaa matkatietoja
- ei vastaa tietojen häviämisestä laitteen menetyksen, varkauden, rikkoutumisen, nollauksen tai käyttäjän poistotoimien vuoksi
- ei vastaa siitä, miten käyttäjä jakaa CSV/PDF-raportteja kolmansille
- ei vastaa käyttäjän itse syöttämien tietojen (esim. matkan tarkoitus, rekisterinumero, matkamittarilukema) oikeellisuudesta eikä siitä, hyväksyykö Verohallinto, työnantaja tai kirjanpitäjä näitä tietoja
- ei ole Verohallinnon tai muun viranomaisen edustaja, kumppani tai alihankkija — ks. kohta 0

Pakottavat GDPR-oikeudet säilyvät. Käyttäjä voi pyytää selvitystä käsittelystä tukiosoitteeseen; kehittäjä ei kuitenkaan voi poistaa laitteella olevaa dataa etänä.

---

## 10. Alaikäiset

Sovellus on tarkoitettu täysi-ikäisille käyttäjille (18+). App Storen ikäluokitus on 17+, joka on alustan korkein mahdollinen luokitus.

---

## 11. Muutokset tietosuojaselosteeseen

Tätä selostetta voidaan päivittää (esim. uudet ominaisuudet). Ajantasainen versio on saatavilla sovelluksen Asetukset -linkin kautta (verkkoyhteys tarvitaan).

**v1.1 (18.6.2026):** Siri-shortcutit, widget ja paikallinen ajotilan jako widgetille. Ei muutoksia pilvisynkronointiin.

**v1.2 (6.7.2026):** Kilsat Plus -tilaus, automaattinen matka, liiketunnistus, Live Activity, toiminnallinen 4 min pysähdys -ilmoitus automatkan aikana. Ei kehittäjän pilvisynkronointia.

**v1.2.1 (8.7.2026):** Suosikkiautot (nimi, rekisterinumero) laitteella. Täydennetty Kilsat Plus -tilauksen tietosuojakuvaus (ei maksukorttitietoja). Linkit tähän selosteeseen ja käyttöehtoihin. Täsmennetty käyttötarkoitukset (tilastot, reittiehdotus). Sijainti ja liike/kunto käsitellään paikallisesti, ei linkitettynä käyttäjän henkilöllisyyteen.

**v1.2.1 (16.7.2026):** Automaattisen matkan herätys merkittävästä sijainninmuutoksesta + lyhyt GPS-ikkuna ilman CarPlay-pakkoa (ei jatkuvaa GPS:ää kun et aja). CarPlay/Bluetooth säilyy nopeutuspolkuna.

**v1.2.1 (8.7.2026):** GPS-primaus automaattiselle matkalle (CarPlay/Bluetooth tai liiketunnistus → taustasijainti; muuten GPS pois akun säästöksi). Autoyhteyden paikallinen tunnistus äänireitin kautta. Live Activityn siivous, kun matkaa ei ole käynnissä. Plus-asetusten käyttöönotto-ohje oston jälkeen.

**v1.2.1 (13.7.2026):** Automaattisen matkan käynnistyksen kumulatiivinen liikeaika ja CarPlay-pikakäynnistys. Yhteyskatkoksen pikatallennus, kun autoyhteys katkeaa alhaisella nopeudella (n. 45–90 s normaalin 5 min sijaan; liikenteen 5 min turva-aika säilyy ennallaan). Paikallinen lähtöosoiteankkuri (merkittävät sijainninmuutokset + liiketunnistus, vanhenee 24 h:ssa). Automaattinen työ-/yksityisajoluokittelu koti-/työpaikkamerkittyjen suosikkiosoitteiden perusteella (Kilsat Plus). Suosikkiosoitteisiin voi merkitä useita työpaikkoja (koti pysyy yksiselitteisenä).

**v1.2.1 (17.7.2026):** Siivottu tekniset termit käyttäjäystävällisemmiksi. Plus on nykyinen valinnainen tilaus; iCloud ei käytössä. Lisätty kohta 9.1 (kehittäjän vastuuvapaus tietosuojan osalta).

**v1.2.1 (27.7.2026):** Lisätty valinnainen matkamittarin lukema (alku/loppu) manuaaliseen matkaan — käyttäjän oma muistiinpano, ei vaikuta korvauslaskentaan. Lisätty kohta 0: sovellus ei liity Verohallintoon tai muuhun viranomaiseen millään tavalla. Täsmennetty kehittäjän vastuuvapautta (kohta 9.1) käyttäjän itse syöttämien tietojen osalta.

**v1.2.1 (6.8.2026):** Täsmennetty kohtaa 3: merkittävät sijainninmuutokset -valvonta voi herättää sovelluksen lyhyeksi hetkeksi taustalla myös silloin, kun käyttäjä on sulkenut sovelluksen kokonaan sovellusvaihtajasta (iOS:n järjestelmätason toiminto). Muu tunnistus (liiketunnistus, CarPlay/Bluetooth) vaatii sovelluksen avaamisen manuaalisesti tämän jälkeen.

**v1.2.1 (8.8.2026):** Siistitty esitystapa: versio-etuliitteet poistettu käsittelykuvauksista (kohdat 2–6). Sisältö säilyy; versiohistoria pysyy tässä muutoslokissa.

---

## 12. Yhteydenotto

**Kehittäjä:** Kilsat  
**Sähköposti:** kilsat.tuki@gmail.com

Käyttäjä voi ottaa yhteyttä myös App Store -sovellussivun App Support -kautta.

Vastaamme tietosuoja- ja tukipyyntöihin 30 päivän kuluessa. Emme vastaanota matkalistojasi sähköpostitse. Käsittele matkadataa vain sovelluksessa tai omissa viennöissäsi.
