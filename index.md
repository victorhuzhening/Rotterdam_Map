---
layout: default
---

## Map Preview

***

Below is an interactive preview of the Rotterdam Touch Grass map. Use your mouse wheel to zoom in and out.

<div class="image-window">
  <img id="zoom-image" img src="./test_squirrel_img.jpg" alt="Zoomable-Pannable-Map">
</div>

<style>
  .image-window {
    width: 800px;    /* Set your desired window width */
    height: 600px;   /* Set your desired window height */
    overflow: hidden; /* Hide scrollbars initially */
    border: 2px solid #ccc;
    position: relative;
  }

  .image-window img {
    width: 100%; /* Initial size fits the window */
    height: 100%;
    object-fit: contain;
    transform-origin: center center;
    transition: transform 0.1s ease;
    display: block;
  }

  /* When the window is zoomed, allow scrollbars */
  .zoomed .image-window {
    overflow: auto;
  }
</style>

<script>
  document.addEventListener('DOMContentLoaded', function() {
    const container = document.querySelector('.image-window');
    const image = document.getElementById('zoom-image');

    let scale = 1;
    let originX = 0;
    let originY = 0;

    container.addEventListener('wheel', function(e) {
      e.preventDefault();

      // Calculate the cursor position relative to the image
      const rect = image.getBoundingClientRect();
      const offsetX = e.clientX - rect.left;
      const offsetY = e.clientY - rect.top;

      // Update origin to the cursor position
      const originPercentX = (offsetX / image.width) * 100;
      const originPercentY = (offsetY / image.height) * 100;
      image.style.transformOrigin = `${originPercentX}% ${originPercentY}%`;

      // Adjust scale
      const scaleAmount = e.deltaY < 0 ? 1.1 : 0.9;
      scale *= scaleAmount;
      scale = Math.min(Math.max(1, scale), 5);

      // Apply scaling
      image.style.transform = `scale(${scale})`;

      // Toggle overflow
      if (scale > 1) {
        container.style.overflow = 'auto';
      } else {
        container.style.overflow = 'hidden';
      }
    });

    // Resize the image to fit the container on page load
    window.addEventListener('resize', () => {
      image.style.width = '100%';
      image.style.height = '100%';
      image.style.objectFit = 'contain';
      image.style.transform = `scale(${scale})`;
    });

    // Ensure it's reset on load
    image.style.transform = `scale(${scale})`;
  });
</script>

***

## About the artist

The Rotterdam Touch Grass map was created by Sara Baldwin as her graduation project at Willem de Kooning Academy. This map is supposed to verbatim verbatim verbatim verbatim verbatim verbatim verbatim verbatim verbatim verbatim verbatim verbatim verbatim verbatim verbatim verbatim verbatim verbatim verbatim verbatim verbatim verbatim verbatim verbatim.
