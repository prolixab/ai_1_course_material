# 03 text

## Bokstäver som tal

Hur kodar man bokstäver? Man bestämmer en **tabell** som kopplar varje tecken till ett tal. Den äldsta standarden heter **ASCII** (American Standard Code for Information Interchange, 1963). Den täcker 128 tecken: A–Z, a–z, 0–9, skiljetecken och kontrollkoder.

### Utdrag ur ASCII-tabellen

|       Tecken       | Decimal | Hexadecimalt | Binärt (8 bit) |
| :----------------: | ------: | -----------: | -------------: |
|         `A`        |      65 |         0x41 |     `01000001` |
|         `B`        |      66 |         0x42 |     `01000010` |
|         `H`        |      72 |         0x48 |     `01001000` |
|         `e`        |     101 |         0x65 |     `01100101` |
|         `j`        |     106 |         0x6A |     `01101010` |
|         `!`        |      33 |         0x21 |     `00100001` |
|    (mellanslag)    |      32 |         0x20 |     `00100000` |
| `0` (siffran noll) |      48 |         0x30 |     `00110000` |

### Ordet "Hej" på disk

Ordet **"Hej"** lagras som tre bytes i rad — en byte per tecken:

```
Tecken:   H          e          j
Decimal:  72         101        106
Binärt:   01001000   01100101   01101010
```

En textfil är alltså bokstavligen en lång sekvens av sådana bytesekvenser, lästa från vänster till höger.

## Från ASCII till Unicode

ASCII räcker inte långt — det finns inget å, ä, ö, och definitivt inga kinesiska tecken. Standarden **Unicode** tilldelar ett unikt nummer (kallat en _kodpunkt_) till varje tecken i alla skriftsystem: över 150 000 tecken, från arabiska till fornnordiska runor och emoji.

Varje kodpunkt skrivs som `U+` följt av ett hexadecimalt nummer:

| Tecken | Kodpunkt | Namn                                   |
| :----: | :------: | -------------------------------------- |
|   `Å`  |  U+00C5  | LATIN CAPITAL LETTER A WITH RING ABOVE |
|   `ä`  |  U+00E4  | LATIN SMALL LETTER A WITH DIAERESIS    |
|   `€`  |  U+20AC  | EURO SIGN                              |
|   `中`  |  U+4E2D  | CJK UNIFIED IDEOGRAPH-4E2D             |
|  `😀`  |  U+1F600 | GRINNING FACE                          |

## UTF-8: så lagras Unicode i bytes

Unicode definierar kodpunkter, men inte hur de lagras som bytes på disk. Det gör en **kodning** (_encoding_). Den överlägset vanligaste är **UTF-8**.

UTF-8 är variabel-längd: vanliga tecken (A–Z, 0–9) tar 1 byte — exakt som ASCII. Sällsyntare tecken tar 2, 3 eller 4 bytes.

```
Tecken   Kodpunkt   UTF-8 bytes (hex)    UTF-8 bytes (binärt)
─────────────────────────────────────────────────────────────
A        U+0041     41                   01000001
Å        U+00C5     C3 85                11000011  10000101
中       U+4E2D     E4 B8 AD             11100100  10111000  10101101
😀       U+1F600    F0 9F 98 80          11110000  10011111  10011000  10000000
```

{% hint style="info" %}
**Bakåtkompatibilitet:** De 128 första Unicode-kodpunkterna (U+0000–U+007F) är identiska med ASCII. Det innebär att ett rent ASCII-dokument är ett giltigt UTF-8-dokument — ingenting behöver konverteras.
{% endhint %}

{% hint style="warning" %}
**Vanligt misstag:** Om en fil sparad i UTF-8 öppnas i ett program som förväntar sig Latin-1 (ISO-8859-1), visas å, ä och ö som konstiga tecken (t.ex. visas `Å` som `Ã…`). Det är inte filen som är skadad — det är fel kodning som används vid läsning.
{% endhint %}

## Text i maskininlärning

Råtext kan inte matas direkt in i de flesta maskininlärningsmodeller — de kräver tal. Vanliga omvandlingsmetoder:

* **Bag-of-words:** räkna hur många gånger varje ord förekommer i ett dokument.
* **TF-IDF:** som bag-of-words, men justerat för hur vanligt ett ord är generellt.
* **Word embeddings (Word2Vec, GloVe):** varje ord representeras som en vektor med hundratals dimensioner, där semantiskt lika ord hamnar nära varandra.
* **Tokenisering för transformers:** texten delas i delordsbitar (_tokens_) som kodas numeriskt — grunden i moderna språkmodeller som GPT och BERT.
