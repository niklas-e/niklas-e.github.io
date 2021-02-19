---
layout:     post
title:      Kryptovaluuttojen louhiminen mobiililaitteella
date:       2018-05-08 17:30:00
author:     Niklas Engblom
summary:    Toimiiko kryptovaluuttojen louhiminen mobiililaitteella ja jos toimii, miten?
categories: Finnish
thumbnail:  btc
tags:
 - cryptocurrency
 - kryptovaluutta
---

*Tämä kirjoitus on alunperin julkaistu digilouhija.fi blogissa, josta siirsin sen tähän henkilökohtaiseen blogiini.*

 Viime kirjoituksessa mainitsin ottavani aiheeksi louhinnan. Olen kirjoittanut aiemmin [kryptovaluuttojen louhinnasta nettiselaimessa]({% post_url 2017-12-07-kryptovaluuttojen-louhiminen-nettiselaimessa-osa1 %}) ja ajattelin taas lähteä syventymään helposti lähestyttävällä esimerkillä. Mobiililaitteella louhimisella en kuitenkaan tarkoita louhintaa laitteen nettiselaimilla. Siinä ei nimittäin ihan hirveästi tule tuottoa, kuten meikäläisen aiemmista kirjoituksista huomaa. Sen sijaan ajattelin kertoa Electroneum nimisestä valuutasta.

Electroneum (ETN) on rakennettu Moneron pohjalta, joten se käyttää myös samaa algoritmia (nimeltään CryptoNote). Ihan alunperin ETN lähettiin rakentamaan ByteCoin nimisen kryptovaluutan pohjalta, joka myös käyttää samaa algoritmia. Myöhemmin kuitenkin yksi Moneron kehittäjistä liittyi tiimiin ja samalla kokeiltiin Moneron käyttämistä pohjana. Näin ollen lopulta päädyttiin käyttämään Moneroa Electroneumin pohjana.

Saatat tässä vaiheessa miettiä, että eipä paljoa kiinnosta, kun akku kuluu muutenkin niin hemmetin vauhdikkaasti. Kannattaa kuitenkin lukaista vielä vähän eteen päin, nimittäin Electroneumin mobiililouhinta ei kuluta juuri yhtään akkua taikka datayhteyksiä.

Niinpä vissiin, miten tuo nyt on mahdollista? Homman nimihän on se, että mobiilisovellus ei oikeasti tee louhintaa. Prosessorin käytön ja monimutkaisten matemaattisten pulmien ratkaisemisen sijasta sovellus tarkkailee käytettävissä olevaa prosessoritehoa. Tämän avulla se päättelee kuinka paljon prosessorin tehoja **olisi voitu käyttää louhintaan**, mikäli laitteesi louhisi oikeasti. Sovellus määrittää sinulle laskentatehon (hash rate), jonka mukaan palkkioita jaetaan.

Hieman kyllä haiskahtaa... miten sovelluksella voi louhia valuuttaa vaikka se ei tee lohkoketjuun liitettävää louhintaa varsinaisesti? Mistä ne palkkiot oikein tulevat? Kolikot ovat valmiiksi louhittuja (premined), eli käytännössä ennen valuutan julkaisua louhittuja kolikoita. Lisäksi samaan pottiin heitettiin listautumisannista (ICO, Initial Coin Offering) ylijääneet Electroneumit.

Mobiililouhijoille tarkoitettujen palkkioiden rajallinen määrä tarkoittaa myös sitä, että ne loppuvat aikanaan. Siihen vain menee todella pitkään, koska sovelluksen laskentateho ja palkitseminen simuloivat oikeaa louhintaa. Toisin sanoen vaikeusaste muuttuu, joka tarkoittaa ajan myötä vähemmän palkkioita samalla laskentateholla.

Miksi mobiililouhija on tehty, jos se ei edistä valuuttaa louhimalla ja palkkiotkin on rajattuja? Päätarkoitus on houkutella uusia käyttäjiä ja tutustuttaa ihmisiä louhintaan. Toki mobiililouhijan kyljessä on myös täysin toimiva ETN lompakko.

Itse olen jo tovin antanut puhelimen louhia, eikä akkua tai dataa kulu juuri lainkaan. Mikäli haluat itsekin kokeilla ETN mobiililouhijaa, käytä ihmeessä meikäläisen refekoodia: 725EAC tai skannaa alla oleva QR-koodi. Molemmat hyötyvät tästä - tarkemmat tiedot löydät osiosta [More]. Sovelluksen voit ladata [Androidille](https://play.google.com/store/apps/details?id=com.electroneum.mobile){:target='_blank'} ja lähiaikoina myös Applen laitteille.

{% include image.html url="/img/Electroneum mobile miner.jpg" description="Electroneum mobiililouhija" %}

Tässäpä tämä tältä erää. Seuraavaksi selvittelen ja kirjoitan louhinnasta yleisemmällä tasolla. Mukavampi lukea lisää, kun lompakkoon kilisee kolikoita samalla.

Lähteet:

* <https://electroneum.com/2017/10/28/electroneum-announce-adoption-of-monero-codebase/>{:target='_blank'}
* <https://electroneum.com/technical-white-paper.pdf>{:target='_blank'}
* <https://electroneum.com/overview-white-paper.pdf>{:target='_blank'}
