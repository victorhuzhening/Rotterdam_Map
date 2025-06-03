---
layout: default
---

## Map Preview

Below is an interactive preview of the Rotterdam Touch Grass map. Use your mouse wheel to zoom in and out.

<div class="image-container">
  <img src="Rotterdam_Map/test_squirrel_img.jpg" alt="Embed Map">
</div>

<script>
  document.addEventListener('DOMContentLoaded', function() {
    const container = document.querySelector('.image-container');
    const image = container.querySelector('img');

    let scale = 1;

    container.addEventListener('wheel', (e) => {
      e.preventDefault();
      const scaleAmount = 0.1;
      if (e.deltaY < 0) {
        scale += scaleAmount;
      } else {
        scale -= scaleAmount;
      }
      scale = Math.min(Math.max(0.5, scale), 3);
      image.style.transform = `scale(${scale})`;
    });
  });
</script>

<style>
  .image-container {
    width: 1200px; 
    height: 900px;
    overflow: auto;
    border: 2px solid #ccc;
    position: relative;
    cursor: grab;
    margin: 0 auto;
  }
  .image-container img {
    display: block; 
    max-width: none;
    transform-origin: top left;
    transition: transform 0.2s;
  }
</style>

---

## About the artist

The Rotterdam Touch Grass map was created by Sara Baldwin as her graduation project at Willem de Kooning Academy. This map is supposed to verbatim verbatim verbatim verbatim verbatim verbatim verbatim verbatim verbatim verbatim verbatim verbatim verbatim verbatim verbatim verbatim verbatim verbatim verbatim verbatim verbatim verbatim verbatim verbatim.
