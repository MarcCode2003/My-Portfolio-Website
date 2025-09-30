<script>
  let notification = "";
  let showNotification = false;

  function copyToClipboard(text) {
    navigator.clipboard.writeText(text).then(() => {
      notification = "✅ Copied to clipboard!";
      showNotification = true;
      setTimeout(() => {
        showNotification = false;
      }, 2000);
    });
  }
</script>

<section class="py-20 bg-gradient-to-b from-gray-900 to-black text-white" id="contact">
  <div class="max-w-5xl mx-auto px-6">
    <h2 class="text-4xl font-bold mb-10 text-center">📬 Contact Me</h2>

    <div class="grid md:grid-cols-2 gap-6">

      <!-- Facebook -->
      <div class="p-6 rounded-2xl bg-gray-800/60 backdrop-blur-md border border-gray-700 shadow-lg flex items-center justify-between">
        <div>
          <h3 class="text-lg font-semibold">Facebook</h3>
          <p class="text-sm text-gray-400">facebook.com/maaku0223</p>
        </div>
        <div class="flex space-x-2">
          <a href="https://www.facebook.com/maaku0223" target="_blank" 
            class="px-3 py-2 bg-blue-600 text-white rounded-lg hover:bg-blue-700 text-sm transition">
            Visit
          </a>
          <button 
            class="px-3 py-2 text-sm border border-gray-600 rounded-lg hover:bg-gray-700 transition" 
            on:click={() => copyToClipboard('https://www.facebook.com/maaku0223')}>
            Copy
          </button>
        </div>
      </div>

      <!-- Instagram -->
      <div class="p-6 rounded-2xl bg-gray-800/60 backdrop-blur-md border border-gray-700 shadow-lg flex items-center justify-between">
        <div>
          <h3 class="text-lg font-semibold">Instagram</h3>
          <p class="text-sm text-gray-400">@maaku0223</p>
        </div>
        <div class="flex space-x-2">
          <a href="https://www.instagram.com/maaku0223/" target="_blank" 
            class="px-3 py-2 bg-pink-500 text-white rounded-lg hover:bg-pink-600 text-sm transition">
            Visit
          </a>
          <button 
            class="px-3 py-2 text-sm border border-gray-600 rounded-lg hover:bg-gray-700 transition" 
            on:click={() => copyToClipboard('https://www.instagram.com/maaku0223/')}>
            Copy
          </button>
        </div>
      </div>

      <!-- LinkedIn -->
      <div class="p-6 rounded-2xl bg-gray-800/60 backdrop-blur-md border border-gray-700 shadow-lg flex items-center justify-between">
        <div>
          <h3 class="text-lg font-semibold">LinkedIn</h3>
          <p class="text-sm text-gray-400">linkedin.com/in/marc-samuel-canales-b87944317</p>
        </div>
        <div class="flex space-x-2">
          <a href="https://www.linkedin.com/in/marc-samuel-canales-b87944317/" target="_blank" 
            class="px-3 py-2 bg-blue-700 text-white rounded-lg hover:bg-blue-800 text-sm transition">
            Visit
          </a>
          <button 
            class="px-3 py-2 text-sm border border-gray-600 rounded-lg hover:bg-gray-700 transition" 
            on:click={() => copyToClipboard('https://www.linkedin.com/in/marc-samuel-canales-b87944317/')}>
            Copy
          </button>
        </div>
      </div>

      <!-- GitHub -->
      <div class="p-6 rounded-2xl bg-gray-800/60 backdrop-blur-md border border-gray-700 shadow-lg flex items-center justify-between">
        <div>
          <h3 class="text-lg font-semibold">GitHub</h3>
          <p class="text-sm text-gray-400">github.com/MarcCode2003</p>
        </div>
        <div class="flex space-x-2">
          <a href="https://github.com/MarcCode2003" target="_blank" 
            class="px-3 py-2 bg-gray-700 text-white rounded-lg hover:bg-black text-sm transition">
            Visit
          </a>
          <button 
            class="px-3 py-2 text-sm border border-gray-600 rounded-lg hover:bg-gray-700 transition" 
            on:click={() => copyToClipboard('https://github.com/MarcCode2003')}>
            Copy
          </button>
        </div>
      </div>

      <!-- Email -->
      <div class="p-6 rounded-2xl bg-gray-800/60 backdrop-blur-md border border-gray-700 shadow-lg flex items-center justify-between">
        <div>
          <h3 class="text-lg font-semibold">Email</h3>
          <p class="text-sm text-gray-400">marcsamuelcanales.26@gmail.com</p>
        </div>
        <div class="flex space-x-2">
          <button 
            class="px-3 py-2 text-sm border border-gray-600 rounded-lg hover:bg-gray-700 transition" 
            on:click={() => copyToClipboard('marcsamuelcanales.26@gmail.com')}>
            Copy
          </button>
        </div>
      </div>

      <!-- Calendly -->
      <div class="p-6 rounded-2xl bg-gray-800/60 backdrop-blur-md border border-gray-700 shadow-lg flex items-center justify-between">
        <div>
          <h3 class="text-lg font-semibold">Calendly</h3>
          <p class="text-sm text-gray-400">Schedule a meeting with me</p>
        </div>
        <a href="https://calendly.com/your-username" target="_blank" 
          class="px-4 py-2 bg-green-500 text-white rounded-lg hover:bg-green-600 text-sm transition">
          Book
        </a>
      </div>

    </div>
  </div>

  <!-- Toast Notification -->
  {#if showNotification}
    <div class="fixed top-6 right-6 bg-white/10 backdrop-blur-lg text-white border border-white/20 px-4 py-2 rounded-lg shadow-xl animate-fade-in">
      {notification}
    </div>
  {/if}
</section>

<style>
  @keyframes fade-in {
    from { opacity: 0; transform: translateY(-10px); }
    to { opacity: 1; transform: translateY(0); }
  }
  .animate-fade-in {
    animation: fade-in 0.3s ease-out;
  }
</style>
