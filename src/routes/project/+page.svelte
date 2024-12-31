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

  let projects = [
    {
      title: "Building Competent Models: Ensembles for Unlearning Single Feature Artifacts",
      description: "Large NLI datasets often exhibit word-label imbalances, commonly referred to as single feature artifacts, which pose challenges for training robust language inference models. In this project, I apply the competency problems framework to identify these artifacts within the SNLI dataset. I analyze their impact on entailment predictions made by an ELECTRA-small model and present evidence that training ELECTRA-small in a mixed capacity ensemble with a unigram bag-of-words multi-layer perceptron model can effectively mitigate single feature bias.",
      github: "https://github.com/ekgoode/ensemble_based_debiasing",
      writeup: "/pdf/CompetentModels.pdf",
      image: "/images/competent_models.png"
    },
    {
      title: "Replication Package: Projecting the Impact of Rising Temperatures: The Role of Macroeconomic Dynamics.",
      description: "This repository provides the replication package for the study 'Projecting the Impact of Rising Temperatures: The Role of Macroeconomic Dynamics,' published in the IMF Economic Review in 2023. Authored by Gregory Casey, Stephie Fried, and Ethan Goode, the study explores how temperature fluctuations affect economic growth, distinguishing between temporary impacts on output per capita and more enduring effects. The replication package includes the data, code, and documentation necessary to reproduce the study's key findings and projections.",
      github: "https://github.com/ekgoode/climate-macrodynamics",
      writeup: "/pdf/climate_replication.pdf",
      image: "/images/climate_replication.png"
    }
    // Add more projects as needed
  ];
</script>

<header class="bg-[#f8f1e7] dark:bg-gray-900 py-4 shadow-md">
  <div class="max-w-6xl mx-auto px-8 flex justify-between items-center">
    <a href="/" class="text-2xl font-bold text-teal-500 dark:text-teal-300 hover:underline">Ethan Goode</a>
    <nav class="flex space-x-6">
      <a href="/" class="text-gray-700 dark:text-gray-300 hover:text-teal-500 dark:hover:text-teal-300">About</a>
      <a href="/publications" class="text-gray-700 dark:text-gray-300 hover:text-teal-500 dark:hover:text-teal-300">Publications</a>
      <a href="/projects" class="text-gray-700 dark:text-gray-300 hover:text-teal-500 dark:hover:text-teal-300">Projects</a>
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
    <h1 class="text-4xl font-bold text-gray-900 dark:text-gray-100 mb-6">Projects</h1>

    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
      {#each projects as project}
        <div class="bg-white dark:bg-gray-800 shadow-md rounded-lg overflow-hidden">
          <img src={project.image} alt={project.title} class="w-full h-40 object-cover">
          <div class="p-4">
            <h2 class="text-xl font-bold text-gray-900 dark:text-gray-100 mb-2">{project.title}</h2>
            <p class="text-gray-700 dark:text-gray-300 text-sm mb-4">{project.description}</p>
            <div class="flex space-x-4">
              <a href={project.github} target="_blank" class="bg-teal-500 hover:bg-teal-400 text-white py-1 px-3 rounded-md text-sm">GitHub</a>
              <a href={project.writeup} target="_blank" class="bg-gray-500 hover:bg-gray-400 text-white py-1 px-3 rounded-md text-sm">Write-Up</a>
            </div>
          </div>
        </div>
      {/each}
    </div>
  </main>
</div>
