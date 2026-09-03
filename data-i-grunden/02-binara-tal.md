# 02 binara tal

## Varför ettor och nollor?

En dators minsta byggsten är **transistorn** — en elektronisk strömbrytare som antingen är på (spänning finns) eller av (ingen spänning). Det finns exakt två möjliga lägen. Det är därför all information i en dator till slut reduceras till kombinationer av **1** och **0**.

En ensam 1 eller 0 kallas en **bit** (binary digit). En sekvens av 8 bitar kallas en **byte**. Med 8 bitar kan man representera 2⁸ = **256 olika värden** (0–255).

## Räkna binärt

I det vanliga decimalsystemet har vi tio siffror (0–9). Positionen avgör värdet: hundratal, tiotal, ental. Binärt funkar likadant, men med bas 2: tvåpotenser i stället för tiopotenser.

```
Decimal:  4 × 100 + 2 × 10 + 7 × 1  =  427

Binärt:   1 × 128 + 0 × 64 + 1 × 32 + 0 × 16 +
          1 × 8   + 0 × 4  + 1 × 2  + 1 × 1   =  171
                                                   (10101011)
```

### Positionernas värden i en byte

```
Position:  7     6     5     4     3     2     1     0
Värde:    128    64    32    16     8     4     2     1
Bit:       1     0     1     0     1     0     1     1
           │                             │           │
           └─ mest signifikant           └─ minst signifikant
```

Summa: 128 + 32 + 8 + 2 + 1 = **171**

### Konverteringstabell (0–15)

| Decimal | Binärt (4 bit) | Decimal | Binärt (4 bit) |
| ------: | :------------: | ------: | :------------: |
|       0 |     `0000`     |       8 |     `1000`     |
|       1 |     `0001`     |       9 |     `1001`     |
|       2 |     `0010`     |      10 |     `1010`     |
|       3 |     `0011`     |      11 |     `1011`     |
|       4 |     `0100`     |      12 |     `1100`     |
|       5 |     `0101`     |      13 |     `1101`     |
|       6 |     `0110`     |      14 |     `1110`     |
|       7 |     `0111`     |      15 |     `1111`     |

## Bits och bytes

| Enhet           |           Bitar | Kombinationer | Typisk användning     |
| --------------- | --------------: | ------------: | --------------------- |
| 1 bit           |               1 |             2 | på / av               |
| 1 byte          |               8 |           256 | ett tecken            |
| 1 kilobyte (KB) |           8 192 |             — | ett kort textdokument |
| 1 megabyte (MB) |       8 388 608 |             — | en liten bild         |
| 1 gigabyte (GB) | ≈ 8,6 miljarder |             — | en film               |
| 1 terabyte (TB) |  ≈ 8,8 biljoner |             — | en stor hårddisk      |

{% hint style="info" %}
**Obs:** Prefixen kilo, mega och giga är tvetydiga i datakontexten. I SI-systemet betyder kilo = 1 000, men i datorminnessammanhang används ofta kilo = 1 024 (2¹⁰). Standarderna KiB/MiB/GiB (kibibyte/mebibyte/gibibyte) är precisa, men i vardagligt tal blandas de ofta ihop.
{% endhint %}

## Hexadecimalt — ett praktiskt mellansystem

Binärt är exakt men svårläst. **Hexadecimalt** (bas 16) är ett kompromissformat som används flitigt av programmerare. Det har 16 siffror: 0–9 och A–F (där A=10, B=11, ..., F=15).

En byte (8 bitar) representeras alltid av exakt **2 hexadecimala siffror**:

```
Binärt:       1100 1111
Hex:             C    F    →  CF  (eller 0xCF)
Decimal:       207
```

Hexadecimala värden skrivs ofta med prefixet `0x` (programmering) eller `#` (CSS-färger, t.ex. `#FF8C00` för en orange nyans).
