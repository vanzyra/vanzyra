<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Vanzyra - Portfolio</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <script>
    // Dark Mode Setup
    if(localStorage.getItem("theme") === "light"){
      document.documentElement.classList.remove("dark");
    } else {
      document.documentElement.classList.add("dark");
    }
  </script>
</head>
<body class="bg-gray-900 text-white font-sans transition-colors duration-500 dark:bg-gray-900 dark:text-white">

  <!-- Navbar -->
  <nav class="fixed top-0 left-0 w-full bg-gray-800/70 backdrop-blur-md py-4 px-8 flex justify-between items-center z-50">
    <h1 class="text-xl font-bold">Vanzyra</h1>
    <div>
      <button id="themeToggle" class="px-4 py-2 bg-indigo-500 rounded-lg text-sm font-semibold hover:bg-indigo-600 transition">🌙/☀️</button>
    </div>
  </nav>

  <!-- Hero Section -->
  <header class="h-screen flex flex-col justify-center items-center bg-gradient-to-r from-indigo-600 via-purple-600 to-pink-500 text-center">
    <h1 class="text-6xl md:text-7xl font-extrabold animate-bounce">Vanzyra</h1>
    <p class="mt-4 text-xl md:text-2xl opacity-90">Future Web Developer & Designer</p>
    <a href="#projects" class="mt-6 px-6 py-3 bg-white text-gray-900 font-semibold rounded-full shadow-lg hover:scale-110 transform transition">View My Work</a>
  </header>

  <!-- About -->
  <section id="about" class="max-w-4xl mx-auto py-20 px-6 text-center opacity-0 translate-y-6 transition-all duration-700" data-animate>
    <h2 class="text-4xl font-bold mb-6 text-indigo-400">About Me</h2>
    <p class="text-lg leading-relaxed opacity-80">
      Halo, saya <span class="text-pink-400 font-semibold">Vanzyra</span> 👋. 
      Saya seorang pelajar yang sedang belajar menjadi Web Developer. 
      Saya suka mendesain, coding, dan membangun sesuatu yang bermanfaat. 
      Portofolio ini adalah tempat saya berbagi karya dan perjalanan belajar saya.
    </p>
  </section>

  <!-- Projects -->
  <section id="projects" class="bg-gray-800 py-20 px-6">
    <div class="max-w-6xl mx-auto opacity-0 translate-y-6 transition-all duration-700" data-animate>
      <h2 class="text-4xl font-bold text-center mb-12 text-indigo-400">Projects</h2>
      <div class="grid md:grid-cols-3 gap-8">
        
        <div class="bg-gray-700 rounded-2xl shadow-lg p-6 hover:scale-105 hover:shadow-2xl transform transition">
          <h3 class="text-xl font-semibold mb-2">Project 1</h3>
          <p class="opacity-80">Deskripsi singkat project pertama kamu.</p>
        </div>

        <div class="bg-gray-700 rounded-2xl shadow-lg p-6 hover:scale-105 hover:shadow-2xl transform transition">
          <h3 class="text-xl font-semibold mb-2">Project 2</h3>
          <p class="opacity-80">Deskripsi singkat project kedua kamu.</p>
        </div>

        <div class="bg-gray-700 rounded-2xl shadow-lg p-6 hover:scale-105 hover:shadow-2xl transform transition">
          <h3 class="text-xl font-semibold mb-2">Project 3</h3>
          <p class="opacity-80">Deskripsi singkat project ketiga kamu.</p>
        </div>

      </div>
    </div>
  </section>

  <!-- Contact -->
  <section id="contact" class="max-w-4xl mx-auto py-20 px-6 text-center opacity-0 translate-y-6 transition-all duration-700" data-animate>
    <h2 class="text-4xl font-bold mb-6 text-indigo-400">Contact</h2>
    <p class="mb-4">Email: <a href="mailto:yourname@email.com" class="text-pink-400 hover:underline">yourname@email.com</a></p>
    <p>Instagram: <a href="https://instagram.com/username" target="_blank" class="text-pink-400 hover:underline">@username</a></p>
  </section>

  <!-- Footer -->
  <footer class="bg-gray-950 py-6 text-center text-sm opacity-70">
    © 2025 Vanzyra. All rights reserved.
  </footer>

  <!-- Script -->
  <script>
    // Theme Toggle
    const themeToggle = document.getElementById("themeToggle");
    themeToggle.addEventListener("click", () => {
      document.documentElement.classList.toggle("dark");
      if(document.documentElement.classList.contains("dark")){
        localStorage.setItem("theme","dark");
      } else {
        localStorage.setItem("theme","light");
      }
    });

    // Scroll Animations
    const elements = document.querySelectorAll("[data-animate]");
    const observer = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if(entry.isIntersecting){
          entry.target.classList.add("opacity-100","translate-y-0");
          entry.target.classList.remove("opacity-0","translate-y-6");
        }
      });
    }, {threshold:0.2});
    elements.forEach(el => observer.observe(el));
  </script>

</body>
</html>
