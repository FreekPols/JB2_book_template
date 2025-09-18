# Markdown (Cheatsheet)


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
A Jupyter Book 2 made with MyST requires a collection of markdown and Jupyter notebooks, which can then be exported to PDF, HTML, and even Word.

## Structure
We can distinguish between two structures: that of the book's content (a collection of different documents), and the (internal) structure of the chapters.

### Table of Contents
The software we use automatically builds a table of contents (ToC) in alphabetical order. But you can also specify the ToC yourself. This is best done offline (`jupyter init --toc`), see the [MyST documentation](https://mystmd.org/guide/table-of-contents#toc-format-legacy).

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
- [x] Create a markdown cheat sheet
- [x] Publish online
- [] Let others test
:::
:::{tab-item} syntax
```markdown
- [x] Create a markdown cheat sheet
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
