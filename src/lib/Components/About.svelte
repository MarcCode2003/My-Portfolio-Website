<script lang="ts">
  export let id: string = "about"; // anchor for navigation
</script>

<section id={id} class="about">
  <div class="container">
    <h2 class="title">About Me</h2>
    <p class="intro">
      I believe in a user-centered design approach, ensuring that every project I work on 
      is tailored to meet the specific needs of its users.
    </p>

    <div class="content">
      <h1 class="subtitle">This is me.</h1>
      <h3 class="name">Hi, I'm Marc.</h3>
      <p>
        I'm a frontend web developer dedicated to turning ideas into creative solutions. 
        I specialize in creating seamless and intuitive user experiences.
      </p>
      <p>
        My approach focuses on creating scalable, high-performing solutions tailored 
        to both user needs and business objectives. By prioritizing performance, 
        accessibility, and responsiveness, I strive to deliver experiences that 
        not only engage users but also drive tangible results.
      </p>
    </div>
  </div>
</section>

<style>
  .about {
    min-height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 4rem 2rem;
    background: #0f0f0f;
    color: #f5f5f5;
  }

  .container {
    max-width: 900px;
    text-align: center;
  }

  .title {
    font-size: 2rem;
    font-weight: 600;
    margin-bottom: 1.5rem;
    color: #00d1b2;
  }

  .intro {
    font-size: 1.2rem;
    margin-bottom: 2.5rem;
    line-height: 1.6;
  }

  .subtitle {
    font-size: 1.3rem;
    font-weight: 500;
    margin-bottom: 0.5rem;
    color: #aaa;
  }

  .name {
    font-size: 2.5rem;
    font-weight: 700;
    margin-bottom: 1.5rem;
    color: #fff;
  }

  .content p {
    font-size: 1.1rem;
    line-height: 1.7;
    margin-bottom: 1rem;
  }
</style>
