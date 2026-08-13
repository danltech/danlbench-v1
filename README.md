# ⚡ DanlBench V1

**DanlBench V1** ist ein plattformübergreifender CPU‑Benchmark für Browser, der speziell für **Stabilität** und **Vergleichbarkeit** über eine breite Gerätepalette entwickelt wurde – vom alten Android‑2‑Smartphone bis zum modernen Desktop‑PC.

> Live‑Demo: [https://danltech.github.io/danlbench-v1/](https://danltech.github.io/danlbench-v1/)

---

## 🚀 Funktionen

- **Fünf CPU‑Teiltests**:  
  Integer‑Arithmetik, Gleitkomma‑Berechnungen (sin/cos), Primzahlsieb (Sieve), Matrixmultiplikation (20×20) und Quicksort (500 Elemente).

- **Adaptive Laufzeit**:  
  Jeder Test wird automatisch so skaliert, dass er etwa **1 Sekunde** benötigt – unabhängig von der Gerätegeschwindigkeit. Das liefert auch auf extrem langsamen oder schnellen CPUs Aussagekräftige Werte.

- **Robuste Messung**:  
  Drei Durchläufe pro Test, **Median** als Endergebnis – Ausreißer durch Garbage‑Collection oder Systemlast werden minimiert.

- **Gesamtscore**:  
  Geometrischer Mittelwert der fünf Teilergebnisse → ein einziger, vergleichbarer Wert.

- **Ranking‑Einordnung**:  
  Zeigt **maximal 5 Einträge** (2 unterhalb, dein Gerät, 2 oberhalb) aus einer manuell gepflegten `ranking.json` an – übersichtlich und ohne Datenmüll.

- **Kompatibilität**:  
  Reines ES3‑JavaScript, kein CSS‑Flexbox/Grid, keine externen Abhängigkeiten. **Läuft auf jedem Browser, der HTML5 und XMLHttpRequest unterstützt** – das schließt Android 2 (API 8) mit ein.

---

## 📂 Projektstruktur

```
danlbench-v1/
├── index.html         # Die komplette Web‑App
├── ranking.json       # Deine manuelle Geräte‑Liste mit Scores
└── README.md          # Diese Datei
```

---

## 🧪 Benchmark‑Ablauf

1. Der Benutzer klickt auf **„Benchmark starten“**.
2. Die `ranking.json` wird geladen (falls vorhanden).
3. Nacheinander werden die fünf Tests ausgeführt – jeder mit drei Durchläufen.
4. Nach etwa 5–10 Sekunden (abhängig von der Gerätegeschwindigkeit) erscheint das Ergebnis:
   - **Gesamtscore** (größer = besser)
   - **Einordnung** in deinem Ranking (zwischen welchen zwei Geräten)
   - **Detailtabelle** mit den ops/sec pro Test

---

## 🗂️ Ranking‑Daten (ranking.json)

Die Datei `ranking.json` ist ein einfaches JSON‑Array mit Objekten:

```json
[
  { "name": "Raspberry Pi 1", "score": 120 },
  { "name": "Samsung Galaxy S2", "score": 450 },
  { "name": "Intel Core i5-4460", "score": 2100 },
  { "name": "AMD Ryzen 5 3600", "score": 3800 }
]
```

- **name**: Freier Text (Gerätename, Modell, etc.)
- **score**: Der zuvor gemessene DanlBench‑Score

Du kannst die Liste beliebig erweitern – der Benchmark sortiert automatisch aufsteigend. Die Anzeige zeigt nur die 2 langsameren und 2 schnelleren Geräte relativ zu deinem aktuellen Score. Ich empfehle die Erweiterung über ein Issue der öffentlichen Liste.

---

## 📜 Lizenz

**DanlBench V1** steht unter der **MIT‑Lizenz** – du darfst den Code frei nutzen, verändern und weitergeben, solange der Urhebervermerk erhalten bleibt.

```
MIT License

Copyright (c) 2026 DanlTech

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

---

## 🤝 Mitwirken

Du hast Verbesserungsvorschläge, Testergebnisse anderer Hardware oder findest einen Fehler?  
Öffne gerne ein **Issue** oder reiche einen **Pull Request** ein – alle Beiträge sind willkommen!

---

## 📅 Version & Status

**DanlBench V1** (2026)  
Stabil, getestet auf:
- DanlTechOS (Chromium), Android 4+, iOS, Windows (Chrome, Firefox, Edge), macOS (Safari, Chrome)

---

Viel Erfolg beim Benchmarken!  
– Dein DanlTech‑Team
