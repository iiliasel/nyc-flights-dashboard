# ✈️ NYC Flights + Weather Dashboard (2013)

Ein interaktives **Flexdashboard in R**, das die Beziehung zwischen **Wetterbedingungen**, **Airlines** und **Flugverspätungen** in New York City im Jahr 2013 analysiert.  
Basierend auf dem bekannten Datensatz [`nycflights13`](https://cran.r-project.org/web/packages/nycflights13/index.html).

---

## 📊 Projektinhalt

Das Dashboard besteht aus vier Tabs:

### 1️⃣ Überblick
- Zeigt zentrale **Kennzahlen** (Anzahl der Flüge, Flughäfen)
- Vorschau der bereinigten Datensätze
- Streudiagramm: **Windgeschwindigkeit vs. Ankunftsverspätung**
- Balkendiagramm: **Ø Verspätung nach Monat**

### 2️⃣ Wetter
- Analyse des Wettereinflusses:
  - Ø Verspätung nach **Temperatur**
  - Ø Verspätung nach **Windgeschwindigkeit**
  - Ø Verspätung nach **Sichtweite**
  - **Verspätungsquote nach Regenintensität**
- Erkenntnis: Geringe Sichtweite und starker Regen führen erwartungsgemäß zu mehr Verspätungen.

### 3️⃣ Airlines
- Vergleich der **durchschnittlichen Verspätungen pro Airline**
- Farbkodierung nach Anzahl der Flüge
- Unerwartetes Ergebnis:  
  Airlines mit **mehr Flügen (z. B. Delta, United)** sind **nicht automatisch unpünktlicher**.  
  Langstrecken-Airlines (z. B. *Hawaiian, Alaska*) zeigen sogar **negative Durchschnitts-Delays**,  
  da sie mehr **Zeitpuffer** und **stabilere Strecken** haben.

### 4️⃣ Zeit & Saison
- Ø Verspätung nach **Wochentag**
- Anteil verspäteter Flüge (>15 min) nach **Monat**
- Heatmap: Ø Verspätung nach **Tageszeit & Monat**
- Trendanalyse über das Jahr 2013

---

## 💡 Unerwartete Erkenntnisse

| Beobachtung | Interpretation |
|--------------|----------------|
| ✈️ Kurzstrecken-Airlines (Frontier, Mesa, Envoy) haben höhere Delays | Viele Umläufe pro Tag, kaum Pufferzeiten |
| 🌦️ Geringe Sichtweite → höhere Verspätung | Nebel & Regen zwingen zu längeren Sicherheitsabständen |
| ☀️ Temperatur hat kaum Einfluss | Wetterfaktoren wie Wind & Niederschlag sind entscheidender |
| 🗓️ Samstag = geringste Verspätung | Weniger Geschäftsflüge, geringere Flughafenauslastung |

---

## 🧠 Verwendete Technologien
- **R** + **R Markdown / Flexdashboard**
- **tidyverse** (dplyr, ggplot2)
- **lubridate**
- **nycflights13**
- **janitor**
- **DT (DataTables)**

---

## ⚙️ Lokale Ausführung
Um das Dashboard selbst auszuführen:

```r
# Pakete installieren (nur beim ersten Mal)
install.packages(c("flexdashboard", "tidyverse", "nycflights13", "lubridate", "janitor", "DT"))

# Dashboard starten
rmarkdown::run("Flights_Dashboard.Rmd")

