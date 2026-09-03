# Data i grunden

**AI 1 · Kursmaterial**

Hur datorer egentligen lagrar och representerar information — från binära tal till text, bilder, ljud och maskininlärningens features.

## Vad det här materialet täcker

| Avsnitt                                         | Ämne                                    |
| ----------------------------------------------- | --------------------------------------- |
| [01 · Vad är data?](01-vad-ar-data.md)          | Definition och grundprincip             |
| [02 · Binära tal](02-binara-tal.md)             | Bitar, bytes och det binära systemet    |
| [03 · Text](03-text.md)                         | ASCII, Unicode och UTF-8                |
| [04 · Bilder](04-bilder.md)                     | Pixlar, RGB och upplösning              |
| [05 · Ljud och musik](05-ljud.md)               | Sampling, samplingsfrekvens och bitdjup |
| [06 · Personlig information](06-personlig-information.md) | Strukturerad data och tabeller  |
| [07 · One-hot encoding](07-one-hot-encoding.md) | Kategorisk data och feature-vektorer    |

## Den röda tråden

All information — text, bild, ljud, video, mätdata — kan kodas som tal. Och alla tal kan representeras i det binära talsystemet. Det är denna kedja av omvandlingar som gör det möjligt för datorer att hantera hela vår informationsvärld med transistorer som bara kan vara på eller av.

I maskininlärning är förståelsen av datarepresentation central: en modell lär sig aldrig av "en bild av en katt" — den lär sig av en lång vektor med tal som representerar pixlarnas RGB-värden. Den lär sig aldrig av "Stockholm" — den lär sig av `[1, 0, 0]` efter att vi tillämpat one-hot encoding.

{% hint style="info" %}
**Nästa steg efter det här materialet:** hur en modell faktiskt lär sig mönster i dessa talvektorer — optimering, förlustfunktioner och gradientmetoden.
{% endhint %}
