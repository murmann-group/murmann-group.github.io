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
</style>

## 2024

<div class="chip-entry">
    <img src="/assets/images/chips/2024_ECE628/628ChipFullSize.jpg" class="chip-main-image" id="chipClickAndChange" onclick="changeChipImage()">
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
        <div class="chip-description">Design of an Inverter-Based Incremental Delta-Sigma Modulator in IHP's Open-Source 130-nm CMOS Technology</div>
        <div class="chip-names">
            Aftab Uzzaman, Andee Gary, Anthony Gasbarro, Bo Rasse, Brooke Maeda, Chase Urasaki, Denny Landica, Eliya Nakamura, Glan Manio, Jie Zhou, Jonathan Itokazu, Keith Maki, Matt Sahara, Matthew Kouchi, Maxwell Pauly, Osiel (Alex) Montoya, Ryan Taylor, Saige Dacuycuy, Shaun Corpuz, Vikas Kumar, Wannasa Setthapittayakul, Zion McDowell, & Calvin Lee
            <img src="/assets/images/chips/2024_ECE628/628Students.jpg" class="chip-secondary-image">
        </div>
    </div>
</div>