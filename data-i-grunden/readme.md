# README

**AI 1 · Kursmaterial**

Hur datorer egentligen lagrar och representerar information — från binära tal till text, bilder, ljud och maskininlärningens features.

## Vad det här materialet täcker

| Avsnitt                                                                              | Ämne                                    |
| ------------------------------------------------------------------------------------ | --------------------------------------- |
| [01 · Vad är data?](/broken/pages/a341cf5b3345625b6fe61769f6928068cfa5de72)          | Definition och grundprincip             |
| [02 · Binära tal](/broken/pages/b00b911a36ad58a3c973a390d4085d524fb78410)            | Bitar, bytes och det binära systemet    |
| [03 · Text](/broken/pages/3b7b1822f8ef8758c9ef98ed1cb9f6622a8488ae)                  | ASCII, Unicode och UTF-8                |
| [04 · Bilder](/broken/pages/7cb2dca356298810c47f74fc17e52d57332a466c)                | Pixlar, RGB och upplösning              |
| [05 · Ljud och musik](/broken/pages/acd3b91972912c2409dcb58643457dfa83d5f98e)        | Sampling, samplingsfrekvens och bitdjup |
| [06 · Personlig information](/broken/pages/ce8307a8bad783818de6c6b81d52383dd2dd6376) | Strukturerad data och tabeller          |
| [07 · One-hot encoding](/broken/pages/cdd379368481c148ab0761ed9666ca053187fa14)      | Kategorisk data och feature-vektorer    |

## Den röda tråden

All information — text, bild, ljud, video, mätdata — kan kodas som tal. Och alla tal kan representeras i det binära talsystemet. Det är denna kedja av omvandlingar som gör det möjligt för datorer att hantera hela vår informationsvärld med transistorer som bara kan vara på eller av.

I maskininlärning är förståelsen av datarepresentation central: en modell lär sig aldrig av "en bild av en katt" — den lär sig av en lång vektor med tal som representerar pixlarnas RGB-värden. Den lär sig aldrig av "Stockholm" — den lär sig av `[1, 0, 0]` efter att vi tillämpat one-hot encoding.

{% hint style="info" %}
**Nästa steg efter det här materialet:** hur en modell faktiskt lär sig mönster i dessa talvektorer — optimering, förlustfunktioner och gradientmetoden.
{% endhint %}
