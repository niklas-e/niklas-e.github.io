---
layout:     post
language:   fi
title:      Mikä on blockchain/lohkoketju, osa 2
date:       2018-03-04 17:30:00
author:     Niklas Engblom
summary:    Mikä on blockchain/lohkoketjut, yksinkertaistetusti teknologian perusteet
categories: Finnish
thumbnail:  btc
tags:
 - cryptocurrency
 - kryptovaluutta
---

*Tämä kirjoitus on alunperin julkaistu [digilouhija.fi]({% post_url 2017-12-01-digilouhija-esittely %}) blogissa, josta siirsin sen tähän henkilökohtaiseen blogiini.*

Tämä on jatkoa kirjoitukselle [Mikä on blockchain/lohkoketju, osa 1]({% post_url 2018-01-19-mika-on-blockchain-lohkoketju-osa1 %}).

Transaktioissa ei ole aikaleimaa, joten niistä ei pystytä päättelemään kronologista järjestystä. Aikaleima puuttuu lähinnä turvallisuussyistä, koska se olisi erittäin helppo väärentää. Lohkoketjun verkosto kuitenkin järjestää transaktiot lohkoihin, jotka ovat aikajärjestyksessä. Tästä lohkoketju saakin nimensä - tilikirja muodostuu linkitetyistä lohkoista, jotka ovat aikajärjestyksessä. Tästä syntyy ikään kuin ketju, jossa on lohkoja.

{% include image.html url="/img/Lohkoketju.png" description="Transaktiot ja lohkoketju" %}

Jokainen verkoston tietokone voi ryhmitellä vahvistamattomia transaktioita ja tehdä ehdotuksen uudesta lohkosta. Uusi lohko lisätään ketjuun kuitenkin vain, jos se sisältää vastauksen monimutkaiseen matemaattiseen pulmaan. Käytännössä tämä matemaattinen pulma on peruuttamattomasti salattu tarkiste, jonka voi ratkaista vain arvailemalla satunnaisia numeroita. Oikea tarkiste luodaan yhdistämällä tämä satunnainen numero sekä edellisen lohkon sisältö. Prosessissa saattaisi kestää vuosi, jos sitä yritettäisiin yksittäisellä perustietokoneella. Lohkoja kuitenkin luodaan huomattavasti useammin, koska verkostossa on yleensä suuri määrä tietokoneita, jotka ovat vieläpä huomattavasti tehokkaampia kuin perustietokoneet. Uusien lohkojen luontiaika vaihtelee kryptovaluutoittain, mutta suosituimpien valuuttojen luontiajat ovat n. 5-15 minuutin luokkaa.

## Louhinta

Selvä homma, mutta... Mistä uusia kolikoita syntyy? Varojen lähettäminenhän varmennetaan transaktioon liitettyjen syötteiden avulla, eli käytännössä ennen varojen lähettämistä sinulla pitää olla yhtä paljon tai enemmän sinun lompakkoosi tulleita varoja. Miten kukaan on voinut saada kolikoita lompakkoonsa? Tässä tulee kehiin toiminta, jota kutsutaan louhinnaksi. Aina kun verkoston kone saa ratkaistua edellä mainitun, uuteen lohkoon, vaaditun matemaattisen pulman, myönnetään siitä palkkio. Nämä palkkiot ovat syy, miksi monet valjastavat koneensa lohkoketjun verkostoon. Tällä tavalla saadaan myös tarpeeksi laskentatehoa pyörittämään lohkoketjua.

Ok, mutta eikös se ole melko hidasta saada tienestejä, jos ainoastaan uuden lohkon luomisesta saa palkkion? Kyllä, mutta tämän takia onkin perustettu yhteistyötä tekeviä keskittymiä (ns. "mining pool"). Toisin sanoen X määrä koneita yrittävät yhdessä saada luotua lohkoja ja aina siinä onnistuessaan palkkio jaetaan osallistujille heidän laskentatehon perusteella.

Tässäpä oikeastaan perusteet lohkoketjuihin ja louhintaan. Kuten arvata saattaa, aiheesta voisi kirjoittaa huomattavasti enemmän, mutta näiden kahden kirjoituksen tarkoitus olikin kattaa vain perusteet. Seuraavaksi ajattelin kirjoittaa muun muassa siitä, miksi kryptovaluutat ovat mielenkiintoisia ja mitä hyötyjä ne tarjoavat verrattuna (keskus)pankkien hallitsemiin valuuttoihin.
