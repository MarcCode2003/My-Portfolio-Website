<script lang="ts">
  // List of resumes with category + links
  const resumes = [
    {
      title: "Frontend Web Developer",
      language: "English",
      link: "/resumes/frontend_en.pdf"
    },
    {
      title: "Frontend Web Developer",
      language: "日本語 (Japanese)",
      link: "/resumes/frontend_jp.pdf"
    },
    {
      title: "Photo & Video Editor",
      language: "English",
      link: "/resumes/editor_en.pdf"
    },
    {
      title: "Photo & Video Editor",
      language: "日本語 (Japanese)",
      link: "/resumes/editor_jp.pdf"
    },
    {
      title: "Discord Staff / Mod / Admin / Manager",
      language: "English",
      link: "/resumes/discord_en.pdf"
    },
    {
      title: "Discord Staff / Mod / Admin / Manager",
      language: "日本語 (Japanese)",
      link: "/resumes/discord_jp.pdf"
    }
  ];
</script>

<section class="resume-section">
  <h2 class="section-title">📄 My Resumes</h2>
  <p class="section-subtitle">View or download my resumes in English or Japanese.</p>
  <p class="section-subtitle">英語版または日本語版の履歴書をご覧いただくか、ダウンロードしてください。</p>

  <div class="resume-grid">
    {#each resumes as resume (resume.link)}
      <a href={resume.link} target="_blank" class="resume-card">
        <div class="card-content">
          <h3>{resume.title}</h3>
          <p>{resume.language}</p>
        </div>
        <div class="hover-glow"></div>
      </a>
    {/each}
  </div>
</section>

<style>
  .resume-section {
    text-align: center;
    padding: 4rem 2rem;
    background: linear-gradient(135deg, #0f172a, #1e293b);
    color: white;
  }

  .section-title {
    font-size: 2rem;
    font-weight: 700;
    margin-bottom: 0.5rem;
  }

  .section-subtitle {
    color: #94a3b8;
    margin-bottom: 2rem;
  }

  .resume-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 1.5rem;
    justify-items: center;
  }

  .resume-card {
    position: relative;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    width: 100%;
    max-width: 300px;
    height: 160px;
    background: #1e293b;
    border-radius: 16px;
    text-decoration: none;
    overflow: hidden;
    color: white;
    box-shadow: 0 4px 15px rgba(0,0,0,0.2);
    transition: transform 0.3s ease, box-shadow 0.3s ease;
  }

  .resume-card:hover {
    transform: translateY(-6px);
    box-shadow: 0 10px 25px rgba(59, 130, 246, 0.4);
  }

  .card-content h3 {
    font-size: 1.1rem;
    margin-bottom: 0.3rem;
  }

  .card-content p {
    font-size: 0.9rem;
    color: #a5b4fc;
  }

  .hover-glow {
    position: absolute;
    inset: 0;
    background: radial-gradient(circle at top left, rgba(59, 130, 246, 0.3), transparent 60%);
    opacity: 0;
    transition: opacity 0.4s ease;
  }

  .resume-card:hover .hover-glow {
    opacity: 1;
  }

  @media (max-width: 600px) {
    .section-title {
      font-size: 1.6rem;
    }
    .resume-card {
      height: 140px;
    }
  }
</style>
