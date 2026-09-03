# Flödesscheman

Ett **flödesschema** (eng. *flowchart*) är ett visuellt sätt att beskriva en algoritm. Det använder standardiserade symboler:

| Symbol | Form | Betydelse |
|---|---|---|
| **Start/Slut** | Rektangel med rundade hörn | Algoritmen börjar eller slutar |
| **Process** | Rektangel | En åtgärd eller beräkning utförs |
| **Beslut** | Romb | En fråga med Ja/Nej-svar styr flödet |
| **Indata/Utdata** | Parallellogram | Läs in data eller skriv ut ett resultat |
| **Pil** | → | Visar i vilken ordning stegen utförs |

---

## Flödesschema 1 — Grundstruktur för en algoritm

```mermaid
flowchart TD
    A([Start]) --> B[/Läs in indata/]
    B --> C[Bearbeta data]
    C --> D{Är svaret klart?}
    D -- Nej --> C
    D -- Ja --> E[/Skriv ut resultat/]
    E --> F([Slut])
```

---

## Flödesschema 2 — Euklides algoritm

```mermaid
flowchart TD
    A([Start]) --> B[/Läs in a och b/]
    B --> C{b = 0?}
    C -- Ja --> D[/Skriv ut a\nDetta är SGD/]
    D --> E([Slut])
    C -- Nej --> F[rest ← a MOD b]
    F --> G[a ← b]
    G --> H[b ← rest]
    H --> C
```

**Läs flödesschemat:** Starta uppifrån. Vid romben frågar vi om `b = 0`. Om ja är vi klara. Om nej beräknar vi en ny rest och loopar tillbaka till frågan.

---

## Flödesschema 3 — Linjärsökning

```mermaid
flowchart TD
    A([Start]) --> B[/Läs in lista och sökterm/]
    B --> C[i ← 0]
    C --> D{i < längd på lista?}
    D -- Nej --> E[/Skriv ut: Hittades inte/]
    E --> F([Slut])
    D -- Ja --> G{lista_i_ = sökterm?}
    G -- Ja --> H[/Skriv ut: Hittad på plats i/]
    H --> F
    G -- Nej --> I[i ← i + 1]
    I --> D
```

---

## Flödesschema 4 — Binärsökning

```mermaid
flowchart TD
    A([Start]) --> B[/Läs in sorterad lista och sökterm/]
    B --> C[vänster ← 0\nhöger ← sista index]
    C --> D{vänster ≤ höger?}
    D -- Nej --> E[/Hittades inte/]
    E --> F([Slut])
    D -- Ja --> G[mitten ← vänster+höger / 2]
    G --> H{lista_mitten_ = sökterm?}
    H -- Ja --> I[/Hittad på plats mitten/]
    I --> F
    H -- Nej --> J{lista_mitten_ < sökterm?}
    J -- Ja --> K[vänster ← mitten + 1]
    J -- Nej --> L[höger ← mitten - 1]
    K --> D
    L --> D
```

{% hint style="info" %}
**Tips:** Jämför flödesschemat för linjärsökning med binärsökning. Hur skiljer sig looparna åt? Varför behöver binärsökning tre beslutspunkter?
{% endhint %}
