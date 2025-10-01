<script>
  import { onMount } from "svelte";

  let isPlaying = true;
  let audio;

  onMount(() => {
    audio = new Audio("/music/background.mp3");
    audio.loop = true;

    // Start playing automatically
    audio.play().catch(() => {
      // In case browser blocks autoplay (some do), set isPlaying = false
      isPlaying = false;
    });
  });

  function toggleMusic() {
    if (!audio) return;

    if (isPlaying) {
      audio.pause();
    } else {
      audio.play();
    }
    isPlaying = !isPlaying;
  }
</script>

<style>
.music-toggle {
  position: fixed;
  top: 1rem;
  right: 1rem;
  background: rgba(255, 255, 255, 0.1);
  backdrop-filter: blur(8px);
  border: 1px solid rgba(255, 255, 255, 0.3);
  color: white;
  padding: 0.8rem;
  border-radius: 50%;
  cursor: pointer;
  font-size: 1.3rem;
  transition: all 0.3s ease;
  z-index: 9999;
  display: flex;
  align-items: center;
  justify-content: center;
  box-shadow: 0 4px 12px rgba(0,0,0,0.2);
}
.music-toggle:hover {
  background: rgba(255,255,255,0.3);
  transform: scale(1.1);
}
</style>

<!-- Toggle Button -->
<div class="music-toggle" on:click={toggleMusic} title="Toggle music">
  {#if isPlaying}
    🔊
  {:else}
    🔇
  {/if}
</div>
