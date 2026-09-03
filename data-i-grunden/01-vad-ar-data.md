# 01 vad ar data

Data är information i en form som kan lagras, skickas och behandlas. En bokstav, en temperaturmätning, ett fotografi, ett mellanslag — allt detta är data. Det som förenar dem är att de alla kan kodas som siffror.

Datorer arbetar med **symboler**: de känner inte till "röd" eller "A" eller "varm" — de känner bara till värden och regler för hur värden transformeras. Vår uppgift är att hitta sätt att _representera_ världens information som siffror datorn kan räkna med.

{% hint style="info" %}
**Huvudidén:** All information — text, bild, ljud, video, mätdata — kan kodas som tal. Och alla tal kan representeras i det binära talsystemet.
{% endhint %}

## Tre typer av data

Det är användbart att skilja på tre grundläggande kategorier:

**Strukturerad data** är information som passar i en tabell med rader och kolumner — till exempel en databas med kunduppgifter eller en CSV-fil med mätresultat. Varje kolumn har en bestämd typ (text, heltal, datum).

**Ostrukturerad data** är information som inte naturligt passar i en tabell — bilder, ljud, fritext, videofiler. Den kan fortfarande lagras digitalt, men kräver mer arbete för att utvinnas ur.

**Semi-strukturerad data** är något mittemellan: JSON, XML och HTML har en viss struktur (nyckel–värde-par, taggar) men är inte lika strikta som en relationsdatabas.

## Varför spelar representationen roll?

Hur data representeras avgör vad man kan göra med den. En bild lagrad som en lista av pixelintensiteter kan analyseras av ett neuralt nätverk. Samma bild lagrad som en JPEG-fil måste först avkomprimeras. Texten "42" och talet `42` ser likadana ut för oss, men datorn behandlar dem helt olika — det ena är en sekvens av tecken, det andra ett tal man kan räkna med.

I maskininlärning handlar **feature engineering** om att välja rätt representation: vilka egenskaper hos data ska extraheras, och i vilken form, för att en modell ska kunna lära sig från dem?
