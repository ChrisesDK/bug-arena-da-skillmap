# Bug Arena: Kruseduller
### @hideReplaceMyCode true

## Introduktion til Bug Arena @showdialog

Velkommen til 👾 **Bug Arena** 👾, hvor de klogeste bugs kæmper om æren!

Se denne introduktionsvideo for at komme i gang, og klik derefter på Ok.

![Introduktion til Bug Arena](youtube:U_bcAht2o0A "introduktionsvideo om Bug Arena")

## Tilfældig algoritme @showdialog

![Bug Arena: tilfældigt mønster](/static/skillmap/bug-arena/random.gif "animation af et tilfældigt mønster")

Godt valg af algoritme – lad kaosset råde! 🤪

I denne vejledning koder vi en AI-algoritme ✨ til vores bug, så den bevæger sig i tilfældige mønstre 🌀 på skærmen.

## Hvornår skal buggen dreje? 

Lad os få vores bug til at dreje i en ny retning hvert 5. sekund.  Det gør vi med en tidsintervalblok. 🕓

Fra værktøjskategorien ``||hourOfAi:Bug AI||`` skal du trække en ``||hourOfAi:hver 5000 ms||``-blok ud på arbejdsområdet – du kan placere den hvor som helst.

![Træk og slip blokke](/static/skillmap/bug-arena/dragdrop.gif "animation af at trække og slippe blokke")

~hint Hvad gør denne blok?

---

Blokken ``||hourOfAi:hver 5000 ms||`` kører den kode, du lægger ind i den, med et bestemt millisekundinterval (ms) 🕓 – i dette tilfælde hver 5000 ms eller hvert 5. sekund.

hint~

Klik på pæren 💡, hvis du har brug for hjælp, eller klik på **Næste** for at fortsætte.

```blockconfig.local
hourOfAi.every(5000, function () {

})
randint(-180, 180)
```

```blocks
hourOfAi.every(5000, function () {

})
```

## Drej din bug!

Fra kategorien ``||hourOfAi:Bug AI||`` skal du trække en ``||hourOfAi:drej 90°||``-blok ud og slippe den i ``||hourOfAi:hver 5000 ms||``-blokken.
<br/>
<br/>

~hint Hvad gør drej 90°?

---

Drejeblokken ↩️ drejer vores bug et bestemt antal grader fra dens nuværende retning. Et positivt tal ➕ drejer med uret, og et negativt tal ➖ drejer mod uret.

![Drejevinkel](/static/skillmap/bug-arena/turn-angle.png "drejevinkel")

hint~

```blockconfig.local
hourOfAi.every(5000, function () {

})
randint(-180, 180)
```

```blocks
hourOfAi.every(5000, function () {
    //@highlight
    hourOfAi.turnBy(90)
})
```

## 🎲 Vælg tilfældigt

Hvert 5. sekund skal vores bug dreje i en ny, tilfældig retning.

Fra værktøjskassen ``||Math:Matematik||`` skal du trække en ``||Math:vælg tilfældig fra 0 til 10||``-blok og slippe den i ``||hourOfAi:drej||``-blokken, så den erstatter **90**.
<br/>
<br/>

~hint Hvad gør Vælg tilfældigt?

---

Blokken ``||Math:vælg tilfældig fra 0 til 10||`` giver et tilfældigt tal 🎲 mellem en mindsteværdi ⏬ og en størsteværdi ⏫. I dette tilfælde giver den et tilfældigt tal mellem **-180** grader (mod uret) og **+180** grader (med uret).

hint~

```blockconfig.local
hourOfAi.every(5000, function () {

})
randint(-180, 180)
```

```blocks
hourOfAi.every(5000, function () {
    //@highlight
    hourOfAi.turnBy(randint(-180, 180))
})
```

## 🔎 Find nogle bugs!

Lad os teste vores algoritme og sikre os, at buggen gør det, vi forventer – at den løber rundt i tilfældige mønstre!

I spilvinduet 🖼️ skal du klikke på knappen **Practice**.

Vælg derefter **No Opponent** og **Infinite**.

Skifter din bug retning hvert 5. sekund?  Sejt! 😎

```blockconfig.local
hourOfAi.every(5000, function () {

})
randint(-180, 180)
```

## 🧱 Når buggen rammer en væg

Lad os tilføje kode, så vores bug drejer ↩️, når den rammer en væg.

Fra kategorien ``||hourOfAi:Bug AI||`` skal du trække en ``||hourOfAi:når buggen rammer en væg||``-blok ud på arbejdsområdet – du kan placere den hvor som helst.

Træk nu endnu en ``||hourOfAi:drej 90°||``-blok og slip den i ``||hourOfAi:når buggen rammer en væg||``-blokken.

```blockconfig.local
hourOfAi.every(5000, function () {

})
randint(-180, 180)
```

```blocks
hourOfAi.onBumpWall(function () {
    hourOfAi.turnBy(90)
})
```

## Drej tilfældigt

Igen vil vi have, at vores bug drejer i en tilfældig retning, så lad os bruge funktionen 🎲 Vælg tilfældigt igen.

Fra værktøjskassen ``||Math:Matematik||`` skal du trække endnu en ``||Math:vælg tilfældig fra 0 til 10||``-blok og slippe den i ``||hourOfAi:drej||``-blokken, så den erstatter **90**.

```blockconfig.local
hourOfAi.every(5000, function () {

})
randint(-180, 180)
```

```blocks
hourOfAi.onBumpWall(function () {
    //@highlight
    hourOfAi.turnBy(randint(-180, 180))
})
```

## 🎉 Godt arbejde! 🎉

Test dit spil igen i 🕹️ spilvinduet.

Du kan flytte **SPEED**-skyderen mod højre ➡️ og se din bug lave flotte, skøre 🌈 farvemønstre!

Flot arbejde! 👍 Du har kodet en smart AI-algoritme ✨, som vil forvirre og narre dine modstandere i Bug Arena!

Gå videre til 🏰 Tårnkamp for at udfordre dine bug-rivaler!

```blockconfig.local
hourOfAi.every(5000, function () {

})
randint(-180, 180)
```

```blocks
hourOfAi.every(5000, function () {
    hourOfAi.turnBy(randint(-180, 180))
})
hourOfAi.onBumpWall(function () {
    hourOfAi.turnBy(randint(-180, 180))
})
```

```template
hourOfAi.onStart(function () {
	
})
```

```package
bug-arena=github:ChrisesDK/bug-arena#0ce10d860d180012df631a557b96ecba6823f4a0
```
