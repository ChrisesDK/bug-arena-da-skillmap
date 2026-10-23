# Bug Arena: Frem og tilbage
### @hideReplaceMyCode true

## Introduktion til Bug Arena @showdialog

Velkommen til 👾 **Bug Arena** 👾, hvor de klogeste bugs kæmper om æren!

Se denne introduktionsvideo for at komme i gang, og klik derefter på Ok.

![Introduktion til Bug Arena](youtube:U_bcAht2o0A "introduktionsvideo om Bug Arena")

## Frem-og-tilbage-algoritme @showdialog

![Bug Arena: Frem og tilbage](/static/skillmap/bug-arena/back-and-forth.gif "animation af et frem-og-tilbage-mønster")

💡 Klogt valg af algoritme – millioner af plæneklippere kan ikke tage fejl! 🚜

Følg disse trin for at kode din bugs AI-algoritme ✨, så den bevæger sig frem og tilbage hen over skærmen.

## Indstil retning

Vores bug bevæger sig selv, men det er vigtigt, at den starter med at bevæge sig i den rigtige retning! 🗺️

Fra værktøjskategorien ``||hourOfAi:Bug AI||`` skal du trække blokken ``||hourOfAi:vend mod 0°||`` ud og slippe den i ``||hourOfAi:ved start||``-blokken.

~hint Hvad gør denne blok?

---

``||hourOfAi:vend mod||`` drejer din bug, så den peger mod en bestemt vinkel i grader, hvor:
- 0 = højre
- 90 = ned
- 180 = venstre
- 270 = op

![Peg mod grader](/static/skillmap/bug-arena/degrees.png "peg mod grader")

Så starter vores bug med at bevæge sig mod højre side af skærmen.

hint~

```blockconfig.local
hourOfAi.doAfter(1000, function () {

})
```

```blocks
hourOfAi.onStart(function () {
    //@highlight
    hourOfAi.turnTowards(0)
})
```

## 🧱 Når buggen rammer en væg

I spilvinduet 🖼️ nederst til højre skal du klikke på knappen **Practice**.

Vælg derefter **No Opponent** og **Infinite**.

Kan du se din bug bevæge sig mod højre?  Flot! 😊 Men hvad sker der, når din bug kommer til den anden side af skærmen?

Ingenting 🥺 Så lad os tilføje noget kode, der kører, når den rammer en væg.

Fra kategorien ``||hourOfAi:Bug AI||`` skal du trække en ``||hourOfAi:når buggen rammer en væg||``-blok ud på arbejdsområdet – du kan placere den hvor som helst.

```blockconfig.local
hourOfAi.doAfter(1000, function () {

})
```

```blocks
hourOfAi.onBumpWall(function () {

})
```

## Drej 90°

Fra kategorien ``||hourOfAi:Bug AI||`` skal du trække en ``||hourOfAi:drej 90°||``-blok og slippe den i ``||hourOfAi:når buggen rammer en væg||``-blokken.
<br/>
<br/>

~hint Hvad gør drej 90°?

---

Drejeblokken ↩️ drejer vores bug et bestemt antal grader fra dens nuværende retning. Et positivt tal ➕ drejer med uret, og et negativt tal ➖ drejer mod uret.

![Drejevinkel](/static/skillmap/bug-arena/turn-angle.png "drejevinkel")

hint~

```blockconfig.local
hourOfAi.doAfter(1000, function () {

})
```

```blocks
hourOfAi.onBumpWall(function () {
    //@highlight
    hourOfAi.turnBy(90)
})
```

## ⬇️ Bevæg dig ned

Vi vil have, at vores bug drejer 90 grader, så den peger nedad ⤵️, bevæger sig lidt ned ⬇️ og derefter drejer yderligere 90 grader, så den peger tilbage den vej, den kom fra. ↩️

For at gøre det skal vi bruge en blok, der venter et stykke tid ⏱️, før den drejer igen.

Fra kategorien ``||hourOfAi:Bug AI||`` skal du trække en ``||hourOfAi:kør efter 1000 ms||``-blok ud og slippe den efter ``||hourOfAi:drej 90°||``-blokken.

~hint Hvad gør denne blok?

---

Blokken ``||hourOfAi:kør efter||`` kører koden inde i den efter at have ventet den valgte tid ⏳.  I dette tilfælde venter vi 1 sekund eller 1000 millisekunder (ms), før vi drejer om igen.

hint~

```blockconfig.local
hourOfAi.doAfter(1000, function () {

})
```

```blocks
hourOfAi.onBumpWall(function () {
    hourOfAi.turnBy(90)
    //@highlight
    hourOfAi.doAfter(1000, function () {
 
    })
})
```

## ↩️ Drej nu om

Fra kategorien ``||hourOfAi:Bug AI||`` skal du trække endnu en ``||hourOfAi:drej 90°||``-blok ud og slippe den i ``||hourOfAi:kør efter||``-blokken.

```blockconfig.local
hourOfAi.doAfter(1000, function () {

})
```

```blocks
hourOfAi.onBumpWall(function () {
    hourOfAi.turnBy(90)
    hourOfAi.doAfter(1000, function () {
        //@highlight
        hourOfAi.turnBy(90)
    })
})
```

## 🚜 Lad os slå græs!

Lad os teste vores AI-algoritme og se, hvordan den klarer sig. 💫

Se i 🕹️ spilvinduet.  Hvad sker der? 

Vores bug bevæger sig godt nok frem og tilbage, men den bliver ved med at køre frem og tilbage øverst på skærmen! ➡️⬅️

Hvordan får vi vores bug til at blive ved med at bevæge sig nedad ⬇️, så den fylder hele arenaen?

```blockconfig.local
hourOfAi.doAfter(1000, function () {

})
```

## Opret en variabel

Vi skal ændre den retning, vores bug drejer i, hver gang den rammer en væg.  Først drejer den mod højre ➡️ (90 grader), og derefter skal den dreje mod venstre ⬅️ (-90 grader) – sådan fortsætter den frem og tilbage.

Lad os først oprette en variabel.

Åbn kategorien ``||Variables:Variabler||`` i værktøjskassen, og klik på knappen **Opret en variabel**.

Giv variablen navnet **angle**, og klik på Ok.

~hint Hvad er en variabel?

---

En **variabel** er ligesom en beholder 🪣, der indeholder en værdi. Variabler har navne, så du nemt kan bruge dem i dit program. Værdierne i variabler kan ændre sig.

hint~

```blockconfig.local
hourOfAi.doAfter(1000, function () {

})
```

## Indstil variablens værdi

Fra kategorien ``||Variables:Variabler||`` skal du trække en ``||Variables:sæt angle til 0||``-blok ind i ``||hourOfAi:ved start||``-blokken.

Skriv **-90** som værdi for variablen angle i stedet for **0**.

```blockconfig.local
hourOfAi.doAfter(1000, function () {

})
```

```blocks
let angle = 0
hourOfAi.onStart(function () {
    hourOfAi.turnTowards(0)
    //@highlight
    angle = -90
})
```
## Skift variablens værdi, når buggen rammer en væg

Fra kategorien ``||Variables:Variabler||`` skal du trække endnu en ``||Variables:sæt angle til 0||``-blok ind øverst i ``||hourOfAi:når buggen rammer en væg||``-blokken.

```blockconfig.local
hourOfAi.doAfter(1000, function () {

})
```

```blocks
hourOfAi.onBumpWall(function () {
    //@highlight
    angle = 0
    hourOfAi.turnBy(90)
    hourOfAi.doAfter(1000, function () {
        hourOfAi.turnBy(90)
    })
})
```

## Gang med -1

For at skifte frem og tilbage mellem 90 og -90 grader ganger vi med -1.

Fra værktøjskategorien ``||Math:Matematik||`` skal du trække en ``||Math:0 × 0||``-blok ud og slippe den i ``||Variables:sæt angle til||``-blokken i stedet for **0**.

Fra kategorien ``||Variables:Variabler||`` skal du trække en ``||Variables:angle||``-blok ud og slippe den i ``||Math:0 × 0||``-blokken i stedet for det første **0**.

Skriv **-1** som den anden værdi i ``||Math:0 × 0||``-blokken.

```blockconfig.local
hourOfAi.doAfter(1000, function () {

})
```

```blocks
hourOfAi.onBumpWall(function () {
    //@highlight
    angle = angle * -1
    hourOfAi.turnBy(90)
    hourOfAi.doAfter(1000, function () {
        hourOfAi.turnBy(90)
    })
})
```

## Drejevinkel

Nu skal vi erstatte vores drejninger på 90 grader med variablen ``||Variables:angle||``.

Fra kategorien ``||Variables:Variabler||`` skal du trække to ``||Variables:angle||``-blokke ud og slippe én i hver ``||hourOfAi:drej||``-blok i stedet for de **90** grader.

```blockconfig.local
hourOfAi.doAfter(1000, function () {

})
```

```blocks
hourOfAi.onBumpWall(function () {
    angle = angle * -1
    //@highlight
    hourOfAi.turnBy(angle)
    hourOfAi.doAfter(1000, function () {
        //@highlight
        hourOfAi.turnBy(angle)
    })
})
```

## 🎉 Godt arbejde! 🎉

Test dit spil igen i 🕹️ spilvinduet.

Du kan flytte **SPEED**-skyderen mod højre ➡️ og se din bug bevæge sig frem og tilbage, mens den fylder skærmen med masser af maling!

👏 Flot arbejde! Du har kodet en smart AI-algoritme ✨, som vil slå dine modstandere 🍃 af banen i Bug Arena!

Gå videre til 🏰 Tårnkamp for at udfordre dine bug-rivaler!

```blockconfig.local
hourOfAi.doAfter(1000, function () {

})
```

```blocks
let angle = 0
hourOfAi.onStart(function () {
    hourOfAi.turnTowards(0)
    angle = -90
})
hourOfAi.onBumpWall(function () {
    angle = angle * -1
    hourOfAi.turnBy(angle)
    hourOfAi.doAfter(1000, function () {
        hourOfAi.turnBy(angle)
    })
})
```

```template
hourOfAi.onStart(function () {
	
})
```

```package
bug-arena=github:ChrisesDK/bug-arena#0ce10d860d180012df631a557b96ecba6823f4a0
```
