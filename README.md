# AUFGEHTS Project – Simulation Results

This repository provides the outputs of the [AUFGEHTS project](https://www.bmv.de/SharedDocs/DE/Artikel/DG/mfund-projekte/aufgehts.html), which explores a **scalable and automated methodology** for generating and calibrating **mesoscopic traffic simulation models** using **Floating Car Data (FCD)** as the sole input source.

You can use the data available in this repository under [MIT License](https://opensource.org/license/mit).

## Project Overview

The core objective of AUFGEHTS was to develop a **cost-effective and transferable modeling pipeline** that enables:

* Calibration using commercially available FCD
* Seamless **cross-border traffic modeling**

Conventional modeling approaches often break down at administrative or national boundaries due to fragmented data sources. AUFGEHTS aimed to address this gap by relying entirely on FCD, enabling simulation of traffic dynamics across jurisdictions. The **A93/A12 corridor between Bavaria and Tyrol** served as the primary test case—representing a heavily trafficked, cross-border segment of European transport infrastructure.

## Inputs to the model

* **Data Source**: Aggregated edge-based FCD from **HERE Technologies**, providing average speeds of probe vehicles per 5-minute interval. No trajectory-level data is used.
* **Network Generation**: Based on **OpenStreetMap data (Feb 2024)** combined with HERE’s map. Included road types: `motorway`, `motorway_link`, `primary`, `primary_link`.
* **Demand Estimation**: Generated using the AUFGEHTS pipeline, with speed data as the only external input. No sensor counts, OD matrices, or travel surveys were used.

## Model Performance

Model performance was evaluated using **GEH85 statistics**, which compare observed and simulated flows:

* **GEH85 range**: 10–24 over a full-day simulation
* **Benchmark**: FGSV recommends GEH85 < 5 for high-quality calibration

It is thus important to note, given these results, the model should be interpreted as a **coarse approximation** of traffic conditions rather than an operationally valid forecast.

The results can be used in understanding the current capabilities and limitations of speeds-based calibration, exploring the traffic condition of the area. But it is **not suitable** for high-fidelity traffic planning or traffic impact assessments.

## How to Run the Simulation

Ensure [SUMO](https://www.eclipse.dev/sumo/) is installed and accessible via your system path. Then, run:

```bash
sumo-gui -c sumo_withTrips.sumocfg
```

This will generate:

* `edge_data_AFG.xml` – summary data for all vehicles
* `edge_data_AFG_LKW.xml` – summary data for heavy goods vehicles
* `routes_AFG.xml` – generated route definitions

Further outputs can be configured in the `.sumocfg` and `additional.add.xml` files.

## Contact

For any questions, please contact:
Gabriel Tilg 
gabriel.tilg@transcality.com



---



# AUFGEHTS Projekt – Simulationsergebnisse

Dieses Repository enthält die Ergebnisse des [AUFGEHTS-Projekts](https://www.bmv.de/SharedDocs/DE/Artikel/DG/mfund-projekte/aufgehts.html), das ein **skalierbares und automatisiertes Verfahren** zur Erstellung und Kalibrierung **mesoskopischer Verkehrssimulationsmodelle** untersucht –  ausschließlich basierend auf **Floating Car Data (FCD)** als verkehrliche Eingangsdatenquelle.

Sie können die in diesem Repository verfügbaren Daten unter [MIT License](https://opensource.org/license/mit) nutzen.

## Projektüberblick

Das Hauptziel von AUFGEHTS war die Entwicklung eines **kosteneffizienten, übertragbaren Modellierungsverfahrens**, das Folgendes ermöglicht:

* Kalibrierung auf Basis kommerziell verfügbarer FCD
* Nahtlose **grenzüberschreitende Verkehrsmodellierung**

Klassische Modellierungsansätze scheitern oft an administrativen Verwaltungsgrenzen, da Datenquellen fragmentiert vorliegen. AUFGEHTS adressiert diese Problematik, indem ausschließlich FCD verwendet werden – und somit die Modellierung von Verkehrsdynamiken über Zuständigkeitsgrenzen hinweg ermöglicht wird. Als Testgebiet diente der **Korridor A93/A12 zwischen Bayern und Tirol** – ein stark frequentierter, grenzüberschreitender Abschnitt europäischer Verkehrsinfrastruktur.

## Eingaben für das Modell

* **Datenquellen**: Aggregierte, kantenbasierte FCD von **HERE Technologies**, mit durchschnittlichen Fahrzeuggeschwindigkeiten im 5-Minuten-Intervall. Es handelt sich **nicht** um Trajektoriendaten.
* **Netzwerk-Erstellung**: Basierend auf **OpenStreetMap-Daten (Februar 2024)**, kombiniert mit HERE-Kartendaten. Enthaltene Straßentypen: `motorway`, `motorway_link`, `primary`, `primary_link`.
* **Nachfrageerzeugung**: Erzeugt mit dem AUFGEHTS-Verfahren. Als einzige verkehrliche Eingangsgröße dienen die Geschwindigkeitsdaten. Es wurden keine Zähldaten, OD-Matrizen oder Befragungsdaten verwendet.

## Modellgüte

Die Modellgüte wurde anhand der **GEH85-Statistik** bewertet, welche beobachtete und simulierte Verkehrsstärken vergleicht:

* **GEH85-Bereich**: 10–24 über einen gesamten Tagesverlauf
* **Referenzwert**: Die FGSV empfiehlt GEH85 < 5 für hochwertige Kalibrierung

Aufgrund dieser Ergebnisse ist es wichtig zu betonen, dass das Modell als **grob angenäherte Repräsentation** der Verkehrsverhältnisse zu interpretieren ist – nicht als operationell belastbare Verkehrsprognose.

Die Ergebnisse können helfen, die aktuellen Möglichkeiten und Grenzen der Kalibrierung mit Geschwindigkeitsdaten zu bewerten und das Verkehrsverhalten im Gebiet explorativ zu untersuchen. Sie sind jedoch **nicht geeignet** für detaillierte Verkehrsplanungen oder Wirkungsanalysen.

## Simulation ausführen

Stellen Sie sicher, dass [SUMO](https://www.eclipse.dev/sumo/) installiert und im Systempfad verfügbar ist. Führen Sie dann aus:

```bash
sumo-gui -c sumo_withTrips.sumocfg
```

Dies generiert folgende Dateien:

* `edge_data_AFG.xml` – Zusammenfassende Daten für alle Fahrzeuge
* `edge_data_AFG_LKW.xml` – Zusammenfassende Daten für Schwerverkehr
* `routes_AFG.xml` – Generierte Routen

Weitere Ausgaben lassen sich über die Dateien `.sumocfg` und `additional.add.xml` konfigurieren.

## Kontakt

Bei Fragen wenden Sie sich bitte an:
Gabriel Tilg
[gabriel.tilg@transcality.com](mailto:gabriel.tilg@transcality.com)

