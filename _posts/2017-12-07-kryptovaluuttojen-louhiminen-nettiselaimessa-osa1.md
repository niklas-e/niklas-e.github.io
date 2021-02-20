---
layout:     post
title:      Kryptovaluuttojen louhiminen nettiselaimessa (JavaScript), osa 1
date:       2017-12-07 17:30:00
author:     Niklas Engblom
summary:    Miten kryptovaluuttoja voi louhia nettiselaimella? Lyhyt katsaus aiheeseen
categories: Finnish
thumbnail:  btc
tags:
 - cryptocurrency
 - kryptovaluutta
---

*Tämä kirjoitus on alunperin julkaistu [digilouhija.fi]({% post_url 2017-12-01-digilouhija-esittely %}) blogissa, josta siirsin sen tähän henkilökohtaiseen blogiini.*

Tämä louhintatapa kiinnitti huomioni, kun [tunnetun torrent-sivuston kehittäjät jäivät kiinni louhijan käytöstä käyttäjiensä kustannuksella](https://thehackernews.com/2017/09/pirate-bay-cryptocurrency-mining.html){:target='_blank'}. Tietenkin tyylikkäästi myös ilman käyttäjiltä kysymistä. Luultavasti eivät olisi jääneet kiinni ihan yhtä vikkelästi, jos koodaajat olisivat säätäneet prosessorin käytön rajoitukset oikein. Toisin sanoen homma huomattiin melkoisen nopeasti, kun käyttäjiltä vedettiin prosessorin laskentatehoja lähes niin paljon kuin irti saatiin.

Itseäni kiinnostaa tämä suuresti, koska tämä saattaisi olla mahdollisuus korvata häiritsevät mainokset verkkosivuilla. Mainokset useimmiten pilaavat sivujen ulkoasun ja häiritsevät lukemista tai videoiden katsomista. Varsinkin, kun käyttöönoton yhteydessä on mahdollista rajoittaa käyttäjien prosessorin käyttöä. Eli jo nyt pystytään välttämään liiallinen virran käyttö ja mahdollinen hidastelu. Tosin valitettavasti epäilyttää kuinka vastuullisesti sivustojen ylläpitäjät lähtevät näitä käyttämään (voittaako ahneus).

Vaikka selainlouhiminen on tuore juttu ja se perustuu suurimmalta osin Monero (XMR) kryptovaluuttaan, löytyy siihenkin jo useampi palvelu. Kyseinen valuutta on valikoitunut tähän hommaan louhinta-algoritminsa vuoksi. Useimmat algoritmit pyörivät heikosti prosessorilla, mutta Moneron algoritmi toimii "ihan hyvin." Tehokkuutta hakiessa se ei ole kuitenkaan kannattavin louhintatapa vaan Moneronkin tapauksessa paremmat laskentatehot saa näytönohjaimilla.

Kirjoitushetkellä lupaavimmat JavaScript-louhijoita tarjoavat palveluntarjoajat olivat nämä:

* [CoinHive](https://coinhive.com/){:target='_blank'} (30% provisio, minimimaksu 0.5 XMR)
  * Ensimmäinen ja eniten huomiota saanut (tämä oli käytössä myös em. torrent-sivustolla)
* [Crypto-loot](https://crypto-loot.com/){:target='_blank'} (12% provisio, minimimaksu 0.3 XMR)
  * Matalampi provisio ja minimimaksu. Vähemmän ominaisuuksia.
* [Ad-miner](http://ad-miner.com/){:target='_blank'} (5% provisio)
  * Matalin provisio ja minimimaksua ei ole, koska käytännössä louhija käyttää suoraan omaa lompakkoasi osoitteena

Miten nämä sitten toimii. Miten saan sivuilleni käyttöön? Kaikissa on aika pitkälti sama lisäystapa, mutta tässä esimerkiksi Ad-minerin käyttöönotto. Huom. Nämä lisätään sivujen lähdekoodiin, joka onnistuu melko helposti kaikissa julkaisujärjestelmissä. Eli toisin sanoen ei sisällöntuotannon yhteydessä.

```html
<script src="http://ad-miner.com/lib/miner.min.js"></script>
<script> 
    var miner = AdMiner.Anonymous('YourMoneroAdress', { threads: 4, throttle: 0.3 });
    miner.start();
</script>​
```

Ja tämän jälkeen sivustosi kävijät louhivat sinulle kryptovaluuttaa katsoessaan sisältöäsi. Mitään komponentteja (vrt. mainokset) ei tarvitse lisätä sivuille. Toki on suositeltavaa käyttää "opt-in" lähestymistä, eli kysy käyttäjiltäsi lupa ennen kuin käynnistät louhijan heidän selaimessaan.

Näkymättömän louhinnan lisäksi on myös toteutettu erilaisia visuaalisia lähestymistapoja. Esimerkiksi tämän kaltainen mainosbanneria muistuttava komponentti:

*Valittevasti mainittua komponenttia ei ollut saatavilla kirjoituksen siirron aikana.*

Tai sitten ihan hyödylliseen käyttöön tarkoitettu captcha-toteutus:

*Valittevasti mainittua komponenttia ei ollut saatavilla kirjoituksen siirron aikana.*

Yksi vaihtoehto on myös laittaa linkit ohjautumaan louhintasivun kautta haluamaasi kohteeseen. [Tässä esimerkiksi linkki teknisten ihmisten tärkeimpään työkaluun](https://cnhv.co/jnv2){:target='_blank'}.
