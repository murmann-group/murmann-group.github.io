---
layout: splash
title: Photos
permalink: /photos/
---

<style>
/* ── Slideshow ── */
.slideshow-container {
    position: relative;
    width: 100%;
    max-width: 700px;
    margin: 2em auto 3em;
    aspect-ratio: 4 / 3;
    overflow: hidden;
    border-radius: 8px;
    background: #111;
    box-shadow: 0 4px 20px rgba(0,0,0,0.25);
}
.slideshow-container img {
    position: absolute;
    inset: 0;
    width: 100%;
    height: 100%;
    object-fit: contain;
    opacity: 0;
    transition: opacity 1.2s ease-in-out;
}
.slideshow-container img.active {
    opacity: 1;
}
.slideshow-caption {
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    background: linear-gradient(180deg, transparent, rgba(0,0,0,0.7));
    color: white;
    padding: 1em 0.8em 0.8em;
    font-size: 0.85em;
    text-align: center;
    opacity: 0;
    transition: opacity 1.2s ease-in-out;
}
.slideshow-caption.active {
    opacity: 1;
}

/* ── Gallery grid ── */
.photo-gallery {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
    gap: 1.5em;
    margin-top: 2em;
}
.photo-card {
    overflow: hidden;
    border-radius: 8px;
    box-shadow: 0 2px 10px rgba(0,0,0,0.12);
    background: #fff;
}
.photo-card img {
    width: 100%;
    height: 260px;
    object-fit: contain;
    display: block;
    background: #f5f5f5;
}
.photo-card .caption {
    padding: 0.6em 0.8em;
    font-size: 0.9em;
    color: #444;
    text-align: center;
}
</style>

<!-- ═══════════════════════════════════════════════════
     SLIDESHOW – automatically cycles through every
     image listed in the gallery below at 5-second
     intervals with a cross-fade.
     ═══════════════════════════════════════════════════ -->
<div class="slideshow-container" id="slideshow">
    <!-- Images are injected by the script below -->
</div>

---

<!-- ═══════════════════════════════════════════════════
     GALLERY – Add new photos using the template below.
     Photos render in the order they appear here.

     TEMPLATE (copy & paste, then fill in):

     <div class="photo-card">
         <img src="/assets/images/photos/YOUR_FILENAME.jpg" alt="Short description">
         <div class="caption">Your caption text here</div>
     </div>

     ═══════════════════════════════════════════════════ -->

## Gallery

<div class="photo-gallery" id="photoGallery">

     <div class="photo-card">
         <img src="/assets/images/photos/DSC02352.jpg">
         <div class="caption">Group Hike at Makiki Valley Loop Trail - April 4th, 2026</div>
     </div>

</div>

<!-- ═══════════════════════════════════════════════════
     SCRIPT – Drives the slideshow.
     It collects every <img> inside #photoGallery,
     clones them into the slideshow container, and
     fades through them at 10-second intervals.
     ═══════════════════════════════════════════════════ -->
<script>
document.addEventListener("DOMContentLoaded", function () {
    var gallery   = document.getElementById("photoGallery");
    var slideshow = document.getElementById("slideshow");
    var imgs      = gallery.querySelectorAll(".photo-card img");

    if (imgs.length === 0) return;

    /* Build arrays of sources and captions, then shuffle in sync */
    var sources = [];
    var captions = [];
    Array.prototype.forEach.call(imgs, function (img) {
        sources.push(img.src);
        var captionText = img.parentElement.querySelector(".caption");
        captions.push(captionText ? captionText.textContent : "");
    });

    function shuffle(arr1, arr2) {
        for (var i = arr1.length - 1; i > 0; i--) {
            var j = Math.floor(Math.random() * (i + 1));
            var tmp1 = arr1[i]; arr1[i] = arr1[j]; arr1[j] = tmp1;
            var tmp2 = arr2[i]; arr2[i] = arr2[j]; arr2[j] = tmp2;
        }
        return [arr1, arr2];
    }
    shuffle(sources, captions);

    /* Create two <img> elements and two caption elements for cross-fading */
    var imgA = document.createElement("img");
    var imgB = document.createElement("img");
    var capA = document.createElement("div");
    var capB = document.createElement("div");
    capA.classList.add("slideshow-caption");
    capB.classList.add("slideshow-caption");
    slideshow.appendChild(imgA);
    slideshow.appendChild(imgB);
    slideshow.appendChild(capA);
    slideshow.appendChild(capB);

    var current = 0;
    var showingImg = imgA;
    var showingCap = capA;

    imgA.src = sources[0];
    imgA.classList.add("active");
    capA.textContent = captions[0];
    capA.classList.add("active");

    function next() {
        current = (current + 1) % sources.length;

        /* Pick the hidden image and caption elements */
        var hiddenImg = (showingImg === imgA) ? imgB : imgA;
        var hiddenCap = (showingCap === capA) ? capB : capA;
        hiddenImg.src = sources[current];
        hiddenCap.textContent = captions[current];

        /* Once loaded, cross-fade */
        hiddenImg.onload = function () {
            showingImg.classList.remove("active");
            showingCap.classList.remove("active");
            hiddenImg.classList.add("active");
            hiddenCap.classList.add("active");
            showingImg = hiddenImg;
            showingCap = hiddenCap;
        };
    }

    setInterval(next, 10000);
});
</script>
