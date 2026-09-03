# 04 bilder

## Pixlar och färger

En digital bild är ett rutnät av **pixlar** (picture elements). Varje pixel har en färg. Färger representeras nästan alltid med **RGB**: tre tal (0–255) som anger hur mycket rött, grönt och blått som blandas.

```
                   Mer rött →
         0    64   128   192   255
    0    ░░░  ▒▒▒  ▓▓▓  ███  ███
   64    ░░░  ...
  128
  192
  255
```

### RGB-exempel

| Färg      | Röd | Grön | Blå | Hex       |
| --------- | --: | ---: | --: | --------- |
| Svart     |   0 |    0 |   0 | `#000000` |
| Vit       | 255 |  255 | 255 | `#FFFFFF` |
| Röd       | 255 |    0 |   0 | `#FF0000` |
| Grön      |   0 |  200 |   0 | `#00C800` |
| Blå       |   0 |    0 | 255 | `#0000FF` |
| Orange    | 255 |  140 |   0 | `#FF8C00` |
| Grå (50%) | 128 |  128 | 128 | `#808080` |

### En pixel som bytes

En enda orange pixel (255, 140, 0) lagras som tre bytes:

```
Kanal       Decimal   Binärt
─────────────────────────────
Röd         255       11111111
Grön        140       10001100
Blå         0         00000000

Totalt: 3 bytes = 24 bitar per pixel
```

## Hur en bild ser ut i minnet

En 4×3-pixels liten bild lagras som en lång lista av RGB-värden, rad för rad:

```
Pixel (0,0)       Pixel (1,0)       Pixel (2,0)       Pixel (3,0)
[255, 0, 0]       [0, 255, 0]       [0, 0, 255]       [255, 255, 0]
Pixel (0,1)       ...
[0, 0, 0]
```

I Python med NumPy representeras en bild som en tredimensionell array med formen `(höjd, bredd, 3)`:

```python
import numpy as np

# En 4×3 bild (3 rader, 4 kolumner, 3 kanaler)
bild = np.array([
    [[255,   0,   0], [  0, 255,   0], [  0,   0, 255], [255, 255,   0]],
    [[  0,   0,   0], [128, 128, 128], [255, 255, 255], [255, 140,   0]],
    [[100,  50, 200], [200, 100,  50], [ 50, 200, 100], [ 10,  10,  10]],
], dtype=np.uint8)

print(bild.shape)  # → (3, 4, 3)
print(bild[0, 0])  # → [255, 0, 0]  — övre vänstra pixeln: röd
```

## Upplösning och filstorlek

| Format    | Upplösning    |    Pixlar | Råstorlek (RGB) |
| --------- | ------------- | --------: | --------------: |
| Thumbnail | 100 × 100     |    10 000 |         ≈ 30 KB |
| HD        | 1 280 × 720   |   921 600 |        ≈ 2,6 MB |
| Full HD   | 1 920 × 1 080 | 2 073 600 |        ≈ 5,9 MB |
| 4K        | 3 840 × 2 160 | 8 294 400 |       ≈ 23,7 MB |

{% hint style="info" %}
**Färgdjup:** Standardmässigt används 8 bitar per kanal (24 bitar per pixel), vilket ger 256³ ≈ 16,7 miljoner möjliga färger. Professionell fotografi och film använder ibland 10 eller 12 bitar per kanal för större nyansrikedom.
{% endhint %}

## Komprimering

Råstorlekarna ovan är impraktiskt stora. Bildformat komprimerar data:

* **PNG:** förlustfri komprimering — pixelvärdena bevaras exakt. Bra för skärmdumpar och grafik med skarpa kanter.
* **JPEG:** förlustgivande komprimering — kastar bort bilddetaljer som ögat knappt märker. Bra för fotografier; kan minska filstorleken 10–20×.
* **WebP:** modernare format som kombinerar fördelar från båda; ofta 25–35% mindre än JPEG vid likvärdig kvalitet.

## Gråskala och alfakanal

Alla bilder har inte tre kanaler:

* **Gråskala:** 1 kanal (0 = svart, 255 = vit). Hälften så stor som RGB.
* **RGBA:** 4 kanaler — RGB plus en **alfakanal** (genomskinlighet, 0 = helt transparent, 255 = helt ogenomskinlig). Används för PNG-bilder med transparens.

## Bilder i maskininlärning

När en bild matas in i ett neuralt nätverk plattas den ut till en lång vektor — eller behandlas direkt som en 3D-tensor av ett konvolutionellt neuralt nätverk (CNN). En 28×28-pixels gråskalebild (som i MNIST-datasetet) ger en vektor med 784 tal.

```python
# Platta ut en bild för ett fullt anslutet nätverk
bild_flat = bild.flatten()   # shape (3, 4, 3) → (36,)

# Normalisera pixelvärdena till intervallet [0, 1]
bild_norm = bild.astype(np.float32) / 255.0
```

Normalisering till \[0, 1] eller \[−1, 1] är nästan alltid nödvändigt — neurala nätverk fungerar bättre med tal i små intervall.
