# Bug Arena: Kvadrater
### @hideReplaceMyCode true

## Introduktion til Bug Arena @showdialog

Velkommen til 👾 **Bug Arena** 👾, hvor de klogeste bugs kæmper om æren!

Se denne introduktionsvideo for at komme i gang, og klik derefter på Ok.

![Introduktion til Bug Arena](youtube:U_bcAht2o0A "introduktionsvideo om Bug Arena")

## Kvadratisk algoritme @showdialog

![Bug Arena: kvadrater](/static/skillmap/bug-arena/squares.gif "animation af et kvadratisk mønster")

Godt valg af AI-algoritme ✨ – du kommer helt sikkert til at sætte 🟨 konkurrenterne på plads!

Lad os kode din bug, så den bevæger sig rundt på skærmen og farvelægger arenaen i et kvadratisk mønster.

## Indstil retning

Vores bug bevæger sig selv, men det er vigtigt, at den starter med at bevæge sig i den rigtige retning! 🗺️

Fra værktøjskategorien **Bug AI** skal du trække blokken **vend mod 0°** ud og slippe den i **ved start**-blokken.

~hint Hvad gør denne blok?

---

**vend mod** drejer din bug, så den peger mod en bestemt vinkel i grader, hvor:
- 0 = højre
- 90 = ned
- 180 = venstre
- 270 = op

![Peg mod grader](/static/skillmap/bug-arena/degrees.png "peg mod grader")

Så starter vores bug med at bevæge sig mod højre side af skærmen.

hint~

```blockconfig.local
hourOfAi.every(500, function () {
    if (hourOfAi.distanceToColor(ColorType.MyColor) == 0) {
    	
    }
})
```

```blocks
hourOfAi.onStart(function () {
    //@highlight
    hourOfAi.turnTowards(0)
})
```

## Når buggen rammer en væg

I spilvinduet 🖼️ nederst til højre skal du klikke på knappen **Practice**.

Vælg derefter **No Opponent** og **Infinite**.

Hvad sker der, når din bug kommer til den anden side af skærmen?

Åh nej!  Den sidder fast! 🔄

Lad os kode noget, der sker, når den rammer en væg. 🧱

Fra kategorien **Bug AI** skal du trække en **når buggen rammer en væg**-blok ud på arbejdsområdet – du kan placere den hvor som helst.

```blockconfig.local
hourOfAi.every(500, function () {
    if (hourOfAi.distanceToColor(ColorType.MyColor) == 0) {
    	
    }
})
```

```blocks
hourOfAi.onBumpWall(function () {

})
```

## Drej 90°

Fra kategorien **Bug AI** skal du trække en **drej 90°**-blok og slippe den i **når buggen rammer en væg**-blokken.
<br/>
<br/>

~hint Hvad gør drej 90°?

---

Drejeblokken ↩️ drejer vores bug et bestemt antal grader.  Et positivt tal ➕ drejer med uret, og et negativt tal ➖ drejer mod uret.

![Drejevinkel](/static/skillmap/bug-arena/turn-angle.png "drejevinkel")

I dette tilfælde beholder vi den på 90 grader, fordi vi vil have, at vores bug drejer i en ret vinkel ved hjørnet af skærmen.

hint~

```blockconfig.local
hourOfAi.every(500, function () {
    if (hourOfAi.distanceToColor(ColorType.MyColor) == 0) {
    	
    }
})
```

```blocks
hourOfAi.onBumpWall(function () {
    //@highlight
    hourOfAi.turnBy(90)
})
```

## Test for bugs! 🐞

Lad os teste vores algoritme og se, om vores bug bevæger sig i et kvadrat. 🟨

Hvad sker der i spilvinduet 🖼️, når vores bug dækker alle fire sider af arenaen?

Åh nej!  Den bliver bare ved med at bevæge sig i det samme kvadratiske mønster! ⏹️

Hvordan får vi vores bug til at bevæge sig i et koncentrisk, kvadratisk mønster, så den fylder hele skærmen?

~hint Hvad betyder koncentrisk?

---

**Koncentrisk** betyder former, der passer ind i hinanden, ligesom en skydeskive 🎯 består af koncentriske cirkler.

hint~

```blockconfig.local
hourOfAi.every(500, function () {
    if (hourOfAi.distanceToColor(ColorType.MyColor) == 0) {
    	
    }
})
```

## Hvornår skal den dreje?

Vi skal få vores bug til at tjekke, at den ikke står på en del af skærmen, der allerede er dækket af dens egen malingsfarve 🎨, før den drejer.

Fra kategorien **Bug AI** skal du trække gruppen af **hver 500 ms**-blokke ud på arbejdsområdet – du kan placere den hvor som helst.

~hint Hvad gør denne blok?

---

Blokken **hver 500 ms** kører den kode, du lægger ind i den, med et bestemt tidsinterval ⏱️ – i dette tilfælde hver 500 millisekunder (ms) eller et halvt sekund.  Blokken **afstand til min farve** giver afstanden i pixels fra forsiden af vores bug til dens egen malingsfarve 🎨. Hvis afstanden er 0, står vores bug på sin egen maling!

hint~

```blockconfig.local
hourOfAi.every(500, function () {
    if (hourOfAi.distanceToColor(ColorType.MyColor) == 0) {
    	
    }
})
```

```blocks
hourOfAi.every(500, function () {
    if (hourOfAi.distanceToColor(ColorType.MyColor) == 0) {

    }
})
```

## Drej til højre

Når afstanden fra vores bug til dens egen malingsfarve er 0, skal den dreje til højre. ↩️

Fra kategorien **Bug AI** skal du trække en **drej 90°**-blok ud og slippe den i **hvis så**-blokken.

```blockconfig.local
hourOfAi.every(500, function () {
    if (hourOfAi.distanceToColor(ColorType.MyColor) == 0) {
    	
    }
})
```

```blocks
hourOfAi.every(500, function () {
    if (hourOfAi.distanceToColor(ColorType.MyColor) == 0) {
        //@highlight
        hourOfAi.turnBy(90)
    }
})
```

## 🎉 Godt arbejde! 🎉

Test dit spil igen i 🕹️ spilvinduet nedenfor.

Du kan flytte **SPEED**-skyderen mod højre ➡️ og se din bug lave perfekte kvadrater! 🟨🟦🟩

Flot arbejde! 👍 Du har kodet en smart AI-algoritme ✨, som vil spærre dine modstandere inde i Bug Arena!

Gå videre til 🏰 Tårnkamp for at udfordre dine bug-rivaler!

```blockconfig.local
hourOfAi.every(500, function () {
    if (hourOfAi.distanceToColor(ColorType.MyColor) == 0) {
    	
    }
})
```

```blocks
hourOfAi.onStart(function () {
    hourOfAi.turnTowards(0)
})
hourOfAi.onBumpWall(function () {
    hourOfAi.turnBy(90)
})
hourOfAi.every(500, function () {
    if (hourOfAi.distanceToColor(ColorType.MyColor) == 0) {
        hourOfAi.turnBy(90)
    }
})
```

```template
hourOfAi.onStart(function () {
	
})
```

```package
bug-arena=github:ChrisesDK/bug-arena#0ce10d860d180012df631a557b96ecba6823f4a0
```
