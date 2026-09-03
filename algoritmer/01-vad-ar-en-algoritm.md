# Vad är en algoritm?

En **algoritm** är en exakt, steg-för-steg-beskrivning av hur man löser ett problem. Varje steg måste vara tydligt nog för att kunna följas utan att man behöver gissa — oavsett om det är en människa eller en dator som utför stegen.

Ordet *algoritm* kommer från namnet på den persiske matematikern **Muhammad ibn Musa al-Khwarizmi** (ca 780–850 e.Kr.), vars böcker om räknemetoder spreds till Europa och kom att kallas *algoritmi* på latin — en latinisering av hans namn.

{% hint style="info" %}
**Kom ihåg:** En algoritm är inte ett datorprogram. En algoritm är en idé — ett recept. Ett program är ett sätt att *uttrycka* den idén i ett språk som en dator förstår.
{% endhint %}

---

## Algoritmers historia

Algoritmer är äldre än datorer — faktiskt tusentals år äldre.

### Euklides algoritm (ca 300 f.Kr.)

En av de äldsta kända algoritmerna är **Euklides algoritm** för att hitta det största gemensamma delaren (SGD) av två tal. Den beskrevs av den grekiske matematikern Euklides i verket *Elementa* och fungerar precis lika bra idag som då.

> *Hur hittar man SGD av 48 och 18?*
> 1. Dela det större talet med det mindre: 48 ÷ 18 = 2, rest 12
> 2. Ersätt det större med det mindre, och det mindre med resten: nu jobbar vi med 18 och 12
> 3. Upprepa: 18 ÷ 12 = 1, rest 6 → jobba med 12 och 6
> 4. 12 ÷ 6 = 2, rest 0 → klart! SGD = **6**

### Al-Khwarizmi och algebra (800-talet e.Kr.)

Al-Khwarizmi gav inte bara namn åt algoritmen — hans bok *Al-Kitāb al-mukhtaṣar fī ḥisāb al-jabr wal-muqābala* gav också namn åt **algebran** (al-jabr). Han beskrev systematiska metoder för att lösa ekvationer, steg för steg.

### Ada Lovelace och den första datoralgoritmen (1843)

**Ada Lovelace** anses vara världens första programmerare. Hon skrev en algoritm för Charles Babbages analytiska maskin — en mekanisk räknemaskin som aldrig byggdes klart — för att beräkna Bernoullis tal. Det är den första algoritmen som var avsedd att köras på en maskin.

### Moderna algoritmer

Med datorernas intåg på 1900-talet exploderade algoritmforskningen. Idag styr algoritmer allt från hur din mobilkamera fokuserar till hur sociala medier väljer vad du ser i ditt flöde.

---

## Vad skiljer en algoritm från ett program?

Det är en viktig och vanlig fråga. Enkelt uttryckt:

| | **Algoritm** | **Program** |
|---|---|---|
| **Vad är det?** | En idé eller metod | En konkret implementation |
| **Språk** | Vanlig svenska, pseudokod, flödesschema | Python, Java, C++, … |
| **Kör på dator?** | Inte nödvändigtvis | Ja |
| **Exempel** | "Sortera listan från minst till störst" | `list.sort()` i Python |

Ett **recept** är ett bra exempel på en algoritm som inte är ett program: det beskriver exakt vad du ska göra, i vilken ordning, men det körs av en människa — inte en dator.

---

## Vad kännetecknar en bra algoritm?

En algoritm måste uppfylla tre krav:

1. **Ändlighet** — Den måste ta slut. En algoritm som aldrig slutar är inte användbar.
2. **Entydighet** — Varje steg måste vara tydligt. "Blanda lite" duger inte — "blanda i 2 minuter" är bättre.
3. **Korrekthet** — Den måste ge rätt svar för alla giltiga indata.
