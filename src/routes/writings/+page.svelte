<script>
  let theme = 'light'; // Default theme

  if (typeof window !== 'undefined') {
    // Load saved theme
    const currentTheme = localStorage.getItem('theme');
    if (currentTheme === 'dark') {
      document.documentElement.classList.add('dark');
      theme = 'dark';
    }
  }

  const toggleTheme = () => {
    if (typeof window !== 'undefined') {
      const isDark = document.documentElement.classList.toggle('dark');
      theme = isDark ? 'dark' : 'light';
      localStorage.setItem('theme', theme);
    }
  };
</script>

<header class="bg-[#f8f1e7] dark:bg-gray-900 py-4 shadow-md">
  <div class="max-w-6xl mx-auto px-8 flex justify-between items-center">
    <a href="/" class="text-2xl font-bold text-teal-500 dark:text-teal-300 hover:underline">Ethan Goode</a>
    <nav class="flex space-x-6">
      <a href="/" class="text-gray-700 dark:text-gray-300 hover:text-teal-500 dark:hover:text-teal-300">About</a>
      <a href="/publications" class="text-gray-700 dark:text-gray-300 hover:text-teal-500 dark:hover:text-teal-300">Publications</a>
      <a href="/project" class="text-gray-700 dark:text-gray-300 hover:text-teal-500 dark:hover:text-teal-300">Projects</a>
      <a href="/writings" class="text-gray-700 dark:text-gray-300 hover:text-teal-500 dark:hover:text-teal-300">Writings</a>
    </nav>
    <button
      on:click={toggleTheme}
      class="p-2 bg-gray-300 dark:bg-gray-700 text-gray-800 dark:text-gray-200 rounded-md shadow-md"
      aria-label="Toggle theme">
      <span class="block dark:hidden">☀️</span>
      <span class="hidden dark:block">🌙</span>
    </button>
  </div>
</header>

<div class="bg-[#f8f1e7] dark:bg-gray-900 min-h-screen flex flex-col items-center justify-center">
  <h1 class="text-4xl font-bold text-gray-900 dark:text-gray-100 mb-6">Under Construction</h1>
  <p class="text-lg text-gray-700 dark:text-gray-300 mb-6">
    In this section of my website, I'll host shorter writings from my research and learning. Stay tuned!
  </p>
  <img
    src="/images/under_construction2.png" 
    alt="Cute Construction Robot"
    class="w-60 h-60"
  />
</div>
