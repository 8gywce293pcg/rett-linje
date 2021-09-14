### @explicitHints false

## Introduksjon @unplugged
Her vil du lære å kode våre kule LED displayer. Målet er å sette på en og en LED!

```blocks
let strip = neopixel.create(DigitalPin.P0, 768, NeoPixelMode.RGB)
strip.setBrightness(50)
let HØYDE = 10
let LED_NUMMER = HØYDE
let TELLER = 0
basic.forever(function () {
    strip.setPixelColor(LED_NUMMER, neopixel.colors(NeoPixelColors.Red))
    strip.show()
    basic.pause(100)
    LED_NUMMER += 31 - HØYDE * 2
    TELLER += 1
    strip.setPixelColor(LED_NUMMER, neopixel.colors(NeoPixelColors.Red))
    strip.show()
    basic.pause(100)
    LED_NUMMER += 1 + HØYDE * 2
    TELLER += 1
    if (TELLER > 48) {
        strip.clear()
        strip.show()
        TELLER = 0
        HØYDE = randint(0, 15)
        LED_NUMMER = HØYDE
    }
})
```

## Steg 1: Definer noen neopixler @fullscreen


 Trykk på ``||Neopixel: Neopixel||`` fra blokkmenyen.
 Klikk og dra inn blokken ``||Neopixel: sett strip til ||`` og slipp den inn i ``||basic: ved start ||`` blokken.
 Velg pinne ``||Neopixel: P0||`` og antall LED til ``||Neopixel: 768||`` la format stå som ``||Neopixel: RGB (GRB) ||``.
 Denne blokken brukes for å velge hvilken pinne som er koblet til LED, hvor mange LEDèr det er og hvilken type LED. 

```blocks

let strip = neopixel.create(DigitalPin.P0, 768, NeoPixelMode.RGB)

```

## Steg 2: Sette lysstyrke så ikke vi trekker for mye strøm
Trykk på ``||Neopixel: Neopixel ||`` fra blokkmenyen.
Klikk og dra inn blokken ``||Neopixel: strip.setBrightness(0) ||`` plasser den under  ``||Neopixel: sett strip til ||``.
Sett verdien til max 50.  Er denne verdien for høyt kan det hende at det ikke vil virke. 
Denne blokken Gjør at vi kan justere lysstyrken.

```blocks

let strip = neopixel.create(DigitalPin.P0, 768, NeoPixelMode.RGB)
strip.setBrightness(50)

```

## Steg 3: Slette minne i LED
Trykk på ``||Neopixel: Neopixel ||`` fra blokkmenyen.
Klikk og dra inn blokken ``||Neopixel: strip.clear ||`` plasser den under forrige blokk.
Denne blokken sletter tidligere data inni lysdidodene.

```blocks

let strip = neopixel.create(DigitalPin.P0, 768, NeoPixelMode.RGB)
strip.setBrightness(50)
strip.clear()

```
## Steg 4: Lage en variabel for å få en tilfeldig LED til å lyse
Trykk på ``||Variabler: variabel ||`` fra blokkmenyen og klikk deretter ``||Variabler: lag en variabel ||`` og gi variabelen navnet ``||Variabler: HØYDE ||``.
Trykk på ``||Variabler: variabel ||``, klikk og dra blokken ``||Variabler: Sett HØYDE ||`` og sett verdi til 0.
Dette for å sette Y aksen. altså 0 til 16.

```blocks
let strip = neopixel.create(DigitalPin.P0, 768, NeoPixelMode.RGB)
strip.setBrightness(50)
strip.clear()
let HØYDE = 5

```
## Steg 5: Sette opp løkker
Trykk på ``||Variabler: variabel ||`` fra blokkmenyen og klikk deretter ``||Variabler: lag en variabel ||`` og gi variabelen navnet ``||Variabler: LED_NUMMER ||``.
Trykk på ``||Variabler: variabel ||``, klikk og dra blokken ``||Variabler: Sett LED_NUMMER ||`` og sett verdi til ``||Variabler: HØYDE ||``.
Dette for å sette hvilken LED_NUMMER som skal begynne å lyse.

```blocks
let strip = neopixel.create(DigitalPin.P0, 768, NeoPixelMode.RGB)
strip.setBrightness(50)
strip.clear()
let HØYDE = 9
let LED_NUMMER = HØYDE
```
## Steg 6: Lage en variabel for X retning. Antall LED Y=16  X=48 = Y * X= 768
Trykk på ``||Variabler: variabel ||`` fra blokkmenyen og klikk deretter ``||Variabler: lag en variabel ||`` og gi variabelen navnet ``||Variabler: TELLER ||``.
Trykk på ``||Variabler: variabel ||``, klikk og dra blokken ``||Variabler: Sett TELLER ||`` og sett verdi til 0.
Dette for å sette hvilken LED_NUMMER som skal begynne å lyse.

```blocks
let strip = neopixel.create(DigitalPin.P0, 768, NeoPixelMode.RGB)
strip.setBrightness(50)
strip.clear()
let HØYDE = 50
let LED_NUMMER = HØYDE
let TELLLER = 0
let TELLER2 = 100
```
## Steg 7: Sette opp neste LED som skal lyse.
Trykk på ``||Neopixel: Neopixel ||`` fra blokkmenyen.
Klikk og dra inn blokken ``||Neopixel: strip.set pixel color at (0) to Red ||`` plasser den inni ``||Basic: gjenta for alltid ||``.
Trykk på ``||Variabler: variabel ||``, klikk og dra blokken ``||Variabler: Sett LED_NUMMER ||`` og sett den inni ``||Neopixel: strip.set pixel color at (0) to Red ||`` ved (0).
Dette for å sette hvilken LED_NUMMER som skal begynne å lyse.

```blocks
let strip = neopixel.create(DigitalPin.P0, 768, NeoPixelMode.RGB)
strip.setBrightness(50)
strip.clear()
let HØYDE = 10
let LED_NUMMER = HØYDE
let TELLER = 0

basic.forever(function () {
    strip.setPixelColor(LED_NUMMER, neopixel.colors(NeoPixelColors.Red))
})
```

## Steg 8: Sende data til LED
Trykk på ``||Neopixel: Neopixel ||`` fra blokkmenyen.
Klikk og dra inn blokken ``||Neopixel: strip show ||`` plasser den under  ``||Neopixel: strip set pixel color at (LED_NUMMER) to red ||``.

```blocks
let strip = neopixel.create(DigitalPin.P0, 768, NeoPixelMode.RGB)
strip.setBrightness(50)
strip.clear()
let HØYDE = 10
let LED_NUMMER = HØYDE
let TELLER = 0

basic.forever(function () {
    strip.setPixelColor(LED_NUMMER, neopixel.colors(NeoPixelColors.Red))
    strip.show()
})
```

## Steg 9: Sette inn en ``||Basic: pause(100) ||`` for å sette hastighet.
Trykk ``||Basic. Basis ||`` og klikk på ``||Basic. pause(100) ||`` og dra den inn under ``||Neopixel: strip show ||`` blokken.
Sett verdien til 100ms.

```blocks
let strip = neopixel.create(DigitalPin.P0, 768, NeoPixelMode.RGB)
strip.setBrightness(50)
strip.clear()
let HØYDE = 10
let LED_NUMMER = HØYDE
let TELLER = 0

basic.forever(function () {
    strip.setPixelColor(LED_NUMMER, neopixel.colors(NeoPixelColors.Red))
    strip.show()
    basic.pause(100)
})
```
## Steg 10 Regne ut og sette neste verdi for variabelen LED_NUMMER. 
Trykk på ``||Variabler: variabel ||`` fra blokkmenyen og klikk deretter ``||Variabler: endre [LED_NUMMER] med (1) ||`` og sett inn under ``||Basic. pause (100)||``.
Trykk på ``||Math: Mattematikk ||``, klikk og dra blokken ``||Math: (0 + 0) ||`` 2 ganger og sett disse inni hverandre.
Hent deretter variabelen ``||Variabler: HØYDE ||`` og sett inn i det miderste verdien. Verdiene = 31 - HØYDE * 2.

```blocks
let strip = neopixel.create(DigitalPin.P0, 768, NeoPixelMode.RGB)
strip.setBrightness(50)
strip.clear()
let HØYDE = 10
let LED_NUMMER = HØYDE
let TELLER = 0

basic.forever(function () {
    strip.setPixelColor(LED_NUMMER, neopixel.colors(NeoPixelColors.Red))
    strip.show()
    basic.pause(100)
    LED_NUMMER += 31 - HØYDE * 2
})
```

## Steg 11 Endre verdi i variabelen TELLER med +1 i X rettningen 
Trykk på ``||Variabler: variabel ||`` fra blokkmenyen og klikk deretter ``||Variabler: endre [TELLER] med (1) ||`` og sett inn under ``||Variabler: endre [LED_NUMMER] med (1) ||``.
Denne brukes for å telle X rettning til 48.

```blocks
let strip = neopixel.create(DigitalPin.P0, 768, NeoPixelMode.RGB)
strip.setBrightness(50)
strip.clear()
let HØYDE = 10
let LED_NUMMER = HØYDE
let TELLER = 0

basic.forever(function () {
    strip.setPixelColor(LED_NUMMER, neopixel.colors(NeoPixelColors.Red))
    strip.show()
    basic.pause(100)
    LED_NUMMER += 31 - HØYDE * 2
    TELLER += 1
})
```

## Steg 12 Sette opp neste LED som skal lyse
Trykk på ``||Neopixel: Neopixel ||`` fra blokkmenyen og klikk deretter ``||Neopixel: mer ||``. Dra inn ``||Neopixel: strip set pixel color at (0) to red ||``.
Sett denne blocken under ``||Variabler: endre [TELLER] med (1) ||``.

```blocks
let strip = neopixel.create(DigitalPin.P0, 768, NeoPixelMode.RGB)
strip.setBrightness(50)
strip.clear()
let HØYDE = 10
let LED_NUMMER = HØYDE
let TELLER = 0

basic.forever(function () {
    strip.setPixelColor(LED_NUMMER, neopixel.colors(NeoPixelColors.Red))
    strip.show()
    basic.pause(100)
    LED_NUMMER += 31 - HØYDE * 2
    TELLER += 1
    strip.setPixelColor(LED_NUMMER, neopixel.colors(NeoPixelColors.Red))
})
```
## Steg 13 Sende data til LED mad ``||Neopixel: strip.show ||`` blokken
Trykk på ``||Neopixel: Neopixel ||`` fra blokkmenyen.
Klikk og dra inn blokken ``||Neopixel: strip show ||`` plasser den under  ``||Neopixel: strip set pixel color at (LED_NUMMER) to red ||``.

```blocks
let strip = neopixel.create(DigitalPin.P0, 768, NeoPixelMode.RGB)
strip.setBrightness(50)
strip.clear()
let HØYDE = 10
let LED_NUMMER = HØYDE
let TELLER = 0

basic.forever(function () {
    strip.setPixelColor(LED_NUMMER, neopixel.colors(NeoPixelColors.Red))
    strip.show()
    basic.pause(100)
    LED_NUMMER += 31 - HØYDE * 2
    TELLER += 1
    strip.setPixelColor(LED_NUMMER, neopixel.colors(NeoPixelColors.Red))
    strip.show()
})
```
## Steg 14 Bruke pauseblokken for å sette hastighet
Trykk ``||Basic. Basis ||`` og klikk på ``||Basic. pause(100) ||`` og dra den inn under ``||Neopixel: strip show ||`` blokken.
Sett verdien til 100ms.

```blocks
let strip = neopixel.create(DigitalPin.P0, 768, NeoPixelMode.RGB)
strip.setBrightness(50)
strip.clear()
let HØYDE = 10
let LED_NUMMER = HØYDE
let TELLER = 0

basic.forever(function () {
    strip.setPixelColor(LED_NUMMER, neopixel.colors(NeoPixelColors.Red))
    strip.show()
    basic.pause(100)
    LED_NUMMER += 31 - HØYDE * 2
    TELLER += 1
    strip.setPixelColor(LED_NUMMER, neopixel.colors(NeoPixelColors.Red))
    strip.show()
    basic.pause(100)
})
```

## Steg 15 Få LED til å lyse ved siden av forrige LED i X rettning
Trykk på ``||Variabler: variabel ||`` fra blokkmenyen og klikk deretter ``||Variabler: endre [LED_NUMMER] med (1) ||`` og sett inn under ``||Basic. pause (100)||``.
Trykk på ``||Math: Mattematikk ||``, klikk og dra blokken ``||Math: (0 + 0) ||`` 2 ganger og sett disse inni hverandre.
Hent deretter variabelen ``||Variabler: HØYDE ||`` og sett inn i det miderste verdien. Verdiene = 1 + HØYDE * 2.

```blocks
let strip = neopixel.create(DigitalPin.P0, 768, NeoPixelMode.RGB)
strip.setBrightness(50)
strip.clear()
let HØYDE = 10
let LED_NUMMER = HØYDE
let TELLER = 0

basic.forever(function () {
    strip.setPixelColor(LED_NUMMER, neopixel.colors(NeoPixelColors.Red))
    strip.show()
    basic.pause(100)
    LED_NUMMER += 31 - HØYDE * 2
    TELLER += 1
    strip.setPixelColor(LED_NUMMER, neopixel.colors(NeoPixelColors.Red))
    strip.show()
    basic.pause(100)
    LED_NUMMER += 1 + HØYDE * 2
})
```

## Steg 16 Plusse på TELLER i X rettning +1
Trykk på ``||Variabler: variabel ||`` fra blokkmenyen og klikk deretter ``||Variabler: endre [TELLER] med (1) ||`` og sett inn under ``||Variabler: endre [LED_NUMMER] med (1) ||``.
Denne brukes for å fotsette telle X rettning til 48.

```blocks
let strip = neopixel.create(DigitalPin.P0, 768, NeoPixelMode.RGB)
strip.setBrightness(50)
strip.clear()
let HØYDE = 10
let LED_NUMMER = HØYDE
let TELLER = 0

basic.forever(function () {
    strip.setPixelColor(LED_NUMMER, neopixel.colors(NeoPixelColors.Red))
    strip.show()
    basic.pause(100)
    LED_NUMMER += 31 - HØYDE * 2
    TELLER += 1
    strip.setPixelColor(LED_NUMMER, neopixel.colors(NeoPixelColors.Red))
    strip.show()
    basic.pause(100)
    LED_NUMMER += 1 + HØYDE * 2
    TELLER += 1
})
```

## Steg 17 Nullstilling av alle variabler ved hjelp av logikk blokken
Trykk på ``||Logic: Logikk||`` fra blokkmenyen og klikk og dra inn ``||Logic:hvis||`` og sett denne inn i under ``||Variabler: endre [TELLER] med (1) ||``.
Trykk på ``||Logic: Logikk||`` fra blokk menyen og klikk og dra inn ``||Logic: < 0 = 0 > ||`` og sett denne inn i ``||Logic:hvis||``.
Trykk på ``||Variabler: Variabel||`` fra blokkmenyen og klikk og dra blokken ``||Variabler:  TELLER ||``  i første 0 inni  ``||Logic: < 0 = 0 > ||`` blokken.
og sett denne til ``||Logic: < TELLER = 47 > ||``.
Denne brukes for å nullstille X rettning når nådd 47.

```blocks
let strip = neopixel.create(DigitalPin.P0, 768, NeoPixelMode.RGB)
strip.setBrightness(50)
strip.clear()
let HØYDE = 10
let LED_NUMMER = HØYDE
let TELLER = 0

basic.forever(function () {
    strip.setPixelColor(LED_NUMMER, neopixel.colors(NeoPixelColors.Red))
    strip.show()
    basic.pause(100)
    LED_NUMMER += 31 - HØYDE * 2
    TELLER += 1
    strip.setPixelColor(LED_NUMMER, neopixel.colors(NeoPixelColors.Red))
    strip.show()
    basic.pause(100)
    LED_NUMMER += 1 + HØYDE * 2
    TELLER += 1
    if (TELLER == 47) {
        
    }
})
```
 
## Steg 18 Nullstilling av alle variabler TELLER i X rettning
Trykk på ``||Neopixel: Neopixel ||`` fra blokkmenyen. Klikk og dra inn blokken ``||Neopixel: strip.clear ||`` plasser den under forrige blokk.
Denne blokken sletter tidligere data inni lysdidodene.

```blocks
let strip = neopixel.create(DigitalPin.P0, 768, NeoPixelMode.RGB)
strip.setBrightness(50)
strip.clear()
let HØYDE = 10
let LED_NUMMER = HØYDE
let TELLER = 0

basic.forever(function () {
    strip.setPixelColor(LED_NUMMER, neopixel.colors(NeoPixelColors.Red))
    strip.show()
    basic.pause(100)
    LED_NUMMER += 31 - HØYDE * 2
    TELLER += 1
    strip.setPixelColor(LED_NUMMER, neopixel.colors(NeoPixelColors.Red))
    strip.show()
    basic.pause(100)
    LED_NUMMER += 1 + HØYDE * 2
    TELLER += 1
    if (TELLER == 47) {
        strip.clear()
    }
})
```

## Steg 19 nullstille variabelen TELLER for å kunne telle fra 0 - 47 på nytt.
Trykk på ``||Variabler: variabel ||`` fra blokkmenyen, klikk og dra blokken ``||Variabler: Sett TELLER ||`` og sett verdi til 0.
Dette for å nullstille teller i X rettningen, som er fra 0 - 47.

```blocks
let strip = neopixel.create(DigitalPin.P0, 768, NeoPixelMode.RGB)
strip.setBrightness(50)
strip.clear()
let HØYDE = 10
let LED_NUMMER = HØYDE
let TELLER = 0

basic.forever(function () {
    strip.setPixelColor(LED_NUMMER, neopixel.colors(NeoPixelColors.Red))
    strip.show()
    basic.pause(100)
    LED_NUMMER += 31 - HØYDE * 2
    TELLER += 1
    strip.setPixelColor(LED_NUMMER, neopixel.colors(NeoPixelColors.Red))
    strip.show()
    basic.pause(100)
    LED_NUMMER += 1 + HØYDE * 2
    TELLER += 1
    if (TELLER == 47) {
        strip.clear()
        TELLER = 0
    }
})
```
## Steg 20 Finne en tilfeldig høyde for neste rekke med LED. Y = 0 - 15
Trykk på ``||Variabler: variabel ||`` fra blokkmenyen. Klikk og dra blokken ``||Variabler: Sett HØYDE ||``.
Trykk på ``||Math: velg tilfeldig (0) til (10) ||``, og sett verdien til ``||Math: (0) til (15) ||``. Dette for å sette en tilfeldig rekke i Y aksen. altså 0 til 15.

```blocks
let strip = neopixel.create(DigitalPin.P0, 768, NeoPixelMode.RGB)
strip.setBrightness(50)
let HØYDE = 10
let LED_NUMMER = HØYDE
let TELLER = 0
basic.forever(function () {
    strip.setPixelColor(LED_NUMMER, neopixel.colors(NeoPixelColors.Red))
    strip.show()
    basic.pause(100)
    LED_NUMMER += 31 - HØYDE * 2
    TELLER += 1
    strip.setPixelColor(LED_NUMMER, neopixel.colors(NeoPixelColors.Red))
    strip.show()
    basic.pause(100)
    LED_NUMMER += 1 + HØYDE * 2
    TELLER += 1
    if (TELLER > 47) {
        strip.clear()
        strip.show()
        TELLER = 0
        HØYDE = randint(0, 15)
    }
})
```
## Steg 21 Sette den første LED til å lyse i den tilfeldige høden i Y rettning. Y = 0 - 15
Trykk på ``||Variabler: variabel ||`` fra blokkmenyen, klikk og dra blokken ``||Variabler: Sett LED_NUMMER ||``.
Trykk på ``||Variabler: variabel ||`` fra blokkmenyen, klikk og dra blokken ``||Variabler: Sett HØYDE ||`` og sett denne inni verdien (0) i ``||Variabler: Sett LED_NUMMER ||`` blokken.
Dette for å sette Y aksen til det tilfeldige tallet fra variabelen HØYDE. altså 0 til 15.

```blocks
let strip = neopixel.create(DigitalPin.P0, 768, NeoPixelMode.RGB)
strip.setBrightness(50)
let HØYDE = 10
let LED_NUMMER = HØYDE
let TELLER = 0
basic.forever(function () {
    strip.setPixelColor(LED_NUMMER, neopixel.colors(NeoPixelColors.Red))
    strip.show()
    basic.pause(100)
    LED_NUMMER += 31 - HØYDE * 2
    TELLER += 1
    strip.setPixelColor(LED_NUMMER, neopixel.colors(NeoPixelColors.Red))
    strip.show()
    basic.pause(100)
    LED_NUMMER += 1 + HØYDE * 2
    TELLER += 1
    if (TELLER > 47) {
        strip.clear()
        strip.show()
        TELLER = 0
        HØYDE = randint(0, 15)
        LED_NUMMER = HØYDE
    }
})
```

## Steg 22 Leste ned på microbiten

hvis du har en @boardname@ tilkoblet, trykk ``|last ned|``!
Prøv nå også endre farge og hvilken LED som skal lyse for så å trykke ``|last ned|`` igjen.
For hver endring vi gjør i koden må det lastes ned på nytt til @boardname@.

