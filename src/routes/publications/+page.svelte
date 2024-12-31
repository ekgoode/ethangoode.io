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

  let articles = [
    {
      title: "Does Working from Home Boost Productivity Growth?",
      date: "January, 2024",
      link: "https://www.frbsf.org/research-and-insights/publications/economic-letter/2024/01/does-working-from-home-boost-productivity-growth/",
      description: "The COVID-19 pandemic's shift to remote and hybrid work has raised questions about its impact on U.S. productivity growth. We analyze the relationship between telework adaptability and productivity growth across industries to understand how the rise in off site work may impact the macroeconomy.",
      authors: "John G. Fernald, Ethan Goode, Huiyu Li, Brigid Meisenbacher",
      image: "/images/prod_growth.png",
      citation: "Fernald, J. G., Goode, E., Li, H., & Meisenbacher, B. (2024). Does Working from Home Boost Productivity Growth? Federal Reserve Bank of San Francisco Economic Letter."
    },
    {
      title: "How Long Do Rising Temperatures Affect Economic Growth?",
      date: "June, 2023",
      link: "https://www.frbsf.org/research-and-insights/publications/economic-letter/2023/06/how-long-do-rising-temperatures-affect-economic-growth/",
      description: "How might rising global temperatures influence GDP growth in the long-run? By synthesizing decades of country-level weather data with a standard growth model we project the impact of future temperature change on global economic output.",
      authors: "Gregory Casey, Stephie Fried, Ethan Goode",
      image: "/images/temp_rise.png",
      citation: "Casey, G., Fried, S., & Goode, E. (2023). How Long Do Rising Temperatures Affect Economic Growth? Federal Reserve Bank of San Francisco Economic Letter."
    },

    {
      title: "The Fiscal Multiplier at the Zero Bound: Evidence from Japan",
      date: "May, 2021",
      link: "https://www.frbsf.org/research-and-insights/publications/economic-letter/2021/05/fiscal-multiplier-at-zero-bound-evidence-from-japan/",
      description: "How do fiscal policy measures and zero-bound interest rates interact to influence economic recovery? Insights from Japan offer a perspective on how government spending might have amplified effects in a sustained zero-rate environment, especially during recessions.",
      authors: "Ethan Goode, Zheng Liu, Thuy Lan Nguyen",
      image: "/images/japan_zlb.png",
      citation: "Goode, E., Liu, Z., & Nguyen, T. L. (2021). The Fiscal Multiplier at the Zero Bound: Evidence from Japan. Federal Reserve Bank of San Francisco Economic Letter."
    }
  ];

  let journalPublications = [
    {
      title: "Projecting the Impact of Rising Temperatures: The Role of Macroeconomic Dynamics",
      date: "June, 2023",
      link: "https://link.springer.com/article/10.1057/s41308-023-00203-0",
      description: "How do rising temperatures influence economic growth? By separating temporary and permanent impacts on output per capita, this study offers new projections of climate change's economic effects, challenging assumptions about long-term growth impacts.",
      authors: "Gregory Casey, Stephie Fried, Ethan Goode",
      image: "/images/climate_macro_dynamics2.png",
      citation: "Casey, G., Fried, S., & Goode, E. (2023). Projecting the Impact of Rising Temperatures: The Role of Macroeconomic Dynamics. IMF Econ Rev 71, 688–718."
    }
  ];

  const copyToClipboard = (text) => {
    navigator.clipboard.writeText(text).then(
      () => alert("Citation copied to clipboard!"),
      (err) => alert("Failed to copy citation.")
    );
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

<div class="bg-[#f8f1e7] dark:bg-gray-900 min-h-screen">
  <main class="px-8 py-16 max-w-6xl mx-auto text-gray-700 dark:text-gray-300">
    <h1 class="text-4xl font-bold text-gray-900 dark:text-gray-100 mb-6">Publications</h1>

    <!-- Articles Section -->
    <section>
      <h2 class="text-2xl font-bold text-gray-900 dark:text-gray-100 mb-4">Articles</h2>
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
        {#each articles as article}
          <div class="bg-white dark:bg-gray-800 shadow-md rounded-lg overflow-hidden">
            <img src={article.image} alt={article.title} class="w-full h-40 object-cover">
            <div class="p-4">
              <h3 class="text-xl font-bold text-gray-900 dark:text-gray-100 mb-2">{article.title}</h3>
              <p class="text-sm text-gray-500 dark:text-gray-400 mb-2">{article.date}</p>
              <p class="text-sm text-gray-600 dark:text-gray-400 mb-2">{article.authors}</p>
              <p class="text-gray-700 dark:text-gray-300 text-sm mb-4">{article.description}</p>
              <div class="flex justify-between items-center">
                <a href={article.link} target="_blank" class="text-teal-500 hover:text-teal-400 dark:text-teal-300 dark:hover:text-teal-200 text-sm">Read More</a>
                <button
                  on:click={() => copyToClipboard(article.citation)}
                  class="bg-teal-500 hover:bg-teal-400 text-white py-1 px-3 rounded-md text-sm">
                  Copy Citation
                </button>
              </div>
            </div>
          </div>
        {/each}
      </div>
    </section>

    <!-- Journal Publications Section -->
    <section class="mt-12">
      <h2 class="text-2xl font-bold text-gray-900 dark:text-gray-100 mb-4">Journal Publications</h2>
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
        {#each journalPublications as journal}
          <div class="bg-white dark:bg-gray-800 shadow-md rounded-lg overflow-hidden">
            <img src={journal.image} alt={journal.title} class="w-full h-40 object-cover">
            <div class="p-4">
              <h3 class="text-xl font-bold text-gray-900 dark:text-gray-100 mb-2">{journal.title}</h3>
              <p class="text-sm text-gray-500 dark:text-gray-400 mb-2">{journal.date}</p>
              <p class="text-sm text-gray-600 dark:text-gray-400 mb-2">{journal.authors}</p>
              <p class="text-gray-700 dark:text-gray-300 text-sm mb-4">{journal.description}</p>
              <div class="flex justify-between items-center">
                <a href={journal.link} target="_blank" class="text-teal-500 hover:text-teal-400 dark:text-teal-300 dark:hover:text-teal-200 text-sm">Read More</a>
                <button
                  on:click={() => copyToClipboard(journal.citation)}
                  class="bg-teal-500 hover:bg-teal-400 text-white py-1 px-3 rounded-md text-sm">
                  Copy Citation
                </button>
              </div>
            </div>
          </div>
        {/each}
      </div>
    </section>
  </main>
</div>
