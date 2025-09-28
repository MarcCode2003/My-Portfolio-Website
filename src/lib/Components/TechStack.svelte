<script lang="ts">
  type Tech = {
    name: string;
    logo: string; // path or external URL
  };

  export let techs: Tech[] = [
    { name: "Svelte", logo: "/logos/svelte.png" },
    { name: "TypeScript", logo: "/logos/typescript.png" },
    { name: "Tailwind CSS", logo: "/logos/tailwind.png" },
    { name: "JavaScript", logo: "/logos/javascript.png" },
    { name: "HTML5", logo: "/logos/html5.png" },
    { name: "CSS3", logo: "/logos/css3.png" },
    { name: "Node.js", logo: "/logos/nodejs.png" }
  ];
</script>

<section id="tech" class="py-20 bg-gray-50 dark:bg-gray-900">
  <div class="max-w-6xl mx-auto px-6 text-center">
    <h2 class="text-4xl font-bold mb-12 text-gray-800 dark:text-gray-100">
      My Tech Stack
    </h2>

    <div class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-4 gap-10">
      {#each techs as tech}
        <div class="flex flex-col items-center group">
          <img
            src={tech.logo}
            alt={tech.name}
            class="w-16 h-16 transition-transform duration-300 group-hover:scale-110"
          />
          <p class="mt-2 text-lg font-medium text-gray-700 dark:text-gray-300">
            {tech.name}
          </p>
        </div>
      {/each}
    </div>
  </div>
</section>
