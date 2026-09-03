# Pseudokod

**Pseudokod** är ett sätt att beskriva en algoritm i en form som liknar programkod, men som är skriven för att vara lättläst för människor — inte för datorer. Det finns inget standardiserat pseudokodspråk; man väljer ord och struktur som gör algoritmen tydlig.

Pseudokod är ett viktigt mellansteg: man kan designa och diskutera en algoritm i pseudokod *innan* man väljer vilket programspråk man ska implementera den i.

{% hint style="info" %}
**Pseudokod används för att:** tänka igenom en lösning, kommunicera en algoritm till andra, och dokumentera logiken oberoende av programspråk.
{% endhint %}

---

## Grundläggande byggstenar

De flesta algoritmer byggs av tre grundläggande konstruktioner:

| Konstruktion | Beskrivning | Exempel |
|---|---|---|
| **Sekvens** | Steg utförs ett i taget, i ordning | `läs in tal` → `beräkna` → `skriv ut svar` |
| **Villkor** | Ett steg utförs bara om ett villkor är sant | `OM tal > 0 DÅ skriv "positivt"` |
| **Upprepning** | Ett block av steg upprepas | `MEDAN rest ≠ 0 GÖR ...` |

---

## Exempel 1 — Hitta det störta talet i en lista

```
ALGORITM HittaStörst(lista)
  störst ← lista[0]
  FÖR VARJE tal I lista GÖR
    OM tal > störst DÅ
      störst ← tal
    SLUT OM
  SLUT FÖR
  RETURNERA störst
SLUT ALGORITM
```

**Förklaring:** Vi börjar med att anta att det första elementet är störst. Sedan jämför vi varje element i listan med vår nuvarande kandidat. Om vi hittar något större, uppdaterar vi kandidaten. Till slut returnerar vi svaret.

---

## Exempel 2 — Euklides algoritm

```
ALGORITM SGD(a, b)
  MEDAN b ≠ 0 GÖR
    rest ← a MOD b     (rest vid heltalsdivision)
    a ← b
    b ← rest
  SLUT MEDAN
  RETURNERA a
SLUT ALGORITM
```

**Exempel:** `SGD(48, 18)` → rest = 12 → `SGD(18, 12)` → rest = 6 → `SGD(12, 6)` → rest = 0 → **returnerar 6**

---

## Exempel 3 — Linjärsökning

Linjärsökning är den enklaste sökalgoritmen: gå igenom listan från början till slut tills du hittar det du söker.

```
ALGORITM LinjärSökning(lista, sökterm)
  FÖR i ← 0 TILL längd(lista) - 1 GÖR
    OM lista[i] = sökterm DÅ
      RETURNERA i          (positionen där vi hittade den)
    SLUT OM
  SLUT FÖR
  RETURNERA -1             (-1 betyder "hittades inte")
SLUT ALGORITM
```

---

## Exempel 4 — Binärsökning

Binärsökning fungerar bara på en *sorterad* lista, men är mycket snabbare: den halverar sökområdet vid varje steg.

```
ALGORITM BinärSökning(lista, sökterm)
  vänster ← 0
  höger  ← längd(lista) - 1

  MEDAN vänster ≤ höger GÖR
    mitten ← (vänster + höger) / 2  (heltalsdivision)

    OM lista[mitten] = sökterm DÅ
      RETURNERA mitten
    ANNARS OM lista[mitten] < sökterm DÅ
      vänster ← mitten + 1           (sök i högra halvan)
    ANNARS
      höger ← mitten - 1             (sök i vänstra halvan)
    SLUT OM
  SLUT MEDAN

  RETURNERA -1
SLUT ALGORITM
```

{% hint style="info" %}
**Jämförelse:** För en lista med 1 000 element behöver linjärsökning i värsta fall **1 000 jämförelser**. Binärsökning behöver bara **10**. Det är skillnaden mellan O(n) och O(log n) — ett viktigt begrepp inom algoritmlära.
{% endhint %}
