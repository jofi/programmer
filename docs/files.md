# Vzhľad zdrojových súborov

## Krátky úvod o programovacích jazykoch

Existuje veľa programovacích jazykov. Dôvodov, prečo ich existuje veľa, a prečo vlastne stále vznikajú nové jazyky je viac.

Spomeniem niektoré:

* niektoré jazyky používajú jednoduchšiu syntax (jednoduchší jazyk), iné zložitejšiu syntax,
* programy napísané v niektorých jazykoch môžu byť rýchlejšie ako v iných,
* niektoré programovacie jazyky sú určené pre konkrétnu oblasť, napr.:
    * v niektorých jazykoch sa ľahšie píšu webové aplikácie (také aplikácie, ktoré generujú stránky)
    * v iných jazykoch sa napr. môže jednoduchšie programovať mobilná aplikácia (dokonca pre Android sa musí písať v podstate v Jave)
* niektoré programovacie jazyky, používajú tzv. funckie, iné používajú tzv. objekty
* programy v niektorých jazykoch treba tzv. kompilovať, aby mohli byť spustené, ale v iných jazykoch to nemusí byť potrebné
* atď.

## Zdrojové súbory

Každý program má svoj zdrojový kód. Zdrojový kód programu je niekedy iba v jednom súbore, ale omnoho častejšie je tých súborov viac.

V programátorských súťažiach, takých, na ktoré chodí Jožko, sa obyčajne celý program zapíše  iba do jedného súboru.

Ale bežné programy a hry môžu pozostávať niekedy aj z tisícov súborov.

Rozdelenie do mnohých súborov je praktické:

* kratšie súbory sa ľahšie čítajú,
* program sa obyčajne člení podľa rôznych oblastí, ktoré má na starosti:
    * napr. v programe Spotify by sa jeden súbor mohol venovať prehrávaniu piesne, iný súbor vyhľadávaniu, atď.,
* vďaka mnohým súborom, môžu ľahšie spolupracovať mnohí programátori,
* atď.

Pre jednotlivé programy je navyše dôležitý aj názov a koncovka daného súboru. Zdrojáky pre:

* programovací jazyk **Java** budú vyzerať `Piesen.java`, `Vyhladavac.java`, atd.
* jazyk **C++**: `piesen.cpp`, `program.cpp`, atd.
* **Ruby**: `migrator.rb`, atd.

## Zdroják v `Java`

``` Java tab="Java"
// Takto sa pise komentar

// Vacsina zdrojakov je vlozena do nejakeho podadresara, 
// aby sa v tom dalo lahsie hladat.
// Preto treba uviest package
package com.silake.prvyprogram

// Java je tzv. objektovo-orientovany jazyk a preto sa tu programy pisu do
// tzv. tried (class) a objectov.

// Ako priklad uvadzam class 'Piesen'
class Piesen {

  // Vnutri v classe, je potom mnoho funkcii (hovori sa im aj 'metody')
  public void hraj(int pocet_minut) {
    // Tuto je naprogramovane nieco na zahratie piesne
  }

  public void pauzni() {
    // Tuto je naprogramovane nieco na pauznutie piesne

  }

  public int dlzka() {
    // Tuto je naprogramovane nieco na vratenie dlzky piesne

  }

}

```


## Zdroják v `C++`





