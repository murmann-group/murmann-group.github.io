---
layout: splash
title: Chip Gallery
permalink: /gallery/
---

<style>
.chip-entry {
    display: flex;
    align-items: center;
    margin-bottom: 3em;
    gap: 2em;
}

.chip-main-image {
    flex-shrink: 0;
    border-radius: 5%;
    width: 400px;
    height: 400px;
}

.chip-image-container {
    flex-shrink: 0;
    display: flex;
    flex-direction: column;
    align-items: center;
}

.chip-caption {
    font-size: 0.9em;
    font-style: italic;
    color: #666;
    text-align: center;
    margin-top: 0.5em;
    max-width: 400px;
}

.chip-content-section {
    flex: 1;
    min-width: 0;
}

.chip-title {
    font-weight: bold;
    font-size: 1.2em;
    margin-bottom: 1em;
}

.chip-description {
    font-weight: bold;
    font-size: 1.2em;
    margin-bottom: 1em;
}

.chip-names {
    font-size: 0.8em;
    margin-bottom: 1em;
}

.chip-secondary-image {
    border-radius: 5%;
    width: auto;
    max-height: 200px;
    float: left;
    margin-left: 1em;
    margin-top: 0.5em;
    clear: both;
}

/* Clear floats after each entry */
.chip-entry::after {
    content: "";
    display: table;
    clear: both;
}

.four-chip-gallery {
    margin-bottom: 3em;
}

.four-chip-header {
    margin-bottom: 2em;
}

.four-chip-images {
    display: flex;
    gap: 1em;
    justify-content: space-between;
}

.four-chip-images img {
    width: calc(25% - 0.75em);
    height: auto;
    border-radius: 5%;
}

.class-photo-row {
    display: flex;
    align-items: center;
    gap: 2em;
    margin-bottom: 2em;
}

.class-photo {
    flex-shrink: 0;
    width: 50%;
    height: auto;
    border-radius: 1em;
}

@media (max-width: 700px) {
    .class-photo-row {
        flex-direction: column;
        align-items: stretch;
    }
    .class-photo {
        width: 100%;
    }
}

.class-photo-row .chip-names {
    flex: 1;
    min-width: 0;
    margin-bottom: 0;
}

.placeholder-box {
    display: flex;
    align-items: center;
    justify-content: center;
    border: 2px dashed #aaa;
    border-radius: 5%;
    color: #888;
    font-size: 0.9em;
    text-align: center;
    background: #f5f5f5;
}

.class-photo-placeholder {
    flex-shrink: 0;
    width: 400px;
    height: 250px;
}

.chip-figure {
    width: calc(25% - 0.75em);
}

.chip-figure .placeholder-box {
    width: 100%;
    aspect-ratio: 1 / 1;
}

.chip-figure img {
    width: 100%;
    height: auto;
    border-radius: 5%;
}

.chip-figure .chip-caption {
    max-width: none;
}

</style>

## 2026

<div class="four-chip-gallery">
    <div class="four-chip-header">
        <div class="chip-title">ECE 628 - Spring 2026</div>
        <div class="chip-description">CEMiD Supported Class Projects in TSMC 180nm CMOS</div>
    </div>
    <div class="class-photo-row">
        <img src="/assets/images/chips/2026_ECE628/sp26_students_crop.jpg" class="class-photo">
        <div class="chip-names">
            Aera Jung, John Graham, Nicholas Boo, Milan Bukovics, Tristan Hall, Andrea Murillo, Ashtar Aggelopoulos, Guanchen Wu, Mandy Liao, Jharrell Sim, Yeunggyun Kwon, Cristian Milanes, Gordon Sheen, Calvin Lee, & Boris Murmann
        </div>
    </div>
    <div class="four-chip-images">
        <div class="chip-figure">
            <img src="/assets/images/chips/2026_ECE628/sp26_26196.jpg">
            <div class="chip-caption">CMOS Image Sensor and Analog Readout</div>
        </div>
        <div class="chip-figure">
            <img src="/assets/images/chips/2026_ECE628/sp26_26197.jpg">
            <div class="chip-caption">Potentiostat</div>
        </div>
        <div class="chip-figure">
            <img src="/assets/images/chips/2026_ECE628/sp26_26198.jpg">
            <div class="chip-caption">Class-D Audio Driver</div>
        </div>
        <div class="chip-figure">
            <img src="/assets/images/chips/2026_ECE628/sp26_26199.jpg">
            <div class="chip-caption">TIA for Heart-Rate and Pulse Oximeter Monitoring</div>
        </div>
    </div>
</div>

## 2025

<div class="four-chip-gallery">
    <div class="four-chip-header">
        <div class="chip-title">CEMiD Supported Test Chips - Spring 2025</div>
        <div class="chip-description">SRAM and ADC Designs in TSMC 180 nm CMOS</div>
        <div class="chip-names">
            Andrea Murillo, Jaeden Chang, Calvin Lee, & Boris Murmann
        </div>
    </div>
    <div class="four-chip-images">
        <img src="/assets/images/chips/2025_Spring/sp25_25148.jpg">
        <img src="/assets/images/chips/2025_Spring/sp25_25149.jpg">
        <img src="/assets/images/chips/2025_Spring/sp25_25150.jpg">
        <img src="/assets/images/chips/2025_Spring/sp25_25151.jpg">
    </div>
</div>

## 2024

<div class="chip-entry">
    <div class="chip-image-container">
        <img src="/assets/images/chips/2024_ECE628/628ChipFullSize.jpg" class="chip-main-image" id="chipClickAndChange" onclick="changeChipImage()">
        <div class="chip-caption" id="chipCaption">Click me!</div>
    </div>
    <script language="javascript">
        var chipImgTag = 0;
        function changeChipImage() {
            chipImgTag = (++chipImgTag % 3);
            var imageName;
            if (chipImgTag === 0) {
                imageName = "628ChipFullSize";
            } else if (chipImgTag === 1) {
                imageName = "628Chip";
            } else {
                imageName = "628Layout";
            }
            document.getElementById("chipClickAndChange").src = "/assets/images/chips/2024_ECE628/" + imageName + ".jpg";
        }
    </script>
    
    <div class="chip-content-section">
        <div class="chip-title">ECE 628 - Spring 2024</div>
        <div class="chip-description">Design of an Inverter-Based Incremental Delta-Sigma Modulator in IHP's Open-Source 130 nm CMOS Technology</div>
        <div class="chip-names">
            Aftab Uzzaman, Andee Gary, Anthony Gasbarro, Bo Rasse, Brooke Maeda, Chase Urasaki, Denny Landica, Eliya Nakamura, Glan Manio, Jie Zhou, Jonathan Itokazu, Keith Maki, Matt Sahara, Matthew Kouchi, Maxwell Pauly, Osiel (Alex) Montoya, Ryan Taylor, Saige Dacuycuy, Shaun Corpuz, Vikas Kumar, Wannasa Setthapittayakul, Zion McDowell, & Calvin Lee
            <img src="/assets/images/chips/2024_ECE628/628Students.jpg" class="chip-secondary-image">
        </div>
    </div>
</div>