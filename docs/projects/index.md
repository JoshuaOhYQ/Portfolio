---
title: Projects
description: Three engineering projects — computer-vision waste sorting, a dementia assistive robot, and a solar-powered irrigation controller.
---

# Projects

Three systems, each taken from a problem statement through component selection,
build and measurement. Every page follows the same structure — problem, role,
stack, approach, features, challenges, results — so they can be read side by side.

<div class="grid cards" markdown>

-   ![Nine validation images with YOLO bounding boxes labelling metal cans, paper cups and plastic bottles](../assets/img/smart-waste-segregation/yolo-validation-predictions.jpg)

    **[Computer Vision Smart Waste Segregation](smart-waste-segregation.md)**

    <span class="jo-card-meta">Vision &amp; firmware · Built &amp; demonstrated</span>

    A conveyor rig that classifies metal, paper and plastic in real time and diverts
    each stream into its own load-cell-weighed bin, reporting fill level to a Blynk
    dashboard and emailing when a bin is full.

    <ul class="jo-tags"><li>YOLOv11</li><li>Python</li><li>ESP32</li><li>OpenCV</li><li>HX711</li><li>Blynk IoT</li></ul>

-   ![Fusion 360 render of PIPER, a domed robot on a three-tier square base](../assets/img/piper/piper-3d-design.jpg)

    **[PIPER — Dementia Assistive Robot](piper.md)**

    <span class="jo-card-meta">System architect &amp; firmware lead · Design stage</span>

    A stationary companion robot for early-to-moderate dementia. mmWave radar
    replaces the camera so nothing is filmed; a local speech pipeline gives it
    conversation and a memory of what the user did today.

    <ul class="jo-tags"><li>ESP32</li><li>Whisper</li><li>Gemini</li><li>Piper TTS</li><li>MQTT</li><li>SQLite</li></ul>

-   ![Blue weatherproof enclosure wired to PVC piping during a water flow-rate test](../assets/img/solar-irrigation/flow-rate-test.jpg)

    **[Solar Irrigation Control](solar-irrigation.md)**

    <span class="jo-card-meta">Project manager &amp; software engineer · Built &amp; tested</span>

    Irrigation water sitting in exposed pipes reaches temperatures that shock roots.
    This controller measures it, holds a solenoid valve shut until it is safe, and
    runs off a solar-charged battery in the field.

    <ul class="jo-tags"><li>ESP8266</li><li>C++</li><li>DS18B20</li><li>Blynk</li><li>ThingSpeak</li><li>Solar / Li-ion</li></ul>

</div>

## At a glance

| Project | My role | Status | Headline result |
| --- | --- | --- | --- |
| [Smart Waste Segregation](smart-waste-segregation.md) | Vision pipeline, ESP32 integration, CAD | Built &amp; demonstrated | 0.984 mAP@0.5; peak F1 0.96 at 0.633 confidence |
| [PIPER](piper.md) | System architect &amp; firmware lead | Design stage, build scheduled | Full design + BOM at RM 234.90, within a RM 500 budget |
| [Solar Irrigation](solar-irrigation.md) | Project manager &amp; software engineer | Built &amp; tested | Built for RM 135.91; 52.5 h idle battery runtime |
