# Matúšova škola programovania

## Vitaj Matúško!

Prostredníctvom týchto stránok by som Ti chcel pomôcť naučiť sa programovať.
Zámerne som si vybral tento spôsob, pretože

* umožňuje postupne pridávať nové lekcie,
* príklady sa dajú ukázať vo viacerých programovacích jazykoch,
* umožňuje aj iným osobám (napr. Jožkovi) pridávať nové materiály (alebo opravovať  staré chyby)
* ...ktovie čo všetko ešte...

## Ako sa tu orientovať?

Jednoducho!

Vľavo je jednoduché navigačné menu. Môžeš ho vnímať ako odkazy na jednotlivé lekcie.

Samotná lekcia je iba jednoduchý text, podobný tomuto, ktorý práve čítaš.

Snažím sa, aby bol dobre členený (t.j. aby mal rozumnú štruktúru a rozumné nadpisy) a ľahko čitateľný.

Občas možno pridám nejaký obrázok.

A samozrejme, budú tu aj kusy kódu (čiže programu). To bude vyzerať zhruba takto:

``` Java tab="Java" hl_lines="5 6 7 10 13"
static AfisClient client = null;

public static void main(String[] args) throws IOException {
        // MQ client configuration initialization
        MQClientConfiguration config =
                MQClientConfiguration.load(
                        new File("client.properties"));

        // Creation of an AfisClient
        client = new AfisClientFactory(config).createClient();
}
```

``` C# tab="C#" hl_lines="6 7 8 11 14"
static AfisClient client = null;

public static void main()
{
        // MQ client configuration initialization
        MQClientConfiguration config =
                MQClientConfiguration.load(
                        File.ReadAllBytes("client.properties"));

        // Creation of an AfisClient
        client = new AfisClientFactory(config).createClient();

        // Ping queue
        client.PingApplicantQueue();
}
```

Pevne verím, že sa Ti to bude páčiť, a že sa niečo naučíš.
