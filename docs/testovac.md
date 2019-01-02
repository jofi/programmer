# Testovač KSP

Existuje stránka, na ktorej existuje veľa úloh pre začínajúcich programátorov ako si ty. Volá sa to Testovač KSP a nájdeš to tu: http://testovac.ksp.sk

## Prihlásenie
Ako prvé si vytvor konto a prihlás sa.


## Úlohy

V sekcii **Úlohy** je množstvo úloh najrôznejších obtiažností. Odporúčam prvú rozsiahlu kategóriu **Úvod do programovania**. Úlohy tam sú zoradené zhruba podľa obtiažnosti, takže kľudne rieš postupne. Postupom času však budeš potrebovať nové poznatky - premenné, cykly, podmienky, ...

## Testovanie riešení

Nakódil si riešenie úlohy a myslíš si, že to máš úplne správne? Na Testovači KSP si môžeš dať svoje riešenie otestovať. Pod zadaním úlohy sa vždy nachádza možnosť vložiť tvoj súbor s riešením a následne ho odovzdať. V priebehu pár sekúnd sa ti riešenie otestuje a dozvieš sa či si to mal dobre. Testovač ti vždy vráti správu o tom ako tvoj program dopadol. Význam jednotlivých správ si môžeš prečítať tu: https://testovac.ksp.sk/wiki/odpovede-testovaca/

Testovač si pamätá aj riešenia, ktoré si submitol (odovzdal) v minulosti. Zoznam od najmladších k najstarším nájdeš tiež v detaile úlohy.

Testovač tvoj program testuje takto: Pripraví niekoľko vstupov, následne spustí tvoj program pre každý z nich a pozrie sa či dal tvoj program dostatočne rýchlo, bez problémov správny výstup. Napríklad v druhej úlohe **Číslo** by mohol mať nachystané vstupy s číslami 3, 987654 a 3727484756. Pre každý z týchto vstupov by spustil tvoj program a pozrel sa či na výstup vypísal presne 3, 987654, resp. 3727484756.

## Pri submitoch pozor

Treba si dávať pozor na viacero vecí. Tu sú najčastejšie chyby aj s dovetkom.

* Pred **class** nesmie byť napísané **public**.
* Kód sa nesmie nachádzať v žiadnom **package**.
* Načítavaj a vypisuj všetko presne tak, ako je to v zadaní špecifikované. Ak máš vypísať **Jozko je uzasny**, nevypíš **Jožko je krásny** ani **Jozko je uzas ny** (hoci obe sú pravda). Pozor na medzery, tabulátor a osobitne pozor na koniec riadka. Koniec riadku znamená, že keď po ňom začneš znova niečo vypisovať, tak už ďalšie, čo napíšeš nebude v tom istom riadku ako predchádzajúci reťazec. Bude to už v ďalšom riadku. Keď napíšeš ``` System.out.println("Jozko je kral!"); ```, automaticky sa napíše **Jozko je  kral** a za tým koniec riadku. Keď na napíšeš ``` System.out.print("Jozko je kral!"); ```, automaticky sa napíše **Jozko je  kral** a za tým nebude koniec riadku. Koniec riadku sa zvykne označovať ako **\n**. 

## Príklad
Dobrý kód, ktorý vypíše v prvom riadku **47 83\n** a v druhom **64 64 64\n** vyzerá napríklad takto:

``` Java tab="Java" hl_lines="6 7"
import java.io.*;
import java.util.*;

class Program {
  public static void main(String args[])   {
    System.out.print("47 83\n");
	System.out.println("64 64 64");
  }
} 
```

Tak makaj riešiť!
