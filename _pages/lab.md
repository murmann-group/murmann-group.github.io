---
layout: splash
title: Lab Equipment
permalink: /lab/
---

<!-- ═══════════════════════════════════════════════════
     LAB EQUIPMENT — Card Grid

     A responsive grid of cards. Each card has an image,
     a title, a short model line, and a description.
     Cards reflow automatically to fit the window.

     TEMPLATE (copy, paste, fill in):

     <div class="equip-card">
         <img src="/assets/images/lab/FILENAME.png" alt="...">
         <div class="equip-body">
             <div class="equip-title">Manufacturer Model</div>
             <div class="equip-type">Category</div>
             <p>One-sentence description.</p>
         </div>
     </div>
     ═══════════════════════════════════════════════════ -->

<style>
.equip-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
    gap: 1.5em;
    margin-top: 2em;
}
.equip-card {
    display: flex;
    flex-direction: column;
    border-radius: 10px;
    overflow: hidden;
    background: #fff;
    box-shadow: 0 2px 12px rgba(0,0,0,0.12);
}
.equip-card img {
    width: 100%;
    height: 200px;
    object-fit: contain;
    background: #f5f5f5;
    display: block;
    padding: 0.8em;
    box-sizing: border-box;
}
.equip-body {
    padding: 1em 1.1em 1.3em;
    border-top: 1px solid #eee;
}
.equip-title {
    font-weight: bold;
    font-size: 1.1em;
    margin-bottom: 0.15em;
}
.equip-type {
    font-size: 0.75em;
    text-transform: uppercase;
    letter-spacing: 0.06em;
    color: #b02a2a;
    margin-bottom: 0.6em;
}
.equip-body p {
    font-size: 0.9em;
    color: #444;
    margin: 0;
}
</style>

## Lab Equipment

<div class="equip-grid">

    <div class="equip-card">
        <img src="/assets/images/lab/keysight-dsox1204g.png" alt="Keysight DSOX1204G">
        <div class="equip-body">
            <div class="equip-title">Keysight DSOX1204G</div>
            <div class="equip-type">Oscilloscope</div>
            <p>4-channel oscilloscope with an integrated waveform generator.</p>
        </div>
    </div>

    <div class="equip-card">
        <img src="/assets/images/lab/teledyne-t3dso-hd.png" alt="Teledyne LeCroy T3DSO-HD">
        <div class="equip-body">
            <div class="equip-title">Teledyne LeCroy T3DSO-HD</div>
            <div class="equip-type">Oscilloscope</div>
            <p>12-bit high-definition oscilloscope.</p>
        </div>
    </div>
    
    <div class="equip-card">
        <img src="/assets/images/lab/stanford-research-systems-ds360.png" alt="Stanford Research Systems DS360">
        <div class="equip-body">
            <div class="equip-title">Stanford Research Systems DS360</div>
            <div class="equip-type">Function Generator</div>
            <p>Ultra-low distortion generator (DC – 200 kHz) for high-fidelity analog test signals.</p>
        </div>
    </div>

    <div class="equip-card">
        <img src="/assets/images/lab/siglent-sva-1075x.png" alt="Siglent SVA1075X">
        <div class="equip-body">
            <div class="equip-title">Siglent SVA1075X</div>
            <div class="equip-type">Spectrum / Network Analyzer</div>
            <p>Combined spectrum and vector network analyzer covering 9 kHz – 7.5 GHz.</p>
        </div>
    </div>

    <div class="equip-card">
        <img src="/assets/images/lab/rohde-schwarz-smc100a.png" alt="Rohde &amp; Schwarz SMC100A">
        <div class="equip-body">
            <div class="equip-title">Rohde &amp; Schwarz SMC100A</div>
            <div class="equip-type">RF Signal Generator</div>
            <p>Analog RF signal generator spanning 9 kHz – 3.2 GHz.</p>
        </div>
    </div>

    <div class="equip-card">
        <img src="/assets/images/lab/rohde-schwarz-smcv100b.png" alt="Rohde &amp; Schwarz SMCV100B">
        <div class="equip-body">
            <div class="equip-title">Rohde &amp; Schwarz SMCV100B</div>
            <div class="equip-type">Vector Signal Generator</div>
            <p>Vector signal generator for modulated and multi-standard communication signals.</p>
        </div>
    </div>

    <div class="equip-card">
        <img src="/assets/images/lab/keysight-b2901bl.png" alt="Keysight B2901BL">
        <div class="equip-body">
            <div class="equip-title">Keysight B2901BL</div>
            <div class="equip-type">Source / Measure Unit</div>
            <p>Precision SMU for sourcing and measurement of voltage and current.</p>
        </div>
    </div>

    <div class="equip-card">
        <img src="/assets/images/lab/keysight-e36312a.png" alt="Keysight E36312A">
        <div class="equip-body">
            <div class="equip-title">Keysight E36312A</div>
            <div class="equip-type">DC Power Supply</div>
            <p>(2x) Triple-output programmable DC power supply with GPIB add-on.</p>
        </div>
    </div>

    <div class="equip-card">
        <img src="/assets/images/lab/keysight-34450a.png" alt="Keysight 34450A">
        <div class="equip-body">
            <div class="equip-title">Keysight 34450A</div>
            <div class="equip-type">Digital Multimeter</div>
            <p>5½-digit bench multimeter with a dual-display OLED readout.</p>
        </div>
    </div>

    <div class="equip-card">
        <img src="/assets/images/lab/other1.png" alt="Bench supplies and multimeters">
        <div class="equip-body">
            <div class="equip-title">Bench Supplies &amp; Multimeters</div>
            <div class="equip-type">Miscellaneous</div>
            <p>Older general-purpose DC power supplies and digital multimeters.</p>
        </div>
    </div>

    <div class="equip-card">
        <img src="/assets/images/lab/computer.png" alt="Measurement workstation">
        <div class="equip-body">
            <div class="equip-title">Bench PC</div>
            <div class="equip-type">Automation</div>
            <p>Windows 11 with Intel i7-8700K, 16 GB RAM, 500 GB SSD, and USB-GPIB module.</p>
        </div>
    </div>

    <div class="equip-card">
        <img src="/assets/images/lab/rework_station.png" alt="Soldering and rework bench">
        <div class="equip-body">
            <div class="equip-title">Soldering &amp; Rework Bench</div>
            <div class="equip-type">Assembly &amp; Rework</div>
            <p>Hot-air rework station, microscope, and surface mount components for board assembly.</p>
        </div>
    </div>

</div>
