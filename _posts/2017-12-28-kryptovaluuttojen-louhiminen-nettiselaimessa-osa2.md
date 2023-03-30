---
layout:     post
language:   fi
title:      Kryptovaluuttojen louhiminen nettiselaimessa (JavaScript), osa 2
date:       2017-12-28 17:30:00
author:     Niklas Engblom
summary:    Miten kryptovaluuttoja voi louhia nettiselaimella? Lyhyt katsaus aiheeseen
categories: Finnish
thumbnail:  btc
tags:
 - cryptocurrency
 - kryptovaluutta
---

*Tämä kirjoitus on alunperin julkaistu [digilouhija.fi]({% post_url 2017-12-01-digilouhija-esittely %}) blogissa, josta siirsin sen tähän henkilökohtaiseen blogiini.*

Edellisessä kirjoituksessa jäi selkeyttämättä se, että louhinta selaimen kautta tapahtuu prosessorilla. Tällä hetkellä selainten käyttömahdollisuudet näytönohjaimien osalta ovat hyvinkin nihkeät.

Nyt kun on tiedossa, että louhimista pystyy tehdä selaimella, kaikkia tietenkin kiinnostaa kuinka tehokasta se on. Tätähän on melko helppo testata esimerkiksi tällä komponentilla:

*Valittevasti mainittua komponenttia ei ollut saatavilla kirjoituksen siirron aikana.*

Tein testejä käyttämällä mahdollisimman paljon laitteen resursseja, eli käytännössä ilman rajoituksia. Laitteina toimivat oma kone ja pari puhelinta (OnePlus 3 ja Samsung Galaxy S7). Omassa koneessa on prosessorina AMD FX-8350 (8 ydintä, 4GHz).

* **Kone (8 säiettä, 100% kuormitus)**
  * Google Chrome ~80-85 hash/s
  * Firefox 105-110 hash/s
  * Edge 30-35 hash/s

* **OnePlus 3 (4 säiettä, 100% kuormitus)**
  * Google Chrome 11-13 hash/s
  * Firefox 11-13 hash/s

* **Samsung Galaxy S7 (8 säiettä, 100% kuormitus)**
  * Google Chrome 20-23 hash/s
  * Firefox 20-22 hash/s
  * Samsung Internet (Android webview?) 4 hash/s

Tästä huomaakin jo, että käytetyllä selaimella voi olla isokin merkitys. Tosin ei niin yllättävää, kun kyseessä on kuitenkin selaimessa pyörivä ohjelmisto.

Mitä näistä lukemista pitäisi saada irti? Tehdäänpä hieman laskelmia tuotoista. Arvioisin oman koneen virrankulutukseksi n. 150-200W, koska näytönohjain ei ole kovalla rasituksella selainpohjaisen louhinnan aikana. Tulevia louhintatutkimuksia varten pitänee hommata sähkönkulutusmittari, jolla saisi tarkemman lukeman. Joka tapauksessa tämän kulutusarvion pohjalta voidaan arvioida mahdolliset tuotot ottamatta huomioon mahdollisia arvonmuutoksia.

Käytin tähän selkeimmän oloista [palvelua](https://www.cryptocompare.com/mining/calculator/xmr){:target='_blank'}, jonka löysin. Syötin tiedoiksi seuraavanlaista:

* Laskentateho 105 hash/s
* Virrankulutus 200 W
* Sähkön hinta 0,05 € (KW/h)

{% include image.html url="/img/monero-xmr-tuotto-nettiselaimella.png" description="Monero (XMR) tuotto nettiselaimella" %}

Kuukausittainen voitto olisi arviolta yhden euron luokkaa. Mutta kuten aiemminkin mainitsin, selainpohjainen louhinta voisi olla vaihtoehtoinen rahoitustapa mainonnan sijasta. Tehdäänpä siis vielä pieniä laskelmia nettisivustolla pyörivän louhinnan osalta.

Olettamia:

* Päivittäisiä kävijöitä on 1000 ja kaikki hyväksyvät louhinnan (tietenkin!)
* 50% kävijöistä ovat tietokoneella ja 50% mobiililaitteella
* Keskimääräinen vierailun kesto: 5 minuuttia (300 sekuntia)
* Käytössä on Coinhive
* Nämä arvot muuttuvat ajan myötä: vaikeustaso 60,778G (60 778 279 684), keskimääräinen palkkio 5,84 XMR (Monero)

Arvioidut keskiarvot:

* Hash/s koneella: 70
* Hash/s mobiililaitteella: 10

Laskelmat:

**Prosessorin käyttö rajoitettu 30% tasolle:**

* 500 * (70 * 0,3) * 300 = 3 150 000 hash
* 500 * (10 * 0,3) * 300 = 450 000 hash
* 1 päivä: 3 600 000
* 30 päivää: 108 000 000

Tuotto Coinhiven antaman laskukaavan mukaan:

* 1 päivä: (3 600 000 / 60 778 279 684) * 5,84 * 0,7 = 0,0002 XMR = 0,063 €
* 30 päivää: (108 000 000 / 60 778 279 684) * 5,84 * 0,7 = 0,0073 XMR = 2,299 €

**Prosessorin käyttö rajoitettu 40% tasolle:**

* 500 * (70 * 0,4) * 300 = 4 200 000 hash
* 500 * (10 * 0,4) * 300 = 600 000 hash
* 1 päivä: 4 800 000
* 30 päivää: 144 000 000

Tuotto Coinhiven antaman laskukaavan mukaan:

* 1 päivä: (4 800 000 / 60 778 279 684) * 5,84 * 0,7 = 0,0003 XMR = 0,094 €
* 30 päivää: (144 000 000 / 60 778 279 684) * 5,84 * 0,7 = 0,0097 XMR = 3,055 €

**Prosessorin käyttö rajoitettu 50% tasolle:**

* 500 * (70 * 0,5) * 300 = 5 250 000 hash
* 500 * (10 * 0,5) * 300 = 750 000 hash
* 1 päivä: 6 000 000
* 30 päivää: 180 000 000

Tuotto Coinhiven antaman laskukaavan mukaan:

* 1 päivä: (6 000 000 / 60 778 279 684) * 5,84 * 0,7 = 0,0004 XMR = 0,126 €
* 30 päivää: (180 000 000 / 60 778 279 684) * 5,84 * 0,7 = 0,0121 XMR = 3,811 €

Näistä laskelmista päätellen pienemmillä sivustoilla tuotot ovat maltilliset. Parhaimmille tienesteille pääsee tekemällä sisältöä, jonka tarkkailuun kävijät käyttävät aikaa. Tämä on ihan hyvä sinänsä, ettei kaikenlaisella roskasisällöllä saa huipputienestejä. Mainoksien osaltahan tienestit lasketaan useimmiten näytettyjen mainosten ja klikkausten mukaan. Näin ollen ei haittaa niin paljoa vaikka kävijät poistuvat sivuilta lähes saman tien.

Eiköhän tässä ollut tarpeeksi laskelmia ja tekstiä yhteen kirjoitukseen. Tässä kuitenkin vielä kysymys teikäläiselle: Minkälaisella laitteella luit tämän ja mihin tasolle laitteesi (ja selaimesi) laskentateho ylsi?
