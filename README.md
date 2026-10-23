# SmartMotionLighting – Home Assistant Blueprint

> Smart, presence-based lighting automation for Home Assistant. Works with both `light.*` and `switch.*` entities.

---

## 🇩🇿 Deutsch

### Funktionen

- **Zwei Sensortypen wählbar:**
  - **Smart (mmWave/Radar):** Das Licht bleibt an, solange Präsenz erkannt wird. Geht sofort aus, wenn die Präsenz erlischt.
  - **PIR (festes Delay):** Das Licht geht bei Bewegung an und nach einer konfigurierbaren Verzögerung wieder aus (unabhängig von weiterer Bewegung).
- **Licht oder Schalter:** Funktioniert mit `light.*` und `switch.*` Entitäten.
- **Optional: Helligkeitsprüfung:** Wenn ein Luminanzsensor konfiguriert ist, wird das Licht nur bei Bewegung eingeschaltet, wenn der gemessene Wert unter einem Schwellenwert liegt.
- **Manuelle Übersteuerung:** Ein `input_boolean` deaktiviert die Automatisierung, wenn es auf `on` steht (z. B. für manuelles Licht).
- **Wiedereinschalten (Smart-Modus):** Wird das Licht manuell ausgeschaltet, während noch Bewegung erkannt wird, schaltet es sich nach einer konfigurierbaren Verzögerung wieder ein.

### Voraussetzungen

- Home Assistant (aktuelle Version)
- Ein `binary_sensor` für Präsenz/Bewegung
- Eine `light` oder `switch` Entität für das Licht
- Ein `input_boolean` für die manuelle Übersteuerung
- Optional: ein `sensor` für Helligkeit (Lux)

### Installation

1. Kopiere die Datei `SmartMotionLighting.yaml` in deinen Home Assistant `config/blueprints/automation/` Ordner.
2. Starte Home Assistant neu.
3. Gehe zu **Einstellungen → Automatisierungen & Szenen → Blueprints**.
4. Wähle **SmartMotionLighting** und erstelle eine neue Automatisierung.
5. Konfiguriere die Eingabefelder nach deinem Setup.

### Eingabefelder

| Feld | Typ | Beschreibung | Standard |
|------|-----|--------------|----------|
| Sensor type | Select | `smart` oder `pir` | `smart` |
| Presence sensor | Entity (`binary_sensor`) | Präsenz-/Bewegungssensor | – |
| Light / Switch | Entity (`light`, `switch`) | Zu schaltende Entität | – |
| Manual override | Entity (`input_boolean`) | Deaktiviert Automation bei `on` | – |
| Luminance sensor (optional) | Entity (`sensor`) | Helligkeitssensor | – |
| Luminance threshold | Number | Schwellwert in Lux | 25 |
| Smart retrigger delay | Number | Verzögerung vor Wiedereinschalten (Smart) | 1 Sekunde |
| PIR off delay | Number | Verzögerung vor Ausschalten (PIR) | 15 Sekunden |

### Trace-Fehler ignorieren

Im Automatisierungs-Trace kann unter Umständen ein Fehler wie *"Cannot read properties of undefined (reading 'includes')"* erscheinen. Das ist ein reines Home Assistant UI-Anzeigeproblem bei Blueprint-Triggern und hat keinen Einfluss auf die Funktion der Automatisierung.

---

## 🇬🇧 English

### Features

- **Two sensor types:**
  - **Smart (mmWave/radar):** Light stays on while presence is detected. Turns off immediately when presence clears.
  - **PIR (fixed delay):** Light turns on on motion and off after a fixed delay, regardless of continued presence.
- **Light or switch:** Works with both `light.*` and `switch.*` entities.
- **Optional luminance check:** If a luminance sensor is configured, the light only turns on when motion is detected and illuminance is below the threshold.
- **Manual override:** An `input_boolean` disables the automation when `on` (e.g. for manual light control).
- **Re-arm (Smart mode):** If the light is manually turned off while motion is still present, it turns back on after a configurable delay.

### Requirements

- Home Assistant (recent version)
- A `binary_sensor` for presence/motion
- A `light` or `switch` entity
- An `input_boolean` for manual override
- Optional: a `sensor` for illuminance (lux)

### Installation

1. Copy `SmartMotionLighting.yaml` to your Home Assistant `config/blueprints/automation/` folder.
2. Restart Home Assistant.
3. Go to **Settings → Automations & Scenes → Blueprints**.
4. Select **SmartMotionLighting** and create a new automation.
5. Configure the input fields for your setup.

### Input Fields

| Field | Type | Description | Default |
|-------|------|-------------|---------|
| Sensor type | Select | `smart` or `pir` | `smart` |
| Presence sensor | Entity (`binary_sensor`) | Presence/motion sensor | – |
| Light / Switch | Entity (`light`, `switch`) | Entity to switch | – |
| Manual override | Entity (`input_boolean`) | Disables automation when `on` | – |
| Luminance sensor (optional) | Entity (`sensor`) | Illuminance sensor | – |
| Luminance threshold | Number | Threshold in lux | 25 |
| Smart retrigger delay | Number | Delay before re-arm (Smart mode) | 1 second |
| PIR off delay | Number | Delay before turn off (PIR mode) | 15 seconds |

### Trace error

A trace error like *"Cannot read properties of undefined (reading 'includes')"* may appear. This is a Home Assistant UI display issue with blueprint triggers and does not affect automation functionality.

---

## 🚀 Add to Home Assistant

[![Open your Home Assistant instance and show the blueprint import dialog](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://raw.githubusercontent.com/USERNAME/REPO/main/SmartMotionLighting.yaml)

> Replace `USERNAME/REPO` with your GitHub username and repository name.

---

## 📄 License

MIT License
