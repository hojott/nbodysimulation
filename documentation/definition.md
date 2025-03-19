## Määrittelydokumentti

- Opinto-ohjelma: TKT

- Dokumentaation kieli: suomi

- Ohjelman kieli: Rust

- Muut kielet: Python, Typescript

- Algoritmit: Barnes-Hut algoritmi

- Ongelma: n kappaleen probleeman simulointi. Sitä tarvitaan esimerkiksi galaksien tai tähtijoukkojen syntymisen laskemiseen, pimeän aineen etsimiseen, mutta myös epätähtitieteellisiin ongelmiin

- Syötteet: Syötteitä ovat: solmujen määrä, alkukoordinaatit (osittain satunnaisia), alkunopeus (osittain satunnaisia), vetovoiman suuruus, aika-askeleen suuruus, sallitun virheen suuruus

- Aikavaativuus: O(n log n)

- Lähteet: [https://www.nature.com/articles/324446a0](https://www.nature.com/articles/324446a0)

## Ydin

Ohjelman ydin tulee olemaan Barnes-Hut algoritmi, joka luokittelee kaukana olevat kappaleet yhteen. Se tulee vaatimaan kolmiuloitteisen avaruuden määrittämistä. Avaruuteen lisätään satunnaisesti solmuja, jonka jälkeen avaruus jaetaan octree-maisesti, kunnes jokaisessa alueessa on vain 1 tai 0 solmua. Tämän jälkeen jokaiselle solmulle lasketaan etäisyys octreen korkeimmasta tasosta (jossa on kahdeksan aluetta), ja jos kappale on liian lähellä niitä, laskeudutaan octreen seuraavalle tasolle. Kun päästään tarpeeksi kauas, voidaan laskea solmun kiihtyvyys käyttäen kaavaa a = GM/r^2, josta saadaan nopeuden muutos ja koordinaattien muutos yhdelle aika-askeleelle.
