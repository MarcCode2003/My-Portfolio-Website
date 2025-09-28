<script lang="ts">
  import { onMount } from "svelte";

  let cursor: HTMLDivElement;
  let cursorInner: HTMLDivElement;

  onMount(() => {
    // Move cursor with mouse
    document.addEventListener("mousemove", (e) => {
      const { clientX, clientY } = e;
      if (cursor) {
        cursor.style.transform = `translate(${clientX - 20}px, ${clientY - 20}px)`;
      }
      if (cursorInner) {
        cursorInner.style.transform = `translate(${clientX - 4}px, ${clientY - 4}px)`;
      }
    });
  });
</script>

<div bind:this={cursor} class="cursor"></div>
<div bind:this={cursorInner} class="cursor-inner"></div>

<style>
  :global(html, body, button, a, input, textarea, select) {
    cursor: none !important; /* Hide default cursor */
  }

  .cursor {
    position: fixed;
    top: 0;
    left: 0;
    width: 40px;
    height: 40px;
    border: 2px solid #00d1b2;
    border-radius: 50%;
    pointer-events: none;
    transition: transform 0.1s ease-out;
    z-index: 9999;
  }

  .cursor-inner {
    position: fixed;
    top: 0;
    left: 0;
    width: 8px;
    height: 8px;
    background: #00d1b2;
    border-radius: 50%;
    pointer-events: none;
    transition: transform 0.05s ease-out;
    z-index: 9999;
  }

  /* EFFECT ON BUTTON HOVER */
  :global(button:hover),
  :global(a:hover) {
    transform: scale(1.05);
    transition: transform 0.2s ease, box-shadow 0.3s ease;
    box-shadow: 0 0 20px rgba(0, 209, 178, 0.5);
  }
</style>
