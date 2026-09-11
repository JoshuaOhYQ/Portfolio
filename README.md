<div align="center">

# Joshua Oh — Engineering Portfolio

**Electronic &amp; Electrical Engineering · Sunway University, Malaysia**

Embedded systems, computer vision and IoT — taken from problem statement to working hardware.

[![Live site](https://img.shields.io/badge/Live_site-joshuaohyq.github.io%2FPortfolio-0f4c52?style=flat-square)](https://joshuaohyq.github.io/Portfolio/)
[![Deploy](https://github.com/JoshuaOhYQ/Portfolio/actions/workflows/deploy.yml/badge.svg)](https://github.com/JoshuaOhYQ/Portfolio/actions/workflows/deploy.yml)
[![Built with Material for MkDocs](https://img.shields.io/badge/built_with-Material_for_MkDocs-526cfe?style=flat-square&logo=materialformkdocs&logoColor=white)](https://squidfunk.github.io/mkdocs-material/)

### 👉 **[View the portfolio →](https://joshuaohyq.github.io/Portfolio/)**

</div>

---

## About

I'm Joshua Oh (Oh Yu Qiao), an Electronic and Electrical Engineering undergraduate at
Sunway University. My work sits where software meets hardware — a model or a piece of
logic that has to produce a physical result: a servo that moves, a valve that closes,
an alert that reaches someone in time.

I take projects down the full stack: trained models, C++ firmware, Python backends,
circuit design, CAD and 3D printing, and the IoT dashboards that make a system
observable once it's running. I'm currently looking for **internship and graduate
roles** in embedded systems, IoT or applied computer vision.

This repository holds both the source of my portfolio site and the original technical
reports behind each project.

## Projects

### 🗑️ [Computer Vision Smart Waste Segregation](https://joshuaohyq.github.io/Portfolio/projects/smart-waste-segregation/)

A conveyor rig that classifies waste as metal, paper or plastic with a custom-trained
YOLO model and drives servo diverter arms to drop each item into its own
load-cell-weighed bin — logging running totals to a Blynk dashboard and emailing when
a bin fills up.

The detail I like most is the *weight-confirmation loop*: the ESP32 doesn't assume the
item landed, it polls a load cell until the weight delta crosses a per-material
threshold. The sort is confirmed by physics, not by a timer.

**Result:** 0.984 mAP@0.5 across all three classes; peak F1 of 0.96 at 0.633 confidence.
<br>**Stack:** YOLOv11s · Ultralytics · Python · OpenCV · ESP32 · HX711 load cells · Blynk IoT · SOLIDWORKS
<br>**Status:** Built, trained and demonstrated end to end · team of 6

---

### 🤖 [PIPER — Dementia Assistive Robot](https://joshuaohyq.github.io/Portfolio/projects/piper/)

A stationary in-home companion for people living with early-to-moderate dementia.
PIPER detects falls with **mmWave radar rather than a camera**, holds a conversation
through a local Whisper → Gemini → Piper TTS pipeline, and keeps a diary of the user's
day so it can answer *"have I taken my pills?"* from the record rather than from the
model's imagination.

A survey of five existing assistive robots found none combining voice interaction,
memory, fall detection, smart-home control and camera-free privacy. That gap is the
project.

**Design targets:** &lt;3 s voice response · caregiver alerted within 10 s · ≥85% command accuracy
<br>**Stack:** ESP32 · Whisper · Google Gemini · Piper TTS · Flask · SQLite · MQTT · Telegram Bot API · LD2450 radar · Fusion 360
<br>**Status:** ⚠️ Design stage — architecture, circuit, power budget, CAD and BOM complete; build runs to December 2026 · team of 4

---

### 🌱 [Solar Irrigation Control](https://joshuaohyq.github.io/Portfolio/projects/solar-irrigation/)

Irrigation water sitting in exposed Malaysian pipelines regularly exceeds 50 °C, and
releasing it onto crops causes thermal shock and root burn. This controller measures
water temperature continuously, holds a solenoid valve shut until it's safe, and runs
off a solar-charged battery in the field.

The most useful finding was a negative one: measured under direct sun, the panel
produced **4.68 mW** against the **12.765 W** needed to open the valve — a shortfall of
2,728×. Rather than quietly drop "solar" from the title, the panel was redefined as a
trickle charger for the battery pack.

**Result:** built for RM 135.91 against a RM 150 budget · 52.5 h idle runtime · no leakage under pressure test
<br>**Stack:** ESP8266 NodeMCU · C++ · DS18B20 · relay-driven solenoid · Blynk · ThingSpeak · solar/Li-ion · ABS enclosure
<br>**Status:** Built, assembled and bench-tested · **my role: project manager &amp; software engineer**, leading a team of 5

## Tech I work with

| | |
| --- | --- |
| **Languages** | Python · C++ (Arduino) · MATLAB |
| **ML &amp; vision** | Ultralytics YOLO · OpenCV · Whisper · Gemini API · Piper TTS |
| **Embedded** | ESP32 · ESP8266 · I²S audio · HX711 · mmWave radar · DS18B20 · L298N · UART |
| **Connectivity** | HTTP/REST · MQTT · SMTP · Flask · SQLite · Blynk · ThingSpeak · Telegram Bot API |
| **Mechanical &amp; PCB** | SOLIDWORKS · Fusion 360 · EasyEDA · FDM printing (PLA/ABS) |
| **Practice** | CDIO · weighted decision matrices · WBS · Gantt &amp; critical path · BOM and whole-life costing |

## About the write-ups

Every figure, metric and cost on the site comes from the project reports themselves —
the YOLO curves, schematics, CAD renders and bench measurements are the original
artefacts, not recreations. Where a project is still in progress the page says so
rather than implying a finished result, and the write-ups deliberately include the
things that went wrong: the class imbalance behind a strong mAP figure, the solar
panel that couldn't do its job, and the components destroyed learning something.

The three source reports are kept in the repository root for reference.

## Repository layout

```text
mkdocs.yml                       site config, nav, theme and palette
docs/
  index.md                       home — hero, featured cards, skills
  about.md                       bio, skills, education
  contact.md                     email, GitHub, resume
  projects/
    index.md                     project grid + comparison table
    smart-waste-segregation.md
    piper.md
    solar-irrigation.md
  assets/img/<project>/          figures extracted from the source reports
  assets/img/site/               logo and favicon
  stylesheets/extra.css          palette, hero, cards, tech pills
.github/workflows/deploy.yml     build + deploy to GitHub Pages
*.pdf                            original technical reports
```

## Building locally

```bash
pip install -r requirements.txt
mkdocs serve          # http://127.0.0.1:8000/Portfolio/
mkdocs build --strict # what CI runs; fails on broken links
```

## Deployment

Every push to `main` runs [`deploy.yml`](.github/workflows/deploy.yml), which builds
with `mkdocs build --strict` and publishes through the native GitHub Pages Actions
deployment. There is no `gh-pages` branch — the artifact is uploaded directly.

> [!IMPORTANT]
> One-time setup, browser only: go to **Settings → Pages** and set **Source** to
> **GitHub Actions**. Until that's done the workflow will build successfully but the
> deploy step will fail.

## Contact

- **Email** — [yuqiao.oh@gmail.com](mailto:yuqiao.oh@gmail.com)
- **GitHub** — [@JoshuaOhYQ](https://github.com/JoshuaOhYQ)

Full technical reports available on request — each runs 35–70 pages with the complete
decision matrices, firmware listings, circuit diagrams and test data.
