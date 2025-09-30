<script>
  // Example project list (you can replace with real data later)
  let projects = [
    {
      title: "E-vent System",
      description: "Web-based event management system with biometrics.",
      link: "https://github.com/your-repo/event-system",
      image: "https://via.placeholder.com/400x200" // Replace with your project screenshot
    },
    {
      title: "Portfolio Website",
      description: "My personal developer portfolio built with Svelte + Vite.",
      link: "https://maaku0223portfolio.my.canva.site/portfolio-website",
      image: "https://via.placeholder.com/400x200"
    },
    {
      title: "Video Editing Samples",
      description: "Collection of edited videos for Reels, TikTok, Shorts.",
      link: "https://drive.google.com/", // Example
      image: "https://via.placeholder.com/400x200"
    }
  ];
</script>

<section id="projects" class="projects">
  <h2>Projects Showcase</h2>

  <div class="grid">
    {#each projects as project}
      <div class="card">
        <img src={project.image} alt={project.title} />
        <div class="card-body">
          <h3>{project.title}</h3>
          <p>{project.description}</p>
          <a href={project.link} target="_blank">🔗 View Project</a>
        </div>
      </div>
    {/each}
  </div>
</section>

<style>
  .projects {
    padding: 4rem 2rem;
    text-align: center;
    background: #111;
    color: white;
  }

  .projects h2 {
    font-size: 2rem;
    margin-bottom: 2rem;
    color: #00ffcc;
  }

  .grid {
    display: grid;
    gap: 2rem;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  }

  .card {
    background: #222;
    border-radius: 12px;
    overflow: hidden;
    box-shadow: 0 4px 12px rgba(0,0,0,0.5);
    transition: transform 0.3s ease;
  }

  .card:hover {
    transform: translateY(-5px);
  }

  .card img {
    width: 100%;
    height: 180px;
    object-fit: cover;
  }

  .card-body {
    padding: 1rem;
  }

  .card-body h3 {
    margin: 0.5rem 0;
    color: #00ffcc;
  }

  .card-body a {
    display: inline-block;
    margin-top: 1rem;
    padding: 8px 16px;
    background: #00ffcc;
    color: #111;
    border-radius: 6px;
    text-decoration: none;
    font-weight: bold;
    transition: background 0.3s ease;
  }

  .card-body a:hover {
    background: #00e6b8;
  }
</style>
