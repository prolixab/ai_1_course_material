# AI historia



## 1. Vad är artificiell intelligens?

Artificiell intelligens (AI) är ett område inom datavetenskap som handlar om att skapa system och program som kan utföra uppgifter som normalt kräver mänsklig intelligens. Det kan handla om att förstå språk, känna igen bilder, fatta beslut, lösa problem eller lära sig av erfarenhet.

Begreppet "intelligens" är dock svårdefinierat. Det finns ingen universellt accepterad definition av vad intelligens egentligen är — varken hos människor eller maskiner. Det är just denna filosofiska grundfråga som gjort AI till ett fascinerande och kontroversiellt forskningsfält sedan starten.

### Olika typer av AI

| Typ                     | Beskrivning                                                                                                           | Status                              |
| ----------------------- | --------------------------------------------------------------------------------------------------------------------- | ----------------------------------- |
| **Smal AI (Narrow AI)** | System optimerade för en specifik uppgift, t.ex. att spela schack, identifiera ansikten eller rekommendera filmer.    | Existerar idag — all AI vi använder |
| **Generell AI (AGI)**   | En hypotetisk AI med samma breda kognitiva förmåga som en människa — kan lösa vilken intellektuell uppgift som helst. | Existerar inte ännu                 |
| **Superintelligens**    | En teoretisk AI som överstiger mänsklig intelligens inom alla områden.                                                | Spekulativt begrepp                 |

{% hint style="info" %}
**Viktigt att veta:** När media rapporterar om AI idag handlar det nästan alltid om _smal AI_ — system som är mycket bra på en sak, men som saknar generell förståelse eller medvetande.
{% endhint %}

## 2. Pionjärerna – grunden läggs (1940–1955)

Länge innan termen "artificiell intelligens" myntades lade matematiker, filosofer och ingenjörer grunden till det som skulle bli ett av 1900-talets mest transformativa vetenskapliga fält. Tre centrala genombrott under 1940- och tidiga 1950-talet var avgörande.

### McCulloch-Pitts-neuronen (1943)

Neurologen **Warren McCulloch** och matematikern **Walter Pitts** publicerade 1943 en banbrytande artikel: _A Logical Calculus of the Ideas Immanent in Nervous Activity_. De visade att biologiska nervceller (neuroner) kan beskrivas matematiskt som logiska grindar (AND, OR, NOT). Deras modell — McCulloch-Pitts-neuronen — lade grunden för artificiella neurala nätverk och är fortfarande relevant idag.

### Alan Turing och Turing-testet (1950)

Den brittiske matematikern **Alan Turing** publicerade 1950 sin epokgörande artikel _Computing Machinery and Intelligence_ med den inledande frågan: _"Can machines think?"_

Turing föreslog ett operationellt test: Om en människa, via textkonversation, inte kan avgöra om de kommunicerar med en maskin eller en annan människa — har maskinen visat intelligens. Detta kallas **Turing-testet** och diskuteras aktivt än idag.

{% hint style="info" %}
**Person: Alan Turing (1912–1954)**\
_&#x4D;atematiker, kryptograf och datavetenskapens fader_

Turing anses av många som den moderna datorvetenskapens grundare. Under andra världskriget knäckte han Enigma-koden, vilket förkortat kriget avsevärt. Hans teoretiska arbeten om beräkningsbarhet (Turing-maskinen) och maskinintelligens lade grunden för hela datavetenskap. Han förföljdes för sin homosexualitet och avled 1954 under omständigheter som fortfarande debatteras.
{% endhint %}

### Perceptronen (1957)

Psykologen **Frank Rosenblatt** vid Cornell University skapade 1957 perceptronen — den första träningsbara artificiella neuronen. Till skillnad från McCulloch-Pitts-modellen kunde perceptronen _lära sig_ från data. Rosenblatt implementerade den i hårdvara (Mark I Perceptron) och demonstrerade hur maskinen kunde lära sig känna igen enkla mönster. Detta skapade enorm entusiasm och lade grunden för moderna neurala nätverk.

## 3. AI:s officiella födelse (1956)

Sommaren 1956 samlades ett tiotal av dåtidens främsta matematiker och datavetare vid **Dartmouth College** i New Hampshire, USA. Det var John McCarthy, Marvin Minsky, Claude Shannon och Nathaniel Rochester som arrangerat mötet.

I sin ansökan om finansiering formulerade de den centrala hypotesen:

> _"Vi föreslår att en sommarforskningsstudie om artificiell intelligens genomförs utgående från antagandet att varje aspekt av lärande eller varje annan egenskap av intelligens i princip kan beskrivas så exakt att en maskin kan simulera den."_
>
> — Dartmouth-ansökan, 1955

Det var vid denna konferens som termen **"Artificial Intelligence"** myntades av John McCarthy. Mötet resulterade inte i de stora genombrotten man hoppats på, men det skapade ett nätverk av forskare och etablerade AI som ett legitimt akademiskt fält.

### Dartmouth-konferensens deltagare

| Person             | Bidrag                                                           |
| ------------------ | ---------------------------------------------------------------- |
| **John McCarthy**  | Myntade termen AI, uppfann programspråket LISP                   |
| **Marvin Minsky**  | Pionjär inom neurala nätverk och kognitiv vetenskap              |
| **Claude Shannon** | Informationsteorins fader, la grunden för digital kommunikation  |
| **Herbert Simon**  | Nobelpristagare, skapade Logic Theorist med Allen Newell         |
| **Allen Newell**   | Skapade Logic Theorist, föregångaren till automatiskt resonemang |

## 4. De tidiga lovtalen och första framstegen (1956–1974)

Åren efter Dartmouth-konferensen präglades av enorm entusiasm. Forskare skapade program som verkade remarkabelt intelligenta, och ledande vetenskapsmän förutspådde att mänsklig nivå av AI var bara ett decennium bort.

### Logic Theorist och General Problem Solver (1956–1957)

Herbert Simon och Allen Newell skapade **Logic Theorist** (1956) — det första programmet som kunde bevisa matematiska satser. Det bevisade 38 av 52 satser i Whitehead och Russells _Principia Mathematica_. 1957 följde **General Problem Solver (GPS)** — ett program designat att lösa generella problem med hjälp av "means-ends analysis".

### ELIZA – den första chatboten (1966)

**Joseph Weizenbaum** vid MIT skapade ELIZA — ett program som simulerade en psykoterapeut genom enkla mönstermatchningstekniker. Trots att ELIZA inte förstod vad den sa, reagerade många användare som om de pratade med en riktig terapeut.

{% hint style="info" %}
**ELIZA-effekten:** Tendensen hos människor att tillskriva mänskliga egenskaper och förståelse till ett program som egentligen bara matchar mönster i text. Weizenbaum var själv oroad över hur lätt folk anthropomorfiserade hans program och varnade för farorna med naiv tilltro till AI.
{% endhint %}

ELIZA-effekten är högst relevant idag när vi interagerar med moderna chatbottar.

### Shakey – den första autonoma roboten (1966–1972)

Stanford Research Institute byggde **Shakey** — en robot som kunde navigera, planera rörelserna och reagera på sin omgivning. Shakey kombinerade datorseende, planering och rörelsestyrning — allt som idag kallas robotik och autonom körning.

### Överdrivna förutsägelser

Under denna period gjordes remarkabelt optimistiska förutsägelser:

> _"Maskiner kommer att kunna, inom tjugo år, utföra allt arbete som en människa kan göra."_
>
> — Herbert Simon, 1965

> _"Inom en generation kommer problemet med att skapa artificiell intelligens att i allt väsentligt vara löst."_
>
> — Marvin Minsky, 1967

## 5. Första AI-vintern (1974–1980)

I mitten av 1970-talet stod det klart att de optimistiska förutsägelserna inte skulle infrias. Datorerna var för långsamma, minnet för litet och problemen mycket svårare än man trott. Resultatet var kraftigt minskad finansiering — en period som kallas den **första AI-vintern**.

### Lighthill-rapporten (1973)

Den brittiske matematikern **Sir James Lighthill** publicerade på uppdrag av brittiska Science Research Council en kritisk granskning av AI-forskningen. Han konstaterade att AI inte hade levererat på sina löften och att grundläggande problem — kombinatorisk explosion — gjorde att AI inte skulle kunna skala upp till verkliga problem. Som ett direkt resultat drog brittiska myndigheter in nästan all AI-finansiering.

### Varför misslyckades den tidiga AI:n?

| Problem                       | Förklaring                                                                                                                               |
| ----------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| **Kombinatorisk explosion**   | Antalet möjliga lösningar på ett problem växer exponentiellt med problemets storlek. Datorer på 1970-talet var alldeles för långsamma.   |
| **Brittleness (bräcklighet)** | Tidiga AI-system fungerade bara inom sina exakta träningsdomäner. Minsta avvikelse från det förväntade orsakade totalt haveri.           |
| **Commonsense reasoning**     | Att programmera en dator med vardagskunskap visade sig extremt svårt. Vad en 5-åring vet intuitivt kräver enorma kunskapsbaser formellt. |
| **Hårdvarubegränsningar**     | Dåtidens datorer hade för lite minne och var för långsamma för de algoritmer man velat använda.                                          |

## 6. Expertsystemens era och ny optimism (1980–1987)

I stället för att försöka skapa generell intelligens fokuserade forskare nu på **expertsystem** — program som kodifierade experters kunskap inom ett smalt domänspecifikt område. Tillvägagångssättet fungerade, och AI fick ett nytt uppsving.

### MYCIN (1972–1980)

MYCIN, utvecklat vid Stanford, var ett expertsystem som diagnostiserade blodsjukdomar och föreslog antibiotikumbehandling. I studier presterade MYCIN bättre än genomsnittliga läkare inom sitt specialiserade område. Det bestod av ca 600 IF-THEN-regler och använde osäkerhetsfaktorer för att hantera otillräcklig information. MYCIN användes aldrig kliniskt (av legala skäl) men inspirerade decennier av medicinsk AI.

### R1/XCON och kommersiell framgång (1980)

Digital Equipment Corporation (DEC) implementerade expertsystemet **R1** (senare XCON) för att konfigurera miniräknarbeställningar. 1986 sparade XCON DEC uppskattningsvis 40 miljoner dollar per år — ett av de första tydliga exemplen på att AI kunde skapa kommersiellt värde.

### Japans femte generationens datorprojekt (1982)

Den japanska regeringen investerade 400 miljoner dollar i ett 10-årigt projekt för att skapa nästa generations AI-datorer baserade på logikprogrammering (Prolog). USA och Europa svarade med egna stora AI-satsningar.

{% hint style="warning" %}
**Expertsystemens begränsning:** Kunskap måste kodas manuellt av experter — en enormt tidskrävande process. Systemen var "brittla": de klarade inte situationer utanför sin exakta kunskapsbas. Och uppdatering av reglerna när ny kunskap uppkom var extremt arbetsintensivt.
{% endhint %}

## 7. Andra AI-vintern (1987–1993)

I slutet av 1980-talet kollapsade marknaden för LISP-maskiner — specialiserad hårdvara för AI-program. Vanliga persondatorer (PC) hade blivit kraftfullare och billigare. Expertsystem visade sig vara dyra att underhålla och känsliga för förändringar. Finansiering drogs åter in, och branschen gick in i den **andra AI-vintern**.

Den strategiska AI-satsningen i Japan levererade inte, och USA:s DARPA ändrade inriktning från AI mot mer tillämpad forskning. Begreppet "AI" hade blivit så belastat med misslyckade löften att många forskare aktivt undvek det och kallade sin forskning något annat.

### Vad lärde man sig?

AI-vintrarna tvingade fram en mer pragmatisk och ödmjuk inställning. Forskarsamhället insåg att:

* Generell intelligens kräver mer än regler och logik.
* Lärande från data — inte manuell kunskapsrepresentation — är nyckeln.
* Sambandet mellan hårdvarukapacitet och AI-möjligheter är avgörande.
* Verkliga tillämpningar kräver robusthet, inte bara imponerande demonstrationer.

## 8. Maskininlärningens framväxt (1993–2010)

I stället för att programmera regler började forskare låta datorer _lära sig_ från stora datamängder med hjälp av statistiska metoder. Paradigmskiftet mot **maskininlärning** (Machine Learning, ML) förändrade AI-fältet fundamentalt.

### Tidslinje

#### 1989 — Backpropagation populariseras

Yann LeCun, Geoffrey Hinton m.fl. populariserar backpropagation — algoritmen som gör det möjligt att träna flerlagers neurala nätverk. LeCun tillämpar den på handskriftsigenkänning med konvolutionella nätverk (CNN).

#### 1997 — Deep Blue slår Kasparov

IBMs datorprogram **Deep Blue** besegrar världsmästaren Garry Kasparov i schack — ett historiskt medialt genombrott. Deep Blue använde dock inte maskininlärning utan brute-force sökning med handtunade heuristiker.

#### 1997 — LSTM uppfinns

Sepp Hochreiter och Jürgen Schmidhuber publicerar **Long Short-Term Memory (LSTM)** — ett neuralt nätverk som kan hantera sekvenser och minnas information över tid. Grundläggande för senare språkmodeller och taligenkänning.

#### 2002 — Support Vector Machines dominerar

SVM-algoritmer (Vapnik m.fl.) dominerar maskininlärningsfältet med starka teoretiska garantier och goda praktiska resultat på bildklassificering och textanalys.

#### 2006 — Deep learning pånyttfödelse

**Geoffrey Hinton** och Ruslan Salakhutdinov publicerar metoder för att träna djupa neurala nätverk effektivt med s.k. pre-training. Detta markerar starten på deep learning-eran.

### Watson vinner Jeopardy! (2011)

IBMs **Watson**-system, tränat på miljontals dokument, besegrar 2011 de bästa mänskliga Jeopardy!-spelarna. Watson kombinerade maskininlärning, NLP och informationshämtning — och visade att AI kunde hantera naturligt, tvetydigt språk i realtid.

## 9. Deep learning-revolutionen (2010–2020)

Tre faktorer sammanföll i början av 2010-talet och skapade ett historiskt paradigmskifte:

1. **Enorma mängder digitala data** från internet
2. **GPU-baserad beräkning** — grafikprocessorer idealiska för parallell träning
3. **Genombrott i algoritmer** för djupa neurala nätverk

### Tidslinje

#### 2012 — AlexNet och ImageNet

Geoffrey Hintons student **Alex Krizhevsky** vinner ImageNet-tävlingen med AlexNet — ett djupt konvolutionellt neuralt nätverk. Felfrekvensen sjunker dramatiskt (från 26 % till 15 %). Detta är startskottet för den moderna deep learning-eran.

#### 2014 — GANs uppfinns

**Ian Goodfellow** uppfinner Generative Adversarial Networks (GANs) — ett system av två konkurrerande nätverk som kan generera fotorealistiska bilder från grunden. Grundläggande för all modern bildgenerering.

#### 2016 — AlphaGo besegrar Lee Sedol

DeepMinds **AlphaGo** besegrar världsmästaren Lee Sedol i det oändligt komplexa brädspelet Go (fler möjliga positioner än atomer i universum). AlphaGo använde reinforcement learning kombinerat med djupa neurala nätverk — och bedömdes av experter vara 10 år för tidigt.

#### 2017 — Transformer-arkitekturen

Google Brain publicerar _"Attention Is All You Need"_ och introducerar **Transformer-arkitekturen**. Detta revolutionerar NLP och är grunden för alla moderna språkmodeller: BERT, GPT, LLaMA m.fl.

#### 2018 — BERT och GPT-1

Google lanserar **BERT** och OpenAI lanserar **GPT-1** — stora, förtränade språkmodeller som slår rekord på mängder av NLP-uppgifter. Eran av förtränade modeller börjar.

#### 2019 — GPT-2 – "för farlig att publicera"

OpenAI tränar GPT-2 (1,5 miljarder parametrar) och väljer initialt att _inte_ publicera hela modellen, med hänvisning till risker för desinformation. Beslutet väcker stor debatt om AI-säkerhet och öppen forskning.

## 10. Generativ AI och vår tid (2020-talet)

2020-talet inledde en era av snabb, synlig AI-adoption. Stora språkmodeller (Large Language Models, LLM) och bildgenererande modeller nådde en bred allmänhet och förändrade hur vi arbetar, skapar och kommunicerar.

### Tidslinje

#### 2020 — GPT-3

OpenAI lanserar **GPT-3** med 175 miljarder parametrar — en modell som kan skriva övertygande text, kod, översätta och resonera på ett sätt som väcker enorm uppmärksamhet och debatt.

#### 2021 — DALL-E och CLIP

OpenAI lanserar **DALL-E** — en modell som genererar bilder från textbeskrivningar. CLIP kopplar samman text och bildförståelse. Början på text-till-bild-revolutionen.

#### 2022 — Stable Diffusion och Midjourney

Öppen bildgenerering med **Stable Diffusion** demokratiserar AI-bildgenerering. Midjourney lanseras och används av miljoner. Konstnärer och rättsinnehavare börjar debattera upphovsrätt intensivt.

#### November 2022 — ChatGPT

OpenAI lanserar **ChatGPT**. Det når 100 miljoner användare på två månader — snabbare än någon applikation i historien. Hela samhället tvingas förhålla sig till AI: skola, juridik, media, arbetsmarknad.

#### 2023 — GPT-4 och multimodala modeller

**GPT-4** kan hantera både text och bilder. Gemini (Google), Claude (Anthropic) och Llama (Meta) lanseras. AI-kapplöpningen accelererar globalt.

#### 2024–2025 — Agentisk AI och reasoning-modeller

AI-agenter som kan utföra flerstegiga uppgifter autonomt börjar ta form. o1, o3, Claude 3.5 Sonnet och liknande modeller visar förbättrat logiskt resonemang. Debatten om AI-säkerhet, reglering (EU AI Act) och långsiktig risk intensifieras.

## 11. Nyckelbegrepp

| Begrepp                    | Förklaring                                                                                                       |
| -------------------------- | ---------------------------------------------------------------------------------------------------------------- |
| **Algoritm**               | En steg-för-steg-instruktion för att lösa ett problem. Datorer följer algoritmer.                                |
| **Neuralt nätverk**        | Ett beräkningssystem inspirerat av hjärnans neuroner, uppbyggt av sammankopplade noder i lager.                  |
| **Deep learning**          | Maskininlärning med djupa (flerlagers) neurala nätverk som lär sig hierarkiska representationer.                 |
| **Maskininlärning (ML)**   | Metoder som låter datorer lära sig från data utan att explicit programmeras för varje uppgift.                   |
| **Träningsdata**           | Den datamängd som används för att träna en AI-modell.                                                            |
| **Backpropagation**        | Algoritm för att träna neurala nätverk genom att propagera fel bakåt genom nätverket.                            |
| **Transformer**            | Arkitektur (2017) som används i moderna språkmodeller. Bygger på "attention"-mekanismen.                         |
| **LLM**                    | Large Language Model — stor språkmodell tränad på massiv textdata för att förutse och generera text.             |
| **GPU**                    | Graphics Processing Unit — processor ursprungligen för grafik, men idealisk för parallell beräkning i AI.        |
| **Overfitting**            | När en modell lär sig träningsdata för bra och misslyckas att generalisera till ny data.                         |
| **Reinforcement learning** | Inlärningsparadigm där en agent lär sig via belöningar och straff i en miljö.                                    |
| **GAN**                    | Generative Adversarial Network — två nätverk tävlar: ett skapar, ett bedömer. Resulterar i realistiskt innehåll. |
| **Turing-testet**          | Test av maskiners intelligens: om en människa inte kan avgöra om den pratar med maskin eller människa.           |
| **AI-vinter**              | Period av minskad AI-finansiering och forskarintresse efter misslyckade löften.                                  |
| **Expertsystem**           | AI-system baserat på manuellt kodade IF-THEN-regler från domänexperter.                                          |

## 12. Viktiga personer

### Alan Turing (1912–1954)

_Matematiker & datavetare_

Skapade Turing-maskinen (beräkningsteorins grund), knäckte Enigma-koden och formulerade Turing-testet. Anses som datavetenskapens och AI:s fader.

### John McCarthy (1927–2011)

_Datavetare, myntade termen AI_

Myntade termen "Artificial Intelligence" 1956, organiserade Dartmouth-konferensen och skapade programspråket LISP som dominerade AI-forskning i decennier.

### Marvin Minsky (1927–2016)

_Kognitiv vetare & AI-pionjär_

Medgrundare av MIT AI Lab, banbrytande arbete inom neurala nätverk och kognitiv modellering. Omdebatterad för sin tidiga kritik av perceptroner (_Perceptrons_, 1969).

### Geoffrey Hinton (1947–)

_Datavetare, "Deep learnings gudfather"_

Nobelpristagare i fysik 2024. Populariserade backpropagation och grundlade modern deep learning. Lämnade Google 2023 för att kunna tala fritt om AI-risker.

### Yann LeCun (1960–)

_Datavetare, Meta Chief AI Scientist_

Pionjär inom konvolutionella neurala nätverk (CNN). Tillämpade backpropagation på handskriftsigenkänning. Nobelpristagare i fysik 2024 (delade med Hinton och Bengio).

### Yoshua Bengio (1964–)

_Datavetare, Université de Montréal_

Nobelpristagare i fysik 2024. Bidrog fundamentalt till deep learning och sekvenslärning. Aktiv röst i AI-säkerhets- och etikdebatt.

### Ian Goodfellow (1985–)

_Datavetare & ML-forskare_

Uppfinnare av Generative Adversarial Networks (GANs, 2014) — tekniken bakom realistisk AI-bildgenerering.

### Sam Altman (1985–)

_VD OpenAI_

Lett OpenAI till att bli världens mest inflytelserika AI-företag med GPT-serien och ChatGPT. Central gestalt i debatten om AI-reglering och AGI-risker.

## 13. Diskussionsfrågor och övningar

### Diskussionsfrågor

{% stepper %}
{% step %}
#### Turing-testet

Vad mäter det egentligen? Är det ett bra mått på intelligens? Vad saknas?
{% endstep %}

{% step %}
#### AI-vintrar inträffade efter perioder av överdrivet hype.

Ser du liknande mönster i hur AI diskuteras idag? Är vi i en ny hype-period?
{% endstep %}

{% step %}
#### ELIZA-effekten

Tendensen att anthropomorfisera AI — är fortfarande aktuell. Var har du upplevt den? Vad kan det leda till?
{% endstep %}

{% step %}
#### Geoffrey Hinton lämnade Google

Han lämnade Google för att kunna tala fritt om AI-risker. Vilka risker tror du han syftade på?
{% endstep %}

{% step %}
#### Expertsystem misslyckades

Expertsystem misslyckades delvis för att kunskap måste kodas manuellt. Hur skiljer sig moderna LLMs från det tillvägagångssättet?
{% endstep %}
{% endstepper %}

### Övningar

{% stepper %}
{% step %}
#### Tidslinje

Skapa en visuell tidslinje över AI:s historia med minst 15 händelser. Markera AI-vintrar, genombrott och viktiga personers bidrag.
{% endstep %}

{% step %}
#### Jämförelse

Jämför ELIZA (1966) med en modern chatbot (t.ex. ChatGPT). Vad är likt? Vad är fundamentalt annorlunda? Formulera 5 konkreta skillnader.
{% endstep %}

{% step %}
#### Etikdiskussion

Turing föreslog att frågan "kan maskiner tänka?" ersätts med ett operationellt test. Skriv en argumenterande text (400–600 ord) om varför detta är eller inte är ett tillfredsställande sätt att definiera maskiners intelligens.
{% endstep %}

{% step %}
#### Källgranskning

Hitta tre nyhetsartiklar om AI från 2022–2026. Analysera: Vad lovas? Vad levereras? Finns tecken på hype? Jämför med AI-vintrarnas mönster.
{% endstep %}
{% endstepper %}

## 14. Källförteckning

### Vetenskapliga originalartiklar

* McCulloch, W.S. & Pitts, W. (1943). A Logical Calculus of the Ideas Immanent in Nervous Activity. _Bulletin of Mathematical Biophysics_, 5, 115–133.
* Turing, A.M. (1950). Computing Machinery and Intelligence. _Mind_, 59(236), 433–460.
* McCarthy, J., Minsky, M., Rochester, N. & Shannon, C. (1955). _A Proposal for the Dartmouth Summer Research Project on Artificial Intelligence_.
* Rosenblatt, F. (1958). The Perceptron: A Probabilistic Model for Information Storage and Organization in the Brain. _Psychological Review_, 65(6), 386–408.
* Minsky, M. & Papert, S. (1969). _Perceptrons: An Introduction to Computational Geometry_. MIT Press.
* Lighthill, J. (1973). _Artificial Intelligence: A General Survey_. Science Research Council.
* Rumelhart, D.E., Hinton, G.E. & Williams, R.J. (1986). Learning Representations by Back-propagating Errors. _Nature_, 323, 533–536.
* Hochreiter, S. & Schmidhuber, J. (1997). Long Short-Term Memory. _Neural Computation_, 9(8), 1735–1780.
* Vaswani, A. et al. (2017). Attention Is All You Need. _Advances in Neural Information Processing Systems_, 30.
* Goodfellow, I. et al. (2014). Generative Adversarial Nets. _Advances in Neural Information Processing Systems_, 27.

### Böcker

* Russell, S. & Norvig, P. (2020). _Artificial Intelligence: A Modern Approach_ (4th ed.). Pearson. _(Standardverket inom AI)_
* Tegmark, M. (2017). _Life 3.0: Being Human in the Age of Artificial Intelligence_. Knopf. _(Tillgänglig på svenska)_
* Bostrom, N. (2014). _Superintelligence: Paths, Dangers, Strategies_. Oxford University Press.
* Nilsson, N.J. (2010). _The Quest for Artificial Intelligence: A History of Ideas and Achievements_. Cambridge University Press. _(Gratis online)_
* Sejnowski, T.J. (2018). _The Deep Learning Revolution_. MIT Press.
* Marcus, G. & Davis, E. (2019). _Rebooting AI: Building Artificial Intelligence We Can Trust_. Pantheon.

### Digitala resurser

* **Stanford Encyclopedia of Philosophy** — plato.stanford.edu _(artiklar om AI, Turing-testet, medvetande)_
* **3Blue1Brown** (YouTube) — "Neural Networks" _(visuell förklaring av neurala nätverk)_
* Turing, A.M. (1950). Computing Machinery and Intelligence _(fritt tillgänglig på nätet)_
* Nilsson, N.J. _The Quest for Artificial Intelligence_ — ai.stanford.edu/\~nilsson/QAI/qai.pdf

_Materialet är framtaget för kursen AI 1 på gymnasienivå. Texten är avsedd som ett lärverktyg och bör kompletteras med primärkällor och aktuell forskning._
