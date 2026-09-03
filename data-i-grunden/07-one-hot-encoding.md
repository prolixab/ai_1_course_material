# 07 one hot encoding

## Problemet med kategorisk data

Maskininlärningsmodeller räknar — de tar siffror som indata och producerar siffror som utdata. Det fungerar bra för _numeriska_ features som ålder och antal klick, men vad gör vi med _kategoriska_ features som stad, betalningsmetod eller djurart?

## Det naiva misstaget: ordinal numrering

Intuitivt kan man tänka sig att bara numrera kategorierna:

```
Stockholm = 1
Göteborg  = 2
Malmö     = 3
```

**Det är fel.** Problemet är att modellen uppfattar denna numrering som en _ordning_ och ett _avstånd_:

* Göteborg (2) uppfattas som dubbelt så mycket som Stockholm (1)
* Skillnaden Stockholm–Göteborg = 1 uppfattas som lika stor som Göteborg–Malmö = 1
* Malmö (3) uppfattas som "mer" än Stockholm (1) på ett meningslöst sätt

Dessa antaganden stämmer inte för städer (eller för de flesta kategorier) och leder till systematiskt felaktiga modeller.

## Lösningen: one-hot encoding

**One-hot encoding** löser problemet. Man skapar en ny binär kolumn per kategori. I varje rad sätts exakt _en_ av dessa till 1 ("one-hot" — en het) och resten till 0.

### Städer

**Före encoding:**

| person\_id | stad      |
| ---------- | --------- |
| 1042       | Stockholm |
| 1043       | Göteborg  |
| 1044       | Malmö     |
| 1045       | Stockholm |

**Efter one-hot encoding:**

| person\_id | stad\_Stockholm | stad\_Göteborg | stad\_Malmö |
| ---------- | :-------------: | :------------: | :---------: |
| 1042       |        1        |        0       |      0      |
| 1043       |        0        |        1       |      0      |
| 1044       |        0        |        0       |      1      |
| 1045       |        1        |        0       |      0      |

Nu finns det **ingen implicit ordning**. Alla städer är matematiskt lika "långt ifrån" varandra. Modellen kan lära sig att just `stad_Stockholm`-kolumnen korrelerar med ett visst beteende, utan att blanda ihop den med de andra städerna.

### Betalningsmetoder

| Betalning | kort | swish | faktura | kontant |
| --------- | :--: | :---: | :-----: | :-----: |
| Kort      |   1  |   0   |    0    |    0    |
| Swish     |   0  |   1   |    0    |    0    |
| Faktura   |   0  |   0   |    1    |    0    |
| Kontant   |   0  |   0   |    0    |    1    |

## One-hot i Python

```python
import pandas as pd

df = pd.DataFrame({
    "person_id": [1042, 1043, 1044, 1045],
    "ålder":     [  34,   28,   51,   19],
    "stad":      ["Stockholm", "Göteborg", "Malmö", "Stockholm"],
})

# Metod 1: pd.get_dummies
df_encoded = pd.get_dummies(df, columns=["stad"])
print(df_encoded)
#    person_id  ålder  stad_Göteborg  stad_Malmö  stad_Stockholm
# 0       1042     34          False       False            True
# 1       1043     28           True       False           False
# 2       1044     51          False        True           False
# 3       1045     19          False       False            True

# Metod 2: scikit-learn OneHotEncoder (föredragen i ML-pipelines)
from sklearn.preprocessing import OneHotEncoder
import numpy as np

encoder = OneHotEncoder(sparse_output=False)
stad_encoded = encoder.fit_transform(df[["stad"]])
print(encoder.categories_)   # [array(['Göteborg', 'Malmö', 'Stockholm'])]
print(stad_encoded)
# [[0. 0. 1.]   ← Stockholm
#  [1. 0. 0.]   ← Göteborg
#  [0. 1. 0.]   ← Malmö
#  [0. 0. 1.]]  ← Stockholm
```

## The dummy variable trap

{% hint style="warning" %}
**Dummy variable trap:** Med k kategorier ger one-hot k kolumner. Men om man vet värdena för k−1 kolumner är det sista alltid givet (de summerar alltid till 1). Detta skapar **perfekt multikollinearitet** — ett statistiskt problem för regressionsmodeller.

Lösningen: ta bort en av kolumnerna (`drop_first=True` i pandas). Med 3 städer räcker 2 kolumner.
{% endhint %}

```python
# Med drop_first=True tas den första kategorin (Göteborg) bort som referens
df_encoded = pd.get_dummies(df, columns=["stad"], drop_first=True)
# Kvar: stad_Malmö, stad_Stockholm
# Göteborg = [0, 0], Malmö = [1, 0], Stockholm = [0, 1]
```

Neurala nätverk och trädbaserade modeller (Random Forest, XGBoost) behöver vanligtvis inte `drop_first` — det är primärt ett problem för linjär regression och logistisk regression.

## Feature-vektorn — allt sammanfört

När alla features är numeriska och kategorier är one-hot-kodade kan en persons hela rad skrivas som en lång lista av tal — en **feature-vektor**. Det är precis det format som matematiska modeller och neurala nätverk förväntar sig.

```python
# Komplett rad för person 1044 (Fatima Osman):
#
# ålder  klick  prenumerant  stad_Gtbg  stad_Malmö  stad_Sthlm
#   51    14         1           0           1           0
#
x = [51, 14, 1, 0, 1, 0]

# Alla fyra personerna som en matris (4 rader × 6 features):
X = np.array([
    [34,  7, 1, 0, 0, 1],   # Anna,    Stockholm
    [28,  2, 0, 1, 0, 0],   # Carlos,  Göteborg
    [51, 14, 1, 0, 1, 0],   # Fatima,  Malmö
    [19,  0, 0, 0, 0, 1],   # Erik,    Stockholm
])

print(X.shape)  # → (4, 6)   — 4 exempel, 6 features vardera
```

Denna matris `X` kan nu skickas direkt till en scikit-learn-modell:

```python
from sklearn.linear_model import LogisticRegression

y = [1, 0, 1, 0]   # prenumerant: 1=ja, 0=nej (målvariabeln)

modell = LogisticRegression()
modell.fit(X, y)   # modellen lär sig nu från datan
```

## Alternativ till one-hot

One-hot fungerar bra för kategorier med få möjliga värden. För kategorier med många värden (t.ex. postnummer, produktkod, landnamn) kan one-hot ge explosivt många kolumner — ett problem känt som _the curse of dimensionality_.

| Teknik               | Passar när                                        | Nackdel                     |
| -------------------- | ------------------------------------------------- | --------------------------- |
| **One-hot**          | Få kategorier (< \~20)                            | Växer med antal kategorier  |
| **Ordinal encoding** | Det finns en naturlig ordning (liten/medium/stor) | Inför falskt avstånd        |
| **Target encoding**  | Många kategorier                                  | Risk för datläckage         |
| **Embedding**        | Många kategorier, djupinlärning                   | Kräver mer data och träning |

**Embeddings** är speciellt viktiga att känna till: i stället för att en kategori ger en gles one-hot-vektor, lär sig modellen en kompakt tät vektor (t.ex. 50 tal). Ord i språkmodeller representeras alltid som embeddings — det är grunden i Word2Vec, GloVe och moderna transformers.

***

## Sammanfattning av avsnittet

```
Rådata              Representation          Redo för modell
──────              ──────────────          ───────────────
34 (ålder)    →    34                  →   34
"Stockholm"   →    one-hot [0, 0, 1]   →   0, 0, 1
True (pren.)  →    1                   →   1
14 (klick)    →    14                  →   14

Resultat: x = [34, 0, 0, 1, 1, 14]  — en vektor av tal
```

Datorn "ser" nu bara dessa vektorer. Det är på dessa representationer som modeller som beslutsträd, linjär regression och neurala nätverk arbetar. Konsten att välja och omvandla features kallas **feature engineering** och är en central del av maskininlärningens praktik.

**Nästa steg:** hur en modell faktiskt lär sig mönster i dessa talvektorer — optimering, förlustfunktioner och gradientmetoden.
