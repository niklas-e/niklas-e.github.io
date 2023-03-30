---
layout:     post
language:   fi
title:      Mikä on blockchain/lohkoketju, osa 1
date:       2018-01-19 17:30:00
author:     Niklas Engblom
summary:    Mikä on blockchain/lohkoketjut, yksinkertaistetusti teknologian perusteet
categories: Finnish
thumbnail:  btc
tags:
 - cryptocurrency
 - kryptovaluutta
---

*Tämä kirjoitus on alunperin julkaistu [digilouhija.fi]({% post_url 2017-12-01-digilouhija-esittely %}) blogissa, josta siirsin sen tähän henkilökohtaiseen blogiini.*

 Kun aloin tutkimaan kryptovaluuttoja, kaikkialla puhuttiin blockchainista tai suomalaisittain lohkoketjusta. Vaikutti siltä, että se on kryptovaluuttojen ydin. Ihan heti en päässyt kärryille, mikä se tarkalleen ottaen on, mutta lisätutkimisen jälkeen asia alkoi jokseenkin valjeta. Aihe on melko haastava selittää kokonaan, mutta yritänpä kuitenkin avata aihetta edes hieman.

Lyhyimmillään vastaus on tilikirja. Käytännössä lohkoketju sisältää kaikki transaktiot, jotka on tehty kyseisellä kryptovaluutalla. Käydään kuitenkin edes hieman tarkemmin läpi, miten homma toimii.

Ensimmäisenä saattaa miettiä, että eikö ole riskaabelia ja hämärää antaa yhden palveluntarjoajan tai rekisterinpitäjän hallita koko valuutan tilikirjaa? Yksi lohkoketjun hienouksia onkin se, että se ei ole yhdessä sijainnissa oleva tietokanta. Se toimii jaettuna ympäri maailmaa yksityisten tietokoneiden verkoston pyörittämänä. Jokaisella näistä tietokoneista on oma kopio tilikirjasta (lohkoketjusta).

Jotta käyttäjä pystyy tekemään transaktion, hänellä pitää olla lompakko, jossa voi säilyttää valuuttaansa. Lompakko on ohjelma, joka on suojattu salatulla avainparilla. Avainparien avaimet ovat uniikkeja, mutta linkitettyjä toisiinsa. Yleisemmin näitä avaimia kutsutaan **julkiseksi** ja **yksityiseksi** avaimeksi. Tätä salaustekniikkaa käytetään myös transaktioiden tekemisessä ja varmistamisessa.

Otetaan esimerkkinä Matti ja Maija. Maija haluaa lähettää Matille 10 "kolikkoa", joten hän lähettää verkostolle yksityisellä avaimellaan salatun viestin halutusta transaktiosta. Vastaanottaessaan viestin jokainen verkoston tietokone purkaa viestin salauksen Maijan lompakon julkisella avaimella. Tämän jälkeen koneet varmistavat transaktion ja merkitsevät tilikirjan kopioonsa kyseisen transaktion. Mikäli viestiä ei ole salattu oikealla yksityisellä avaimella, lohkoketjun tietokoneet eivät voi purkaa sitä. Salauksella saadaan siis vahvistettua, että lähettäjä on Maija.

Hmm, eli jokainen transaktio on merkittynä lohkoketjuun. Miten sitten lohkoketjusta voidaan päätellä kuinka paljon valuuttaa kussakin lompakossa on saatavilla? Voiko käyttäjä lähettää kolikkoja enemmän kuin omistaa? Ei. Jokaisessa lähetetyssä maksussa pitää olla linkitettynä käyttäjän vastaanottamat transaktiot, joiden arvo on tasan tai yli maksettavan summan. Näitä kutsutaan syötteiksi. Kun linkität syötteitä transaktioihin, et voi käyttää niitä enää uudelleen. Käyttäjät eivät joudu tekemään tätä manuaalisesti vaan lompakko hoitaa nämä asiat.

Käytännössä siis kryptovaluutan omistaminen tarkoittaa sitä, että lohkoketjussa on transaktioita, jotka osoittavat lompakkoosi eikä niitä ole käytetty syötteinä.

Toivottavasti tämä avasi blockchainin/lohkoketjun tarkoitusta hieman. Myönnän kuitenkin saman tien, ettei tästä vielä selvinnyt mistä nimi tulee. Se liittyy olennaisesti turvallisuuteen ja transaktioiden varmistamiseen, joista aion kirjoittaa seuraavaksi. Samalla selkiytyy, mistä valuuttaa syntyy ja mitä louhinta on.

Lue tämän kirjoituksen jatko-osa tästä: [Mikä on blockchain/lohkoketju, osa 2]({% post_url 2018-03-04-mika-on-blockchain-lohkoketju-osa2 %}).
