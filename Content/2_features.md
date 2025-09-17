# Markdown (Cheatsheet)

Markdown is a simple markup language: plain text that is *formatted* with small pieces of 'code'. This text can then be quickly exported to various other formats such as PDF, Word, HTML, etc.

```{figure} ../Figures/MyST.PNG
:width:80%
```

````{tab-set}
:::{tab-item} list
* This is a reference to a figure like {numref}`Figure {number} <fig_sunset>`
* This is a reference to a table like {numref}`Table {number} <tl_sanctions>`
* This is a reference to equation {eq}`eq:Newton`
* This is a [hyperlink](https://nos.nl)
:::
:::{tab-item} syntax
```markdown
* This is a reference to a figure like {numref}`Figure {number} <fig_sunset>`
* This is a reference to a table like {numref}`Table {number} <tl_sanctions>`
* This is a reference to equation {eq}`eq:Newton`
* This is a [hyperlink](https://nos.nl)
```
:::
````
A Jupyter Book made with MyST requires a collection of markdown and Jupyter notebooks, which can then be exported to PDF, HTML, and even Word.

## Structure
We can distinguish between two structures: that of the book's content (a collection of different documents), and the (internal) structure of the chapters.

### Table of Contents
The software we use automatically builds a table of contents (ToC) in alphabetical order. But you can also specify the ToC yourself. This is best done offline (`myst init --toc`), see the [MyST documentation](https://mystmd.org/guide/table-of-contents#toc-format-legacy).

### Chapters
To distinguish between chapter, section, and subsection (and further), use a number of `#` symbols, as shown below.

```markdown
# H1 chapter  
## H1.1 section   
### H1.1.3 subsection  
```

```{tip}
Do not number your chapters and sections! This happens automatically.
```

You can create a new line by either a hard enter and a blank line, a `\` at the end of the line and enter, or two spaces at the end of the line.

### New Line
::::{tab-set}
:::{tab-item} list
A new line with double space.  
A new line with a `\`.\  
No new line with just a hard enter and blank line.

End of exercise.
And an example if the previous line does not end with the above.
:::
:::{tab-item} syntax
```markdown
A new line with double space.  
A new line with a `\`.\  
A new line with a hard enter and blank line.

End of exercise.
And an example if the previous line does not end with the above.
```
:::
::::

## Basic Formatting
Markdown is a markup language where text formatting is done with small pieces of code (just like HTML).

| Element | Syntax | Example | 
| --- | --- | --- |
| Bold | `**bold text**` | **Bold** |
| Italic | `*italics*` | *Italics* |
| Emphasis | `***emphasis***` | ***emphasis*** |
| Inline Formula | `$F = m \cdot a$` | $F = m \cdot a$ |
| Super and subscript | ``H{sub}`2`O, and 4{sup}`th` of July`` | H{sub}`2`O, and 4{sup}`th` of July|
| Footnote | ` - A footnote reference[^myref] \ [^myref]: This is an auto-numbered footnote definition.`|- A footnote reference[^myref] \ [^myref]: This is an auto-numbered footnote definition.| 

### Lists Option 1
::::{tab-set}
:::{tab-item} list
1. item 1
1. item 2.
1. item 3.
:::
:::{tab-item} syntax
```markdown
1. item 1
1. item 2.
1. item 3.
```
:::
::::

### Lists Option 2
::::{tab-set}
:::{tab-item} list
1. item 1
2. item 2.
3. item 3.
:::
:::{tab-item} syntax
```markdown
1. item 1
2. item 2.
3. item 3.
```
:::
::::

### Tabs

```markdown
::::{tab-set}
:::{tab-item} Tab 1
Text in tab 1
:::

:::{tab-item} Tab 2
Text in tab 2
:::
::::
```

### Checklists 
::::{tab-set}
:::{tab-item} list
- [x] Create a markdown cheatsheet
- [x] Publish online
- [] Let others test
:::
:::{tab-item} syntax
```markdown
- [x] Create a markdown cheatsheet
- [x] Publish online
- [] Let others test
```
:::
::::

## Formulas

For STEM subjects, mathematical equations are essential. You can also include equations in JB's. What is possible in LaTeX is also possible in JB, for example:

$$ F_{res} = m \cdot a$$ (eq:Newton)

Where labeled equations, such as {eq}`eq:Newton`, can be referenced.

`$$ Equation $$`

But you can also include inline equations like this: $s=v_{avg}t$. Use a single dollar sign before and after: `$ Equation $`

|Name|Script|Symbols|
|---|---|---|
|root|`\sqrt{4}`|$\sqrt{4}$|
|power|`^{2x}`|$^{2x}$|
|fraction|`\frac{2}{3}`|$\frac{2}{3}$|
|subscript|`_{avg}`|$_{avg}$|
|superscript|`^{N}`|$^{N}$|
|multiply|`\cdot`|$\cdot$|

Some examples:
|Name|Script|Output|
|---|---|---|
|Derivative|`\frac{\Delta f}{\Delta t}`|$\frac{\Delta f}{\Delta t}$|
|Integral|`\int_a^b dx`|$\int_a^b dx$|
|sine|`sin(x)`|$sin(x)$|

More: https://en.wikibooks.org/wiki/LaTeX/Mathematics

## Admonitions
You can add special blocks that are highlighted in the text. See, for example, the warning below.

```{warning}
Here is a warning
```

There are different variants such as:
* tip 
* admonition 
* warning 
* note 
* objective 
* see also ...

```{tip} The golden...
Exercises are a special kind of admonition.
```

### Exercises
```{exercise} Exercise 1
:label: ex_opdr_1

Calculate $4+2$
```

```{solution} ex_opdr_1
:class: dropdown

6
```

## Figures
A site/book naturally needs figures. There are roughly two ways to add a figure:

*Quick figure, without formatting options*

| Quick figure | `![](link to figure)` |

*Better way with more control:*

::::{tab-set}
:::{tab-item} Figures

```{figure} https://github.com/rowanc1/pics/blob/main/sunset.png
:label: fig_sunset
:width: 70%
:align: center

With a nice caption
```

:::

:::{tab-item} MyST Syntax

````markdown
```{figure} https://github.com/rowanc1/pics/blob/main/sunset.png
:label: fig1
:width: 70%
:align: center

With a nice caption
```
````

:::
::::

Here we used figures hosted online, but you can also add figures to a folder (e.g., called *Figures*), and then use a relative path.

## Tables

Tables are created with the separator `|`

::::{tab-set}
:::{tab-item} Tables

```
|Header 1|Header 2|Header 3|
|---|---|---|
|text 1|text 2|text 3|
|text 4|text 5|text 6|
```

:::

:::{tab-item} MyST Syntax

````markdown
```
|Header 1|Header 2|Header 3|
|---|---|---|
|text 1|text 2|text 3|
|text 4|text 5|text 6|
```
````

:::
::::

Or via ...

::::{tab-set}
:::{tab-item} Tables

```{list-table} Overview of sanctions for certain behavior
:header-rows: 1
:name: tl_sanctions
* - Behavior
    - Sanction for 1st time
    - Sanction for 2nd time
* - Not (timely or with a valid reason) deregistered 
    - A penalty                                       
    - exclusion              
```

:::

:::{tab-item} MyST Syntax

````markdown
```{list-table} Overview of sanctions for certain behavior
:header-rows: 1
:name: tl_sanctions
* - Behavior
    - Sanction for 1st time
    - Sanction for 2nd time
* - Not (timely or with a valid reason) deregistered 
    - A penalty                                       
    - exclusion              
``` 
````

:::
::::

Method 2 has the advantage of allowing references to {numref}`Table {number} <tl_sanctions>`

## YouTube
To embed YouTube videos on the site, you need the embed YT link. The code is then:

::::{tab-set}
:::{tab-item} YouTube
```{iframe} https://www.youtube.com/embed/YDBr1Lof_mI?si=thWYK9MFi5QJv-tW
:width: 80%
:align: center

A super fun video from the project [Show the Physics](https://interactivetextbooks.tudelft.nl/showthephysics)
```
:::
:::{tab-item} syntax
````markdown
```{iframe} https://www.youtube.com/embed/YDBr1Lof_mI?si=thWYK9MFi5QJv-tW
:width: 80%
:align: center

A super fun video from the project [Show the Physics](https://interactivetextbooks.tudelft.nl/showthephysics)
```
````
:::
::::

```{warning} YT in pdf
Embedded YT videos are not included in the PDF. A solution could be to include a QR code, for example.
```

(sec-ref)=
## References

::::{tab-set}
:::{tab-item} list
* This is a [hyperlink](https://nos.nl)  
* This is a reference to equation {eq}`eq:Newton`  
* This is a reference to a table like {numref}`Table {number} <tl_sanctions>`  
* This is a reference to a figure like {numref}`Figure {number} <fig_sunset>`  
:::
:::{tab-item} syntax
```markdown
* This is a [hyperlink](https://nos.nl)  
* This is a reference to equation {eq}`eq:Newton`  
* This is a reference to a table like {numref}`Table {number} <tl_sanctions>`  
* This is a reference to a figure like {numref}`Figure {number} <fig_sunset>`  
```
:::
::::

:width:80%

Een Jupyter Book gemaakt met MyST vraagt een collectie van markdown en jupyter notebooks die vervolgens geëxporteerd kunnen worden naar pdf, html maar ook word.
```

## Structuur
We kunnen hier onderscheid maken in twee structuren: die van de inhoud van de boek (een collectie van verschillende documenten), en de (interne)structuur van de hoofdstukken.

### Table of Contents
De software waar we gebruik van maken bouwt zelf een inhoudsopgave (Table of contents, ookwel ToC). Dat gaat op alfabetische volgorde. Maar je kunt ook zelf de ToC specificeren. Dit kan wel het beste door offline te werken (myst init --toc), zie de [documentatie van MyST](https://mystmd.org/guide/table-of-contents#toc-format-legacy). 

### Hoofdstukken
Om onderscheid te maken tussen hoofdstuk, sectie en subsectie (en verder) wordt er gewerkt met aantal `#`, zie hieronder.

```markdown
# H1 hoofdstuk  
## H1.1 sectie   
### H1.1.3 subsectie  
```

```{tip}
Nummer je hoofdstukken en sectie niet! Dit gebeurt automatisch.
```

Een nieuwe regel krijg je door of een harde enter en een witregel, of door een \ achter de zin en een enter of door twee spaties achter de zin.


### Nieuwe regel
::::{tab-set}
:::{tab-item} list
Een nieuwe regel met dubbele spatie.  
Een nieuwe regel met een `\`.\
Een niet regel met een harde enter en witregel.

Einde oefening.
En een voorbeeld als de vorige regel niet eindigt met bovenstaande.
:::
:::{tab-item} syntax
```markdown
Een nieuwe regel met dubbele spatie.  
Een nieuwe regel met een `\`.\
Een nieuw regel met een harde enter en witregel.

Einde oefening.
En een voorbeeld als de vorige regel niet eindigt met bovenstaande.
```
:::
::::


## Basic opmaak
Markdown is een opmaaktaal waarbij de formatting van de tekst gedaan wordt met kleine stukjes code (net als bij HTML).

| Element | Syntax | Voorbeeld | 
| --- | --- | --- |
| Bold | `**dik gedrukte tekst**` | **Bold** |
| Italic | `*italics*` | *Italics*
| Emphasis | `***emphasis***` | ***emphasis*** |
| in line Formule | `$F = m \cdot a$` | $F = m \cdot a$ |
| Super en subscript | ``H{sub}`2`O, and 4{sup}`th` of July`` | H{sub}`2`O, and 4{sup}`th` of July|
| Footnote | ` - A footnote reference[^myref] \ [^myref]: This is an auto-numbered footnote definition.`|- A footnote reference[^myref] \ [^myref]: This is an auto-numbered footnote definition.| 


### Lijsten optie 1
::::{tab-set}
:::{tab-item} list
1. item 1
1. item 2.
1. item 3.
:::
:::{tab-item} syntax
```markdown
1. item 1
1. item 2.
1. item 3.
```
:::
::::

### Lijsten optie 2
::::{tab-set}
:::{tab-item} list
1. item 1
2. item 2.
3. item 3.
:::
:::{tab-item} syntax
```markdown
1. item 1
2. item 2.
3. item 3.
```
:::
::::

### Tabbladen

```markdown
::::{tab-set}
:::{tab-item} Tab 1
Hier tekst in tab 1
:::

:::{tab-item} Tab 2
Hier tekst in tab 2
:::
::::
```

### Afvinklijsten 
::::{tab-set}
:::{tab-item} list
- [x] Een markdown cheatsheet maken
- [x] Online zetten
- [] Laten testen
:::
:::{tab-item} syntax
```markdown
- [x] Een markdown cheatsheet maken
- [x] Online zetten
- [] Laten testen
```
:::
::::


## Formules

Voor de betavakken zijn wiskundige vergelijkingen essentieel. Ook in JB's kun je vergelijkingen opnemen. Wat in LaTeX kan, kan in JB ook, bijv:

$$ F_{res} = m \cdot a$$ (eq:Newton)

Waarbij gelabelde vergelijkingen, zoals {eq}`eq:Newton` naar verwezen kan worden. 

`$$ Vergelijking $$`

Maar je kunt ook inline vergelijkingen opnemen zoals deze: $s=v_{gem}t$. Daarbij gebruik je een enkele dollar teken voor en na je `$ Vergelijking $`


|Naam|Script|Symbolen|
|---|---|---|
|wortel|`\sqrt{4}`|$\sqrt{4}$|
|macht|`^{2x}`|$^{2x}$|
|breuk|`\frac{2}{3}`|$\frac{2}{3}$|
|subscript|`_{gem}`|$_{gem}$
|superscript|`^{N}`|$^{N}$|
|vermenigvuldig|`\cdot`|$\cdot$|

Met wat voorbeelden:
|Naam|Script|Output|
|---|---|---|
|Afgeleide|`\frac{\Delta f}{\Delta t}`|$\frac{\Delta f}{\Delta t}$|
|Integraal|`\int_a^b dx`|$\int_a^b dx$|
|sinus|`sin(x)`|$sin(x)$|

Uitgebreider: https://en.wikibooks.org/wiki/LaTeX/Mathematics

## Admonitions
Je kunt speciale blokken toevoegen die gehighlight worden in de tekst. Zie bijvoorbeeld onderstaande waarschuwing.

```{warning}
Hier een waarschuwing
```

Daar zijn verschillende varianten van zoals:
* tip 
* admonition 
* warning 
* note 
* objective 
* see also ...

```{tip} De gouden...
Exercises zijn een speciaal soort admonition.
```

### Opdrachten
```{exercise} Opdracht 1
:label: ex_opdr_1

Maak de som $4+2$
```

```{solution} ex_opdr_1
:class: dropdown

6
```

## Figuren
Een site / boek kan natuurlijk niet zonder figuren. Er zijn grofweg twee manieren om een figuur te maken

*Snelle figuur, zonder opmaak mogelijkheden*

| Snelle figuur | `![](link naar figuur)` |

*Betere manier met meer controle:*

::::{tab-set}
:::{tab-item} Figuren

```{figure} https://github.com/rowanc1/pics/blob/main/sunset.png
:label: fig_sunset
:width: 70%
:align: center

Met een mooi onderschrift
```

:::

:::{tab-item} MyST Syntax

````markdown
```{figure} https://github.com/rowanc1/pics/blob/main/sunset.png
:label: fig1
:width: 70%
:align: center

Met een mooi onderschrift
```
````

:::
::::

Hier hebben we gebruik gemaakt van figuren die op het internet staan, maar je kunt ook figuren zelf toevoegen aan een folder (bijv. genaamd *Figuren*), waarbij je dan een relatief pad op geeft.

## Tabellen

Tabellen worden gemaakt met scheidingsteken `|`

::::{tab-set}
:::{tab-item} Tabellen

```
|Kop 1|Kop 2|Kop3|
|---|---|---|
|tekst 1|tekst 2|tekst 3|
|tekst 4|tekst 5|tekst 6|
```

:::

:::{tab-item} MyST Syntax

````markdown
```
|Kop 1|Kop 2|Kop3|
|---|---|---|
|tekst 1|tekst 2|tekst 3|
|tekst 4|tekst 5|tekst 6|
```
````

:::
::::

Of via ...

::::{tab-set}
:::{tab-item} Tabellen

```{list-table} Overzicht van sancties bij bepaald gedrag
:header-rows: 1
:name: tl_sancties
* - Gedrag
    - Sanctie bij 1e keer
    - Sanctie bij 2e keer
* - Niet (tijdig of met een geldige reden) afgemeld 
    - Een penalty                                       
    - uitsluiting              
```

:::

:::{tab-item} MyST Syntax

````markdown
```{list-table} Overzicht van sancties bij bepaald gedrag
:header-rows: 1
:name: tl_sancties
* - Gedrag
    - Sanctie bij 1e keer
    - Sanctie bij 2e keer
* - Niet (tijdig of met een geldige reden) afgemeld 
    - Een penalty                                       
    - uitsluiting              
``` 
````

:::
::::

Methode 2 heeft als voordeel de mogelijkheid tot refereren naar {numref}`Tabel {number} <tl_sancties>`


## YouTube
Voor het embedden van YouTube filmpjes op de site heb je de embed YT link nodig. De code wordt dan:

::::{tab-set}
:::{tab-item} YouTube
```{iframe} https://www.youtube.com/embed/YDBr1Lof_mI?si=thWYK9MFi5QJv-tW
:width: 80%
:align: center

Een superleuke video van het project [Show the Physics](https://interactivetextbooks.tudelft.nl/showthephysics)
```
:::
:::{tab-item} syntax
````markdown
```{iframe} https://www.youtube.com/embed/YDBr1Lof_mI?si=thWYK9MFi5QJv-tW
:width: 80%
:align: center

Een superleuke video van het project [Show the Physics](https://interactivetextbooks.tudelft.nl/showthephysics)
```
````
:::
::::

```{warning} YT in pdf
De embedded YT filmpjes worden niet opgenomen in de pdf. Een oplossing zou bijv. een qr code opnemen kunnen zijn.
```

(sec-ref)=
## Referenties

::::{tab-set}
:::{tab-item} list
* Dit is een [hyperlink](https://nos.nl)  
* Dit is een verwijzing naar vergelijking {eq}`eq:Newton`  
* Dit is een verwijzing naar een tabel zoals {numref}`Tabel {number} <tl_sancties>`  
* Dit is een verwijzing naar een figuur zoals {numref}`Figuur {number} <fig_sunset>`  
:::
:::{tab-item} syntax
```markdown
* Dit is een [hyperlink](https://nos.nl)  
* Dit is een verwijzing naar vergelijking {eq}`eq:Newton`  
* Dit is een verwijzing naar een tabel zoals {numref}`Tabel {number} <tl_sancties>`  
* Dit is een verwijzing naar een figuur zoals {numref}`Figuur {number} <fig_sunset>`  
```
:::
::::

