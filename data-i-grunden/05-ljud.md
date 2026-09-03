# 05 ljud

## Diskret tid, kontinuerlig värld

Ljud är tryckvågor — ett kontinuerligt fysikaliskt fenomen. Lufttrycket varierar smidigt tusentals gånger per sekund. För att lagra det digitalt måste vi _diskretisera_ det: mäta lufttrycket vid fasta tidpunkter och runda av till ett ändligt antal nivåer.

```
Lufttryck
   │
   │    ╭──╮         ╭──╮
   │   ╱    ╲       ╱    ╲
   │──╱──────╲─────╱──────╲──────  ← nollnivå
   │           ╲   ╱
   │            ╲─╱
   │
   └─────────────────────────────→ Tid (kontinuerlig signal)

   Sampel (diskret signal):
   │ ↕  ↕  ↕  ↕  ↕  ↕  ↕  ↕  ↕
   └─────────────────────────────→ Tid
```

Varje sådan mätpunkt kallas ett **sampel**.

## Samplingsfrekvens

**Samplingsfrekvensen** (engelska: _sample rate_) mäts i Hertz (Hz) och anger hur många sampel som tas per sekund.

| Standard                   |            Frekvens | Används för               |
| -------------------------- | ------------------: | ------------------------- |
| Telefonkvalitet            |            8 000 Hz | Taltelefoni               |
| AM-radio                   |           22 050 Hz | —                         |
| **CD-kvalitet**            |       **44 100 Hz** | **Musik, standard**       |
| DVD-audio / studiokvalitet |           48 000 Hz | Film, professionellt ljud |
| Hi-res audio               | 96 000 / 192 000 Hz | Audiofilt                 |

### Nyquist-teoremet

För att återge ett ljud med frekvens _f_ Hz utan förvrängning krävs en samplingsfrekvens på **minst 2f Hz**.

Människan hör upp till ca 20 000 Hz. Därför:

```
Minsta samplingsfrekvens = 2 × 20 000 = 40 000 Hz
CD-standard: 44 100 Hz  (med lite marginal)
```

Om samplingsfrekvensen är för låg uppstår **aliasing** — ett artificiellt ljud som inte fanns i originalsignalen.

## Bitdjup

**Bitdjupet** anger precisionen för varje enskild mätning: hur många diskreta nivåer som finns tillgängliga för att representera lufttrycket vid varje sampel.

|      Bitdjup |     Nivåer |     Dynamikområde    | Används för         |
| -----------: | ---------: | :------------------: | ------------------- |
|        8 bit |        256 |         48 dB        | Äldre spel, talchip |
|   **16 bit** | **65 536** |       **96 dB**      | **CD, streaming**   |
|       24 bit | 16 777 216 |        144 dB        | Studioinspelning    |
| 32 bit float |          — | praktiskt obegränsat | DAW-bearbetning     |

```
16-bitars sampel:
  0000000000000000 = tystnad (nollnivå)
  0111111111111111 = maximal positiv utslag
  1000000000000000 = maximal negativ utslag
```

## Filstorlek för råljud

```
# En minuts CD-stereo-ljud, okomprimerat (WAV/PCM):

44 100 sampel/s × 60 s × 2 kanaler × 2 bytes/sampel
= 10 584 000 bytes ≈ 10 MB
```

| Format         |  Komprimering  | 1 minuts stereo | Kvalitetsförlust |
| -------------- | :------------: | --------------: | :--------------: |
| WAV / AIFF     |      Ingen     |         ≈ 10 MB |       Ingen      |
| FLAC           |   Förlustfri   |        ≈ 5–6 MB |       Ingen      |
| MP3 (320 kbps) | Förlustgivande |        ≈ 2,4 MB |      Minimal     |
| MP3 (128 kbps) | Förlustgivande |          ≈ 1 MB |      Märkbar     |
| Opus (96 kbps) | Förlustgivande |        ≈ 720 KB |      Minimal     |

{% hint style="info" %}
**MP3 och psykoakustik:** MP3 kastar inte bort slumpmässiga bitar. Den använder en modell av det mänskliga hörselsystemet för att identifiera vilka frekvenser och detaljer som ändå inte uppfattas — till exempel ett svagt ljud som maskeras av ett starkt. Bara det som "inte hörs" kastas bort.
{% endhint %}

## Ljud som data i Python

```python
import numpy as np

# Simulera 1 sekund av en 440 Hz sinuston (A4, "kammartonen")
sample_rate = 44100          # sampel per sekund
duration = 1.0               # sekunder
t = np.linspace(0, duration, int(sample_rate * duration))

# Sinusvåg: amplitud × sin(2π × frekvens × tid)
signal = 0.5 * np.sin(2 * np.pi * 440 * t)

print(f"Antal sampel: {len(signal)}")  # → 44100
print(f"Första 5 sampel: {signal[:5]}")
# → [ 0.      0.0626  0.1247  0.1861  0.2462]
```

## Ljud i maskininlärning

Råa sampelvärden används sällan direkt som features — sekvensen är för lång och informationen för utspridd. Vanliga representationer:

* **Spektrogram:** en 2D-bild av hur frekvensinnehållet förändras över tid. Kan behandlas av CNN precis som vanliga bilder.
* **Mel-spektrogram:** ett spektrogram skalat efter hur det mänskliga örat uppfattar frekvenser — vanligast inom talarigenkänning och musikanalys.
* **MFCC (Mel-Frequency Cepstral Coefficients):** en komprimerad representation av spektromet, klassisk inom taligenkänning.

```python
# Mel-spektrogram med librosa
import librosa
import librosa.display

y, sr = librosa.load("inspelning.wav", sr=22050)
mel = librosa.feature.melspectrogram(y=y, sr=sr, n_mels=128)
log_mel = librosa.power_to_db(mel, ref=np.max)

# log_mel har nu formen (128, tidssteg) — en 2D-matris redo för ett CNN
print(log_mel.shape)  # → (128, 87)  för en 2 s fil
```
