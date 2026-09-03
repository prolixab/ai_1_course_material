# 06 personlig information

## Strukturerad data och tabeller

Till skillnad från bilder och ljud lagras personuppgifter oftast som **strukturerad data** — information organiserad i rader och kolumner. En rad representerar ett _objekt_ (en person, ett köp, ett besök), en kolumn representerar ett _attribut_.

### Exempeltabell

| person\_id | namn          | ålder | stad      | prenumerant | klick\_idag |
| ---------- | ------------- | ----: | --------- | :---------: | ----------: |
| 1042       | Anna Lindgren |    34 | Stockholm |      ✓      |           7 |
| 1043       | Carlos Méndez |    28 | Göteborg  |      —      |           2 |
| 1044       | Fatima Osman  |    51 | Malmö     |      ✓      |          14 |
| 1045       | Erik Nilsson  |    19 | Stockholm |      —      |           0 |

Varje kolumn har en **datatyp** som avgör hur värdet lagras och vilka operationer som är giltiga:

| Datatyp              | Exempel         | Lagringsformat                               |
| -------------------- | --------------- | -------------------------------------------- |
| Heltal (`int`)       | 34, 7, 0        | 1–8 bytes beroende på storlek                |
| Decimaltal (`float`) | 3.14, 1.5e-3    | 4 eller 8 bytes (IEEE 754)                   |
| Text (`string`)      | "Anna Lindgren" | bytes enligt UTF-8                           |
| Boolean (`bool`)     | sant/falskt     | 1 bit (ofta lagrat som 1 byte)               |
| Datum (`date`)       | 2024-03-15      | ofta 4 bytes (dagar sedan ett referensdatum) |

## Datatyper på djupet

### Heltal

Heltal lagras i fast antal bytes. Antalet bytes avgör intervallet:

```
int8   (1 byte):  −128  till  127
int16  (2 bytes): −32 768  till  32 767
int32  (4 bytes): −2 147 483 648  till  2 147 483 647
int64  (8 bytes): ≈ −9,2 × 10¹⁸  till  ≈ 9,2 × 10¹⁸

uint8  (1 byte, utan tecken):  0  till  255
```

### Decimaltal (floating point)

Decimaltal representeras med **IEEE 754**-standarden. En 32-bitars float har:

```
1 bit  →  tecken (+ eller −)
8 bitar  →  exponent (tiopotensen)
23 bitar →  mantissa (de signifikanta siffrorna)

Exempel: talet 3.14
  0  01111111  10010001111010111000011
  │  ────┬───  ──────────────┬────────
 +1    exp=127         mantissa
```

{% hint style="warning" %}
**Avrundningsfel:** Decimaltal som `0.1` kan inte representeras exakt i binär floating point. `0.1 + 0.2` i Python ger `0.30000000000000004`. Använd aldrig `==`-jämförelser med floats — använd istället ett toleransintervall: `abs(a - b) < 1e-9`.
{% endhint %}

## Tabeller i maskininlärning

I maskininlärning kallas kolumnerna ofta **features** (egenskaper) och varje rad kallas ett **exempel** eller en **observation**. Det man vill förutsäga kallas **målvariabeln** eller **etiketten** (_label_).

```python
import pandas as pd

df = pd.DataFrame({
    "ålder":       [34, 28, 51, 19],
    "klick_idag":  [ 7,  2, 14,  0],
    "prenumerant": [ 1,  0,  1,  0],   # bool → 1/0
    "stad":        ["Stockholm", "Göteborg", "Malmö", "Stockholm"],
})

print(df.dtypes)
# ålder          int64
# klick_idag     int64
# prenumerant    int64
# stad           object (text — behöver omvandlas!)
```

`stad`-kolumnen kan inte användas direkt — den måste omvandlas till tal. Det är ämnet för nästa avsnitt.

## Integritet och anonymisering

Persondata måste hanteras varsamt, både juridiskt (GDPR i EU) och etiskt. Vanliga tekniker:

**Anonymisering** tar bort alla identifierande uppgifter (namn, personnummer, adress). Svårare än det låter — kombinationer av attribut kan fortfarande peka ut en individ.

**Pseudonymisering** ersätter direktidentifierare med koder eller hash-värden. Kopplingen kan återställas om man har nyckeln — pseudonymisering är inte anonymisering.

**Aggregering** publicerar bara statistik (medelvärden, antal) i stället för individdata. Ger inte svar på frågor om enskilda individer.

**Differentiell integritet** (_differential privacy_) lägger till kontrollerat brus på individuell nivå så att statistiken är korrekt men enskilda rader inte kan rekonstrueras. Används av bl.a. Apple och Google.

{% hint style="info" %}
**GDPR och AI:** Att träna en maskininlärningsmodell på persondata räknas juridiskt som "behandling" av persondata. Det kräver rättslig grund (t.ex. samtycke eller berättigat intresse) och ska dokumenteras. En tränad modell kan dessutom "läcka" träningsdata om den inte är korrekt designad.
{% endhint %}
