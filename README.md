Maija
=====

## Kääntäminen

Koska rajallisista resursseistani johtuen en ole voinut testata PHL-kääntäjää ihan kaikilla alustoilla, seuraava ei välttämättä toimi. Kaikki testikoneeni ovat amd64-arkkitehtuuria, joten suosittelen
käyttämään sitä.

Koneessa on oltava asennettuna GNU/Linux tai yhteensopiva käyttöjärjestelmä, Java 1.7 tai uudempi, Boehm-roskienkeruukirjasto (libgc), C-kääntäjä (gcc ja tcc testattu) ja assembleri (nasm tai gas).

1. Valmistele käännösympäristö lataamalla PHL:n standardikirjasto gitillä reposta https://github.com/fergusq/phl-standard-library nimeä `phl-standard-library`-kansio uudestaan nimellä `lib`.
2. Lataa PHL-kääntäjä osoitteesta http://www.kaivos.org/doc/phl/phl-dev.jar
3. Luo käännösympäristökansioon (jossa kuuluu olla kansio `lib` ja tiedosto `phl-dev.jar`) väliaikaistiedostoja varten kansio `out`.
4. Käännä ohjelma komennolla `java -jar phl-dev.jar -a --out out maija.phl`.
5. Linkkaa ohjelma komennolla `gcc -o emaija out/*.o -lgc`.
