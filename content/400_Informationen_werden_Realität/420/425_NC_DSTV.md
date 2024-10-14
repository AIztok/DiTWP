---
title: 425_NC_DSTV
draft: false
tags:
  - "#FAB"
  - "#CAM"
---

# Allgemein

Das **NC-DSTV**-Format ist ein Standard in der Stahlbauindustrie und dient zur Beschreibung von Bearbeitungsdaten für numerisch gesteuerte Maschinen (NC = Numeric Control). Es wird hauptsächlich verwendet, um Bearbeitungsdaten für Stahlträger und andere Stahlbauteile zu übermitteln. DSTV steht dabei für **Deutscher Stahlbau-Verband**.

[Hier zu DSTV 109 RiLI](https://dstv.deutscherstahlbau.de/fileadmin/user_upload/bauforumstahl.de/wissen/normen-und-richtlinien/bfs-richtlinien/109_Standartbeschreibung_von_Stahlbau-Teilen_8.0.pdf)

![[425_dstv-nc_Bild_1.png]]
Bildquelle [Klietsch](https://klietsch.com/?m=page&action=240827)

# Struktur des Formats

Das NC-DSTV-Format ist eine textbasierte, standardisierte Dateibeschreibung, die verschiedene Bearbeitungsanweisungen enthält. Die Daten werden in einer .nc-Datei gespeichert, welche die Bearbeitungsdetails für Maschinen wie CNC-Fräsen, Sägen, Bohrmaschinen, Brennschneidmaschinen und Stanzen enthält.

Die Datei besteht aus mehreren Blöcken, die jeweils spezifische Informationen zur Bearbeitung eines Stahlteils enthalten. Die häufigsten Abschnitte in einer NC-DSTV-Datei sind:

1. **Kopfzeile**: Enthält grundlegende Informationen wie das Bauteil, den Werkstoff und Maße.
2. **Geometrie-Daten**: Beschreiben die Abmessungen des Bauteils.
3. **Bearbeitungsdaten**: Enthalten Anweisungen zur Bearbeitung, z.B. Bohrungen, Aussparungen, Schnitte, Schweißvorbereitungen.

## Typische Befehle im NC-DSTV-Format

- **BO**: Bohrung
- **SI**: Sägen
- **PU**: Stanzen
- **KO**: Brennschneiden (Konturschneiden)
- **AK**: Ausschnitte für Schweißnähte

# Verwendung

Das NC-DSTV-Format ermöglicht es, dass verschiedene Maschinen (CNC-gesteuert) die Datei einlesen und die Stahlteile gemäß den in der Datei enthaltenen Bearbeitungsanweisungen verarbeiten können. Damit wird die Integration zwischen CAD-Systemen und Maschinensteuerungen in der Fertigung erheblich erleichtert.

# Vorteile des NC-DSTV-Formats:

- **Interoperabilität**: Unabhängig vom Maschinenhersteller wird das Format von vielen Software- und Maschinensystemen unterstützt.
- **Automatisierung**: Reduziert die manuelle Programmierung von Maschinen durch die automatische Übertragung von Daten aus CAD-Systemen.
- **Standardisierung**: Eine einheitliche Beschreibung für die Herstellung von Stahlbauteilen erleichtert die Zusammenarbeit und verringert Fehler.
