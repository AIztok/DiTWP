---
title: 131_Markdown
draft: false
tags:
  - md
  - PKD
---
# Allgemein

Markdown ist eine leichtgewichtige Auszeichnungssprache, die ursprünglich von [John Gruber](https://en.wikipedia.org/wiki/John_Gruber) und [Aaron Swartz](https://de.wikipedia.org/wiki/Aaron_Swartz) im Jahr 2004 entwickelt wurde. Sie dient dazu, Textdokumente auf einfache Weise zu formatieren, indem sie leicht lesbare und schreibbare Plain-Text-Notationen verwendet, die in HTML oder andere Ausgabeformate konvertiert werden können. Markdown ist besonders beliebt bei Programmierern, Autoren und Bloggern, da es sich gut für das Schreiben von technischen Dokumenten und Webinhalten eignet.

# Beispiele der Formatierung

In Markdown sind Formatierungen wie Überschriften, Listen, Tabellen und Links durch spezielle Zeichen und Syntax gekennzeichnet. Hier sind einige grundlegende Formatierungselemente:

1.  Überschriften: Man kann verschiedene Überschriftenebenen erstellen, indem man Hashtags (#) vor den Text setzt. Zum Beispiel erzeugt `# Überschrift 1` eine Überschrift der ersten Ebene, während `## Überschrift 2` eine Überschrift der zweiten Ebene erzeugt.
2.  Listen: Man kann ungeordnete Listen mit einem Sternchen (*) oder Bindestrich (-) erstellen, gefolgt von einem Leerzeichen. Geordnete Listen erstellt man, indem man die Liste mit Zahlen und einem Punkt (z.B. `1.`) beginnt.
3. Fettschrift: Um Text fett zu formatieren, umschließen Sie ihn mit doppelten Sternchen `**` oder doppelten Unterstrichen `__`. Zum Beispiel: `**fetter Text**` oder `__fetter Text__` wird zu **fetter Text**.
4. Kursivschrift: Um Text kursiv zu formatieren, umschließen Sie ihn mit einfachen Sternchen `*` oder einfachen Unterstrichen `_`. Zum Beispiel: `*kursiver Text*` oder `_kursiver Text_` wird zu _kursiver Text_.
5. Unterstrichener Text, schreiben `<u>`  vor und `</u>` hinter dem Text den Sie unterstreichen wollen, Beispiel: <u>dieser Text ist unterstrichen</u>
6. Durchgestrichener Text: Um Text durchzustreichen, verwenden Sie doppelte Tilden `~~`. Zum Beispiel: `~~durchgestrichener Text~~` wird zu ~~durchgestrichener Text~~.
7. Zitate: Um ein Zitat zu erstellen, beginnen Sie die Zeile mit einem größer-als-Zeichen `>` gefolgt von einem Leerzeichen. Zum Beispiel: `> Zitat` erzeugt:
> Zitat
8. Programmiercode:
- Inline-Code: Um Code innerhalb einer Zeile darzustellen, umschließen Sie den Text mit einfachen Backticks (`` ` ``). Zum Beispiel: `` `Code` `` wird zu `Code`.
-   Mehrzeiliger Code: Um mehrzeiligen Code darzustellen, umschließen Sie den Text mit dreifachen Backticks (` ``` `), gefolgt von einer neuen Zeile für den Code und dann nochmals dreifachen Backticks, um den Codeblock zu schließen. Zum Beispiel:
```
x = 10
y = 20
z = x + y
```
9. wie folgend mit Doppeldollar-Zeichen können auch Gleichungen geschrieben werden, mehr dazu [hier](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/writing-mathematical-expressions):
$$
N = g * L^2 / (8*f)
$$
10.  Externe Links einbetten: der Text wird dabei eckige Klammern gesetzt und der Link in runde - "(text)[Adresse]". Z.B. [Building smarts](https://www.buildingsmart.org/)

12.  Interne Links zu anderen Notizen im Vault einbetten: doppelt eckige Klammer und im Dropdown Menu die Notiz auswähle, z.B. siehe [[018_Obsidian]]

13. Checkbox erstellen:

- [ ] Aufgabe
- [ ] Nächste Aufgabe


14. Videos einbetten, z.B. auf YouTube auf Share / Embed und dann den Textblock ein kopieren:

<iframe width="560" height="315" src="https://www.youtube.com/embed/HNFF_EeFr9Y?si=ZdDDSdOY_Kyv7z3L" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

12. Bruchlinie zeichnen mit drei Bindestrichen "---"
---

# Weitere Unterlagen

Erläuterung der Markdown Sprache:
https://www.markdownguide.org/

Online Markdown Editor:
https://dillinger.io/