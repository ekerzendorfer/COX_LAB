# 🧬 COX-Docking-Lab: Selektives Wirkstoff-Design mit KI (Boltz-2)

Interaktive 3D-Lernumgebung für den Chemieunterricht der Sekundarstufe II zum Thema **Enzymhemmung, Schlüssel-Schloss-Prinzip und rationales Wirkstoff-Design (COX-1 vs. COX-2)**.

🔗 **Live-App starten:** [https://ekerzendorfer.github.io/COX_LAB/](https://ekerzendorfer.github.io/COX_LAB/)

---

## 🎯 Didaktisches Konzept

Klassische Schmerzmittel (NSAR wie **Ibuprofen**, **Aspirin** oder **Naproxen**) blockieren sowohl das Entzündungsenzym **COX-2** als auch das Magenschutz-Enzym **COX-1**. Selektive COX-2-Hemmer (**Celecoxib**) nutzen einen minimalen strukturellen Unterschied in der Bindungstasche aus:
* In **COX-1** versperrt die größere Aminosäure **Isoleucin-523** den Zugang zu einer Seitentasche.
* In **COX-2** sitzt an derselben Position das um eine Methylengruppe (`-CH2-`) kleinere **Valin-523**, wodurch sich eine zusätzliche hydrophobe Seitentasche für den sperrigen Sulfonamid-Rest von Celecoxib öffnet.

### Features der Web-App:
* **⚡ Schnell-Flip (`COX-1 ⇄ COX-2`):** Da alle 10 Proteinkomplexe im 3D-Raum exakt überlagert (*superimposed*) wurden, lässt sich bei fixierter Kamera live zwischen COX-1 und COX-2 hin- und herschalten.
* **🏷️ Farbcodierte Hotspots:** Hervorhebung von `Ile-523` / `Val-523` (Türsteher), `Arg-120` (Ionen-Anker), `Ser-530` (Aspirin-Ziel) und `Tyr-385`.
* **🫧 Van-der-Waals-Clash-Ansicht:** Umschaltbare Atomradien zur visuellen Analyse sterischer Hinderungen.
* **🚀 Docking-Animation & KI-Telemetrie:** Einflug-Simulation in die Bindungstasche, Auswertung der Boltz-2-Affinitätswerte und interaktives Laborjournal inkl. Erkenntnis-Check.

---

## 🛠️ Technische Architektur

* **`index.html`**: Komplette Benutzeroberfläche (Tailwind CSS + `3Dmol.js`).
* **`cox_embedded_data.js`**: Enthält alle 10 mit **Boltz-2** berechneten, mittels **BioPython** im Raum ausgerichteten und auf Backbone + 10-Å-Tasche zugeschnittenen Strukturmodelle (Gzip + Base64 komprimiert).