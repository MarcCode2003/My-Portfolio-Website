<!-- BG EFFECT -->
<script lang="ts">
  import { onMount } from 'svelte';

  let mouseX = 0;
  let mouseY = 0;
  const particles: { el: HTMLDivElement; vx: number; vy: number }[] = [];
  const maxParticles = 80;
  const avoidRadius = 80;

  function handleMouse(e: MouseEvent) {
    mouseX = e.clientX;
    mouseY = e.clientY;
  }

  onMount(() => {
    // Instead of only hero, attach particles to the whole body
    const container = document.body;

    function createParticle() {
      const p = document.createElement('div');
      p.className =
        'particle fixed w-[4px] h-[4px] bg-white opacity-50 rounded-full pointer-events-none';
      p.style.left = `${Math.random() * window.innerWidth}px`;
      p.style.top = `${Math.random() * -window.innerHeight}px`; // spawn above
      container.appendChild(p);

      const vx = (Math.random() - 0.5) * 0.3;
      const vy = 1 + Math.random() * 1;

      particles.push({ el: p, vx, vy });
    }

    // spawn all particles
    for (let i = 0; i < maxParticles; i++) createParticle();

    function animate() {
      const pageHeight = document.body.scrollHeight; // full page height

      particles.forEach((p) => {
        let top = parseFloat(p.el.style.top || '0');
        let left = parseFloat(p.el.style.left || '0');

        // gravity
        top += p.vy;
        left += p.vx;

        // cursor avoidance (side push only)
        const dx = left - mouseX;
        const dy = top - mouseY;
        const dist = Math.hypot(dx, dy);
        if (dist < avoidRadius) {
          const angle = Math.atan2(dy, dx);
          const factor = (avoidRadius - dist) / avoidRadius;
          left += Math.cos(angle) * 3 * factor;
        }

        // reset if below page
        if (top > pageHeight) {
          top = -10; // respawn at top
          left = Math.random() * window.innerWidth;
        }

        p.el.style.top = top + 'px';
        p.el.style.left = left + 'px';
      });

      requestAnimationFrame(animate);
    }

    animate();
  });
</script>



<!-- INTRO PART -->
<section
  id="hero"
  class="h-screen relative flex flex-col justify-center items-start pl-20 bg-black text-white overflow-hidden"
>
  <h1 class="text-6xl font-bold mb-4 z-10 relative">Hi, I'm Marc</h1>
  <p class="text-2xl mb-6 z-10 relative">Frosnt-end Web Developer | SvelteKit + Tailwind + TypeScript</p>
  <p class="max-w-xl text-left mb-5">A creative Frontend Web Developer with experience in building high-performance, scalable, and responsive web solutions.</p>
  <a
    href="#projects"
    class="px-6 py-3 bg-white text-black font-bold roussnded hover:bg-gray-200 transition z-10 relative"
    >See My Work</a
  >
</section>


<svelte:window on:mousemove={handleMouse} />


