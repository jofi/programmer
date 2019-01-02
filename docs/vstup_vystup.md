# Vstup a výstup

Programy, ktoré budeš na začiatku programovať používajú na komunikáciu tzv. štandardný vstup a výstup.

## Načítavanie vstupu

Načítavanie je celkom jednoduché. Hore, nad všetkým načítavaním treba vložiť riadok ``` Scanner reader = new Scanner(System.in); ```. Scanner nemusíš pomenovať ``` reader ```, môžeš zvoliť aj iné meno. Nakonci, úplne po všetkom načítavaní treba vložiť riadok ``` reader.close(); ```. Samotné načítavanie je jednoduché. Ak chceš načítať ``` int ```, napíšeš ``` int vstup = reader.nextInt() ```. Ak chceš načítať ``` String ```, napíšeš ``` int vstup = reader.next() ```. Pre jednotlivé typy nájdeš spôsob načítavania v tejto tabuľke.

| Typ premennej  |      Ako načítať? |
|----------|-------------|
| **int** | ` int vstup = reader.nextInt(); ` |
| **long** | ` long vstup = reader.nextLong(); ` |
| **boolean** | ` boolean vstup = reader.nextBoolean(); ` |
| **String** | ` String vstup = reader.next(); ` |
| **char** | `String retazec = reader.next();`
|      |`for(int i = 0; i < retazec.size(); i++) {` |
|      | 	`//tu mame i-ty znak vstupu` |
|      | 	`char vstup = retazec[i];`|
|      | `}`|

Niekedy nevieš koľko vecí máš na vstupe a chceš načítávať dokým je niečo na vstupe. Tento príklad ukazuje ako to urobiť ak načítavame takto stringy:

``` Java tab="Java"
import java.io.*;
import java.util.*;

class Vec {
  public static void main(String args[])   {
	Scanner reader = new Scanner(System.in);
	//pokiaľ je na vstupe String
	while(reader.hasNext()) {
		String vstup = reader.next();
		System.out.println(vstup);
	}
  }
} 
```

Ak by si chcel načítavať `int`, spravilo by sa to pomocou `reader.hasNextInt()`. Podobne pre ostatné typy.

Java delí vstup na úseky medzi tzv. bielymi znakmi (medzera, koniec riadku, tabulátor). To znamená, že vstup `Peter Jozo Fero` rozdelí na tri `Peter`, `Jozo` a `Fero`. Tamten vstup by sa teda nedal načítať do 1 Stringu. Musel by si použiť 3, pre každý úsek 1.

## Vypisovanie výstupu

Na vypisovanie výstupu sú dva príkazy `System.out.print()` a `System.out.println()`. Do vnútra zátvoriek napíšeš, čo chceš vypísať. Môže to byť číslo (napr. `98`), reťazec(napr. `"Chelsea je krásna"`) alebo premenná. Nedá sa to však kombinovať. Jediným príkazom sa nedá vypísať napríklad aj číslo aj premenná. Musel by si použiť jeden príkaz, ktorý vypíše iba číslo a druhý, ktorý vypíše iba premennú.

`System.out.print()` nevypisuje koniec riadka, `System.out.println()` vypisuje koniec riadka. To je ich jediný rozdiel. Teoreticky sa teda každé `System.out.println(...);` dá nahradiť za `System.out.print(...); System.out.print(\n)`.

## Príklad
Celé to môže vyzerať nejako takto.

* Spustí sa program.
* Program vypíše ``` Zadajte svoje meno: ```
* Používateľ (ja, ty, oco alebo kľudne aj dedko) napíše svoje meno, napr. ``` Fero ```.
* Program toto meno (nech je akékoľvek) načíta a nejako spracuje.
* Program vypíše ``` Zadajte svoj počet rúk! ```.
* Používateľ (povedzme ja) napíše ``` 2```.
* Program si opäť načíta toto číslo, vypočíta, koľko rúk mu chýba a toto číslo vypíše.


Implementácia:

``` Java tab="Java" hl_lines="7 9 11 13 15 18 19 20"
import java.io.*;
import java.util.*;

class Vec {
  public static void main(String args[])   {
	//vyžiadame si užívateľovo meno
    System.out.print("Zadajte svoje meno: ");
	//ideme načítavať, najprv treba vytvoriť Scanner
	Scanner reader = new Scanner(System.in);
	//načítame do premennej meno užívateľa
	String meno = reader.next();
	//vyžiadame pocet ruk
	System.out.print("Zadajte svoj počet rúk: ");
	//načítame do premennej pocet ruk
	int pocet_ruk = reader.nextInt();
	int chyba_ruk = 2-pocet_ruk;
	//vypiseme pocet chybajucich ruk
	System.out.print("Chyba Vam ");
	System.out.print(chyba_ruk);
	System.out.print(" ruk\n");
  }
} 
```
