# Vstup a výstup

Program často potrebuje s používateľom komunikovať. Na to sa používa vstup a výstup. Programy, ktoré budeš na začiatku programovať používajú na komunikáciu tzv. štandardný vstup a výstup. V tejto lekcii sa však dozvieš aj napríklad ako čítať a písať z programu do súboru.

## Whitespace characters
Na začiatok pár slov o tzv. whitespace znaky (medzera, koniec riadku, tabulátor). Tieto znaky nie vždy dobre vidíš, takže si na ne treba dávať pozor pri načítavaní aj vypisovaní.

### \n
Koniec riadku. Jedná sa o špeciálny znak, označuje sa `\n`. Tento znak robí to, že ukončí riadok, na ktorom sa písalo doteraz a presunie nás na ďalší riadok. Napríklad reťazec `Jozko\nje krasny\na \nuzasny` by vypísany vyzeral takto:
```
Jozko
je krasny
a
uzasny|
```
Znak `|` by sa samozrejme nevypísal. Ten som tam iba vložil, aby ukazoval, kde by sa začal písať ďalší text.

### Pozor pri načítavaní!
Java delí vstup na úseky medzi whitespace znakmi. To znamená, že prvá časť vstupu bude tvoriť všetok text po prvý whitespace znak (medzera, tabulátor, `\n`). To znamená, že vstup 
```
Peter 98    72
a 3.145
Jozo
Mohamed Al Ali
``` 
rozdelí na `Peter`, `98`, `72`, `a`, `3.145`, `Jozo`, `Mohamed`, `Al`, `Ali`. Na načítanie každého úseku treba použiť samostatnú premennú.

### Pozor pri vypisovaní!
Testovač je spravidla dosť háklivý na presný formát výstupu. Skontroluj si vždy aj všetky whitespace znaky, či ich vypisuješ správne. Väčšinou má byť úplne na konci výstupu aj koniec riadku `\n`.

## Načítavanie vstupu

### Jednoduché načítavanie
Načítavanie je celkom jednoduché. Hore, nad všetkým načítavaním treba vložiť riadok ``` Scanner reader = new Scanner(System.in); ```. Scanner nemusíš pomenovať ``` reader ```, môžeš zvoliť aj iné meno. Nakonci, úplne po všetkom načítavaní treba vložiť riadok ``` reader.close(); ```. Samotné načítavanie je jednoduché. Ak chceš načítať ``` int ```, napíšeš ``` int vstup = reader.nextInt() ```. Ak chceš načítať ``` String ```, napíšeš ``` String vstup = reader.next() ```. Pre jednotlivé typy nájdeš spôsob načítavania v tejto tabuľke.

| Typ premennej  |      Ako načítať? |
|----------|-------------|
| **int** | ` int vstup = reader.nextInt(); ` |
| **long** | ` long vstup = reader.nextLong(); ` |
| **boolean** | ` boolean vstup = reader.nextBoolean(); ` |
| **String** | ` String vstup = reader.next(); ` |
| **char** | `String retazec = reader.next();`
|      |`for(int i = 0; i < retazec.length(); i++) {` |
|      | 	`//tu mame i-ty znak vstupu` |
|      | 	`char vstup = retazec.charAt(i);`|
|      | `}`|


### Načítavaj dokým tam dačo je!
Niekedy nevieš koľko vecí máš na vstupe a chceš načítávať dokým je niečo na vstupe. Na to slúži funkcia `reader.hasNext()`. Vracia `true` ak na vstupe ešte je nejaký neprečítaný `string`, inak vracia `false`.

``` Java tab="Java"
import java.io.*;
import java.util.*;

class Vec {
  public static void main(String args[])   {
	Scanner reader = new Scanner(System.in);
	//dokým je na vstupe String
	while(reader.hasNext()) {
		String vstup = reader.next();
		System.out.println(vstup);
	}
  }
} 
```

Ak by si chcel načítavať `int`, spravilo by sa to pomocou `reader.hasNextInt()`. Podobne pre ostatné typy.

### Načítavanie zo súboru
Dakedy chceš načítavať vstup zo súboru. To sa robí tak, že namiesto `Scanner reader = new Scanner(System.in);` vložíš `Scanner special_reader = new Scanner(new File("meno_suboru.txt"));` a musíš to celé vložiť do bloku `try, catch`. Takto:

```Java tab="Java"
	try {
		Scanner special_reader = new Scanner(new File("input.txt"));
		...
		special_reader.close();
	} catch (IOException ex) {
    	System.out.println("Something wrong with files!");
	}

```

Toto je špecialitka Javy, chráni ťa tým pre pádom programu v prípade, že súborom so vstupom neexistuje.

### Vlastné rozdelovanie vstupov
Prednastavenie scannera vstupu sa dá zmeniť, tak aby rozdelil vstup podľa iných znakov ako whitespace znakov. Napríklad by sme mohli chcieť rozdeliť vstup na úseky medzi písmenami `W`. Spraví sa to jednoducho. Namiesto obyčajného `Scanner reader = new Scanner(...);` na začiatku, napíšeš `Scanner reader = new Scanner(...).useDelimiter("WW*");` Vnútri `useDelimiter()` môže byť ľubovoľný regulárny výraz (ak nevieš, čo to je, nerieš zatiaľ). Ak chceš deliť iba pomocou písmenka alebo číslice, jednoducho nahraď znak `W` v tamtom príkaze.

## Vypisovanie výstupu

### Jednoduché vypisovanie

Na vypisovanie výstupu sú dva príkazy `System.out.print()` a `System.out.println()`. Do vnútra zátvoriek napíšeš, čo chceš vypísať. Môže to byť číslo (napr. `98`), reťazec(napr. `"Chelsea je krásna"`) alebo premenná. Nedá sa to však kombinovať. Jediným príkazom sa nedá vypísať napríklad aj číslo aj premenná. Musel by si použiť jeden príkaz, ktorý vypíše iba číslo a druhý, ktorý vypíše iba premennú.

`System.out.print()` nevypisuje koniec riadka, `System.out.println()` vypisuje koniec riadka. To je ich jediný rozdiel. Teoreticky sa teda každé `System.out.println(...);` dá nahradiť za `System.out.print(...); System.out.print(\n)`.

### Vypisovanie do súboru

Podobne jak pri načitavaní, musíš hore pridať ` PrintWriter writer = new PrintWriter(new FileWriter("meno_suboru.txt")); ` a na koniec `writer.close()`. Celé to takisto musí byť v `try, catch` bloku. Namiesto `System.out.print()` používaš potom `writer.print()`.

```Java tab="Java"
	try {
		PrintWriter special_writer = new PrintWriter(new FileWriter("output.txt"));
		special_writer.println("Jozko je velmi mudry a sikovny!");
		...
		special_writer.close();
	} catch (IOException ex) {
    	System.out.println("Something wrong with files!");
	}

```

## Príklad
### Jednoduchý príklad

* Spustí sa program.
* Program vypíše ``` Sire, zadajte svoje meno: ```
* Používateľ (ja, ty, oco alebo kľudne aj dedko) napíše svoje meno, napr. ``` Fero ```.
* Program toto meno (nech je akékoľvek) načíta a nejako spracuje.
* Program vypíše ``` Zadajte svoj počet rúk! ```.
* Používateľ (povedzme ja) napíše ``` 2```.
* Program si opäť načíta toto číslo, vypočíta, koľko rúk mu chýba a toto číslo vypíše.


Implementácia:

``` Java tab="Java"
import java.io.*;
import java.util.*;

class Vec {
  public static void main(String args[])   {
	//vyžiadame si užívateľovo meno
    System.out.print("Sire, zadajte svoje meno: ");
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

### Fičúrie v akcii

Načíta všetky reťazce zo vstupného súboru `input.txt` a vypíše ich oddelené medzerami do `output.txt`:

``` Java tab="Java"
import java.io.*;
import java.util.*;

class Vec {
  public static void main(String args[])   {
	//vstup a vystup zo suboru
	try {
		//vytvorime special_reader na citanie vstupu
		Scanner special_reader = new Scanner(new File("input.txt"));
		//vytvorime special_writer na vypisovanie vystupu
		PrintWriter special_writer = new PrintWriter(new FileWriter("output.txt"));
		String text;
		boolean bolo_prve = false;
		special_writer.print("Sire, napisali ste: ");		
		while(special_reader.hasNext()) {
			if(bolo_prve) special_writer.print(", ");
			bolo_prve = true;
			text = special_reader.next();
			special_writer.print(text);
		}
		special_writer.println(".");
		//zatvorime obe special vecicky
		special_reader.close();
		special_writer.close();
	} catch (IOException ex) {
    	System.out.println("Something wrong with files!");
	}
  }
} 
```

Načíta vstup rozdelený na časti medzi malými samohláskami a vypíše to. Inými slovami odstráni z textu malé samohlásky:

``` Java tab="Java"
import java.io.*;
import java.util.*;

class Vec {
  	public static void main(String args[])   {
		Scanner special_scanner = new Scanner(System.in).useDelimiter("(aa*)|(ee*)|(ii*)|(uu*)|(oo*)|(yy*)");
		while(special_scanner.hasNext()) {
			String text = special_scanner.next();
			System.out.print(text);
		}
		System.out.println();
	}
} 
```

Načíta číslo a vypíše ti všetky jeho cifry oddelené medzerou:

``` Java tab="Java"
import java.io.*;
import java.util.*;

class Vec {
  	public static void main(String args[])   {
		Scanner special_scanner = new Scanner(System.in);
		String text = special_scanner.next();
		System.out.print("Sire, vaše číslo sa skladá z týchto cifier:");
		for(int i = 0; i < text.size(); i++) {
			System.out.print(" ");
			System.out.print(text[i]);
		}
		System.out.println();
	}
} 
```
