---
title: 002_Digitale Tragwerksplanung
draft: false
tags:
  - "#DiTWP"
---

# Was ist Tragwerksplanung?

Für die Definition stützen wir uns auf die [Leistungsmodelle 2023 erarbeitet von Univ.-Prof. DI Hans Lechner](https://www.arching.at/mitglieder/552/leistungsmodelle_20142023.html).

Auszug aus dem LM.VM.23:

![[Pasted image 20240728151455.png]]

Die Tragwerksplanung ist ein Bestandteil der Fachplanung.
Umfasst werden mit der Tragwerksplanung vorrangig die mit der Statik eines Bauwerks einhergehenden Leistungen, Nachweise und Berechnungen. 
Der die Tragwerksplanung Ausführende ist der Tragwerksplaner, oft auch synonym als "Statiker" bezeichnet - was nach Meinung des Autors oft etwas kurzgegriffen ist, da Tragwerksplaner nicht "nur" Nachweise und Berechnungen anstellen, sondern auch bei der Objektplanung tätig sind (führend wenn es sich um Ingenieurbauwerke handelt oder den Architekten unterstützend bei Hochbauplanung).

## Leistungsphasen der Tragwerksplanung

- LPH 1: Grundlagenanalyse
- LPH 2: Vorentwurf
- LPH 3: Konstruktionsentwurf
- LPH 4: Einreichplanung
- LPH 5: Ausführungsplanung
- LPH 6: Ausschreibungs (LVs) und Mitwirkung an der Vergabe

In jeder dieser Leistungsphasen kann der Tragwerksplaner beigezogen werden.
Jede dieser LPH hat ihren Fokus und 

Hier liegt auch die große Herausforderung, zu mindestens nach der Erfahrung des Autors, für die Planer das BIM-Konzept mit den etablierten und auch sinnvollen Teilung der Leistungsphasen zu vereinen, ohne in Details zu versinken wo diese noch nicht eindeutig definiert sind, da nicht wichtig oder einfach nicht vorhanden in der jeweilige Leistungsphase. Die Welt ist oft "messy".

Was im jeden Fall hilft und in dieser LVA vermittelt werden soll:
- ist eine strukturierte Arbeit, speichern von Informationen
- parametrisch aufgebaute Modelle, die Anpassungen ohne größere Aufwände ermöglichen 
- leichtes Teilen von vorhandenen Informationen (Modellen, Ergebnissen) mit anderen Projektbeteiligten um Fehler, Konflikte frühzeitig zu erkennen

# Was ist Digital?

Trocken beschrieben bezieht sich *digital* auf die Darstellung von Informationen in einer binären Form, die von Computern "verstanden" und verarbeitet werden kann. Dabei werden Daten in Form von Einsen und Nullen (Bits) kodiert. Diese digitale Darstellung ermöglicht eine präzise und effiziente Speicherung, Verarbeitung und Übertragung von Informationen. Im Gegensatz zur analogen Darstellung, die kontinuierlich und oft variabel ist, sind digitale Informationen diskret und können einfach vervielfältigt, bearbeitet und fehlerfrei übertragen werden. Digitale Technologie bildet die Grundlage moderner Computer, Smartphones, Netzwerke und vieler anderer elektronischer Geräte und Systeme, die unser tägliches Leben prägen.

Aber im etwas weiteren Sinne gibt es die digitalen Prinzipien auch in der Natur, z.B. in der genetischen Information.
DNA nutzt diskrete Einheiten (Nukleotide), um biologische Informationen zu codieren, was Fehlerkorrekturmechanismen während der DNA-Replikation ermöglicht. Dieser digitalähnliche Prozess in der Genetik sichert die Genauigkeit der Informationsübertragung über Generationen hinweg und zeigt eine Parallele zwischen natürlichen Systemen und menschlich entwickelten digitalen Systemen (siehe [Shannon's theorem](https://en.wikipedia.org/wiki/Noisy-channel_coding_theorem)).
Die DNA wird bei der Entstehung und Entwicklung von Lebewesen Milliarden Mal kopiert und das praktisch fehlerfrei bzw. nur mit kleinen genetischen Mutationen.

Im weiten Sinne bedeutet also **Digital** im Bezug auf diese Lehrveranstaltung (die vier Prinzipien wurden von Gershenfeld ([[003_Literatur]]) übernommen): 

**Reliability - Zuverlässigkeit**: Fehlerkorrektur möglich, werden durch die Weiterbearbeitung der Informationen die Fehler multipliziert und immer größer, oder kann wird ein Prozess bzw. Algorithmus verwendet, wo eine Fehlerkorrektur stattfinden kann.

**Modularity - Modularität**: Modularität beschreibt ein Designprinzip, bei dem ein System in kleinere, unabhängige Module zerlegt wird. Jedes Modul erfüllt eine spezifische Funktion und kann unabhängig von anderen Modulen entwickelt, getestet und gewartet werden. Dies erleichtert nicht nur die Fehlersuche und -behebung, sondern auch die Erweiterung und Anpassung des Systems. Modularität fördert Flexibilität und Wiederverwendbarkeit von Komponenten. 

[Stadium 974](https://www.sbp.de/projekt/stadion-974/) (Bild Quelle [istructe.org](https://www.istructe.org/structural-awards/projects/2022/stadium-974/))
![[Pasted image 20240728155048.png]]

**Locality - Lokalität**: kein Masterplan, das Produkt wächst und wird immer wieder neu definiert durch die Einzelteile. 

**Reversibility - Reversibilität**: kein Abfall, alles kann wiederverwendet werden. Was ist Abfall: ein Erzeugnis das nicht die Information besitzt oder diese nicht gelesen werden kann, wozu kann das Erzeugnis noch dienen. In der Natur gibt es solche Erzeugnisse nicht. Alles wird von Pflanzen, Tieren wiederverwendet um neues zu erschaffen. 
Das ist auch einer der großen Ziele der Bauwirtschaft, Bauprodukte und Bauwerke so zu entwerfen und gestalten, dass eine Wiederverwendbarkeit oder Zerlegung in Einzelteile möglich ist.
Siehe hierzu auch:
- [ProHolz / Zuschnitt 88 / Bauteilbörsen und Materialdatenbanken](https://www.proholz.at/zuschnitt/88/bauteilboersen-und-materialdatenbanken)
- [BauKarussell](https://www.baukarussell.at/)

# Was ist digitale Tragwerksplanung?

Die digitale Tragwerksplanung ist somit das verbinden der Leistungen der Tragwerksplanung mit den Grundprinzipien des digitalen:

**Zuverlässigkeit**
Übertragen auf unsere LVA bedeutet das:
- Analoge Informationen in digitale umzuwandeln, damit diese leicht bearbeitbar und teilbar werden (siehe [[111_VO]])
- Klare Datenstrukturen und Datenformate (siehe [[121_VO]])

**Modularität**
Ein wesentlicher Teil sind standarisierte Schnittstellen (siehe [[134_IFC]]) und nahtlose Zusammenarbeit mit anderen Menschen ([[311_VO]]) bzw. nutzen von einzelnen (z.B. Komponenten in Grasshopper ([[013_Grasshopper]]).

**Lokalität**
Dieses Prinzip erscheint im Gegenspruch zu der üblichen Objektplanung zu sein, wo es in der Regel einen "Masterplan" gibt (z.B. Stadtentwicklungsplan -> Architekturplanung -> Tragwerksplanung). Aber dass ist nur von weit im Sinne einer Post-mortem-Analyse betrachtet. Tatsächlich fließen bei Informationen von oben nach unten als auch von unten nach oben, unabhängig von wie "weit" oder "nah" die Prozesse betrachtet werden. Auch in der Objektplanung und Tragwerksplanung kann ein Herstellungsprozess die Form eines Bauteils bestimmen, . Unsere Aufgabe ist es durch das nutzen von digitalen Methoden zu ermöglichen, dass diese Informationen fließen können und somit sinnvolle Entscheidungen getroffen werden können.

**Reversibilität**
Den Anspruch auf Reversibilität bei unserer LVA begrenzen wir auf unsere Arbeit, was wir in den Übungen erstellen. 
Wie gestellten wir unsere Arbeit so, dass wir Teile von dieser immer wieder neu nutzen können? Dafür werden wir folgende Punkte durchgehen:
- Geometrische Modelle parametrisch in Rhino / Grasshopper erstellen: [[112_UE]]
- Versionierung von Daten, Teilen von Informationen:
	- Dienste die ein Teilen von Informationen ermöglichen: [[321_Speckle]]
	- Konzept hinter Versionierung und Zusammenarbeit mit GIT: [[322_Git]]
Das Konzept der Reversibilität überschneidet sich in unserer LVA mit dem Konzept der Modularität. Nur wenn wir unsere Modell Modular aufbauen, können diese auch Reversibel sein, also wieder verwendbar.

# Warum digitale Tragwerksplanung?

Das menschliche Denken ist stark von analogem Denken geprägt – wir erfassen und verarbeiten Informationen intuitiv und bildhaft. Diese Denkweise ist entscheidend, um komplexe Zusammenhänge zu verstehen und kreative Lösungen zu finden. Skizzen auf Papier und Diskussionen mit anderen sind wichtige Methoden, um unsere Gedanken zu visualisieren, zu strukturieren und zu präzisieren. Sie fördern den Austausch von Ideen und helfen, Konzepte klarer zu erfassen.

Um jedoch auf bisherigen Fortschritten aufzubauen und diese effektiv zu teilen, ist es essentiell, analoge Arbeit ins digitale zu übertragen und dort so (lernen) zu gestalten, dass die Vorteile, die die Grundprinzipien des digitalen bieten, zu ermöglichen und zu nutzen.

Der große Anspruch dieser LVA ist es einen kleinen Schritt in diese Richtung zu machen. 


