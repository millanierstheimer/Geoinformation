# Geoinformationen | WiSe 2026



## EP. 01 | UE 1 – Einführung in QGIS: Soziale Stadtentwicklung

<p align="center">
<img width="3507" height="2480" alt="soz stadtentwicklung" src="https://github.com/user-attachments/assets/70154a12-31c3-4e08-bb7d-e1c6b1c9b997" />
</p>

### Umsetzung der Methode

Grundlage sind die Geometrien der Berliner Lebensweltlich orientierten Räume (**LOR-Planungsräume**) sowie die Sachdaten aus dem **Monitoring Soziale Stadtentwicklung (MSS) 2025** der Senatsverwaltung für Stadtentwicklung, Bauen und Wohnen. In **QGIS** wurden die Tabellendaten über den gemeinsamen Raumschlüssel mit den Vektorgeometrien verknüpft (Attribut-Join).

Anschließend erfolgte eine kategorisierte Symbolisierung der Planungsräume anhand der vier **Statusklassen** (*hoch*, *mittel*, *niedrig* und *sehr niedrig*). Im Layout von **QGIS** wurde die Berlinkarte im Maßstab **1 : 300.000** vor einem dunklen Hintergrund aufbereitet und um kartografische Basiselemente wie Titel, Legende, Maßstabsleiste und Quellenangaben ergänzt.

Durch die abgestufte Farbwahl treten räumliche Disparitäten sowie sozialräumliche Schwerpunkte innerhalb des Berliner Stadtgebiets auf Ebene der Planungsräume deutlich hervor.

## EP. 01 | UE 2 | Datenklassifikation

<p align="center">
  <img width="842" height="600" alt="Bevölkerungsverteilung_Berlin2019" src="https://github.com/user-attachments/assets/caa549c9-7f41-4225-96fb-fc7a943a4279" />
</p>

### Umsetzung der Methode

Grundlage sind die Einwohnerdaten des **Amtes für Statistik Berlin-Brandenburg (Stand 2019)**, die in **QGIS** über den gemeinsamen Raumschlüssel mit den Geometrien der Berliner Lebensweltlich orientierten Räume (**LOR-Planungsräume**) verknüpft wurden. 

Im Layout von **QGIS** wurden vier Choroplethenkarten im Maßstab **1 : 450.000** gegenübergestellt, um den Einfluss unterschiedlicher Bezugsgrößen und Klassifizierungsmethoden auf die räumliche Wahrnehmung zu untersuchen. Verglichen werden die **absolute Bevölkerung** (klassifiziert nach *Natürlichen Unterbrechungen / Jenks*) sowie die **Bevölkerungsdichte (Einwohner/km²)** nach **Jenks**, **Quantilen** und **gleichen Intervallen** in einer fünfstufigen blauen Farbskala.

Durch die direkte Gegenüberstellung wird deutlich, wie stark die Wahl des Indikators (absolut vs. relativ) und der Klassenbildung die Interpretation scheinbar objektiver statistischer Daten beeinflusst.

## EP. 02 | UE 3 & UE4 | Georeferenzieren & Digitalisieren | Kirche

<p align="center">
  <img width="992" height="720" alt="berlin_1833_Kirche" src="https://github.com/user-attachments/assets/bb64b5e3-a0a1-4d3e-92dd-4e1c0f4d41b1" />

</p>

### Umsetzung der Methode

Grundlage ist ein historischer Stadtplan von **Berlin aus dem Jahr 1833**, der in **QGIS** anhand bekannter Passpunkte georeferenziert wurde. Anschließend erfolgte die Digitalisierung von zwei Vektorebenen:

1. Die historische Ausdehnung Berlins entlang der eingezeichneten Stadtmauer wurde als Polygon digitalisiert und die zugehörige Fläche über den Feldrechner in einer neuen Spalte der Attributtabelle berechnet.
2.  Parallel dazu entstand für die Objektkategorie *Kirche* ein sechsteiliges Datenbankschema, auf dessen Basis fünf Kirchenstandorte als Punktgeometrien erfasst und attributiert wurden.

Durch das Georeferenzieren und Digitalisieren lassen sich historische Stadtgrenzen räumlich auswerten und punktuelle Landmarken wie Kirchen systematisch in einem GIS erfassen.

## EP. 03 | Standortanalyse


<p align="center">
  <img width="992" height="720" alt="potenzielle_fussballstandorte_berlin" src="https://github.com/user-attachments/assets/bfe58112-0145-4726-a32f-26c793724bd1" />
</p>

### Umsetzung der Methode

Ziel der Analyse war es, anhand frei verfügbarer Geodaten geeignete Standorte für den Neubau von Fußballplätzen innerhalb der Berliner Bezirke zu ermitteln. Als Grundlage dienten Vektordaten von **OpenStreetMap / Geofabrik** (`gis_osm_landuse_a_free_1`, `gis_osm_water_a_free_1`, `gis_osm_roads_free_1`, `gis_osm_transport_free_1`) sowie der Datensatz zu den **Berliner Naturschutzgebieten** (`Berlin_NSG.shp`).

Ausgangspunkt waren unbebaute Grün- und Wiesenflächen (`grass`, `meadow`) mit einer Mindestgröße von **1 Hektar**, die über Puffer-, Verschneidungs- und Filteroperationen mit sieben Standortkriterien abgeglichen wurden: ein Abstand von **500 bis 1.000 m** zu Wohngebieten (`residential`), mindestens **500 m** Abstand zu Naturschutzgebieten, der Ausschluss von Wasserflächen sowie eine maximale Entfernung von jeweils **500 m** zu Hauptverkehrsstraßen (`motorway`, `trunk`, `primary`, `secondary`) und ÖPNV-Haltestellen (`bus_stop`, `railway_halt`, `railway_station`, `tram_stop`).

Durch die Verknüpfung aller Kriterien ließen sich in Berlin **12 potenzielle Standorte** identifizieren, die in der Karte vor den Berliner Bezirksgrenzen makiert sind.


