<script>
  let experiences = [
    {
      title: "Data Analyst",
      company: "Great Lakes Behavioral Research Institute",
      logo: "/images/allegheny_county.png",
      date: "Jul 2023 – Present",
      location: "Pennsylvania"
    },
    {
      title: "Research Associate",
      company: "Federal Reserve Bank of San Francisco",
      logo: "/images/sffed_icon.svg",
      date: "Jan 2021 – May 2023",
      location: "California"
    },
    {
      title: "Research Intern",
      company: "Federal Reserve Bank of Dallas",
      logo: "/images/dallasfedicon.svg",
      date: "Jun 2020 – Aug 2020",
      location: "Texas"
    }
  ];

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
    <!-- Logo -->
    <a href="/web/" class="text-2xl font-bold text-teal-500 dark:text-teal-300 hover:underline">
      Ethan Goode
    </a>

    <!-- Navigation Links -->
    <nav class="flex space-x-6">
      <a href="/web/" class="text-gray-700 dark:text-gray-300 hover:text-teal-500 dark:hover:text-teal-300">
        About
      </a>
      <a href="/web/publications" class="text-gray-700 dark:text-gray-300 hover:text-teal-500 dark:hover:text-teal-300">
        Publications
      </a>
      <a href="/web/project" class="text-gray-700 dark:text-gray-300 hover:text-teal-500 dark:hover:text-teal-300">
        Projects
      </a>
     <a href="/web/writings" class="text-gray-700 dark:text-gray-300 hover:text-teal-500 dark:hover:text-teal-300">
        Writings
      </a>
    </nav>

    <!-- Theme Toggle Button -->
    <button
      on:click={toggleTheme}
      class="p-2 bg-gray-300 dark:bg-gray-700 text-gray-800 dark:text-gray-200 rounded-md shadow-md"
      aria-label="Toggle theme"
    >
      <span class="block dark:hidden">☀️</span>
      <span class="hidden dark:block">🌙</span>
    </button>
  </div>
</header>


<!-- Main Content -->
<div class="bg-[#f8f1e7] dark:bg-gray-900 min-h-screen">
  <main class="px-8 py-16 max-w-6xl mx-auto text-gray-700 dark:text-gray-300">
    <!-- Profile Section -->
    <section class="flex flex-col md:flex-row items-stretch md:space-x-8">
    <!-- Left Column: Profile Image & Info -->
    <div class="flex flex-col items-center md:items-center space-y-4 md:w-1/3 bg-[#f8f1e7] dark:bg-gray-900 h-full">
        <!-- Profile Image -->
        <img
        src="/images/profile.jpg"
        alt="Ethan Goode"
        class="w-60 h-60 rounded-full object-cover shadow-lg"
        />
        <!-- Name and Title -->
        <div class="text-center">
        <h1 class="text-4xl font-bold text-gray-900 dark:text-gray-100">Ethan Goode</h1>
        <p class="text-2xl text-gray-600 dark:text-gray-400">Data Analyst</p>
        <p class="text-2xl text-gray-600 dark:text-gray-400">
            <a
            href="https://www.alleghenycounty.us/Human-Services/Index.aspx"
            target="_blank"
            class="text-gray-600 hover:text-teal-400 dark:text-teal-300 dark:hover:text-teal-200"
            >
            Allegheny County Department of Human Services
            </a>
        </p>
        </div>
        <!-- Social Links -->
        <div class="flex space-x-4">
        <!-- Email Icon -->
        <a
            href="mailto:ethan.goode000@gmail.com"
            class="hover:opacity-80"
        >
            <img
                src="/images/email95.png"
                alt="Email"
                class="w-12 h-13"
            />
        </a>

        <!-- GitHub Icon -->
        <a href="https://github.com/ekgoode" class="hover:opacity-80">
        <!-- Light mode icon -->
        <img
            src="/images/github-mark.png"
            alt="GitHub"
            class="w-12 h-12 block dark:hidden"
        />
        <!-- Dark mode icon -->
        <img
            src="/images/github-mark-white.png"
            alt="GitHub"
            class="w-12 h-12 hidden dark:block"
        />
        </a>

        <!-- LinkedIn Icon -->
        <a
            href="https://www.linkedin.com/in/ethan-goode-a549971a8/"
            class="hover:opacity-80"
        >
            <img
                src="/images/LI-In-Bug.png"
                alt="LinkedIn"
                class="w-13 h-12"
            />
        </a>
        </div>
    </div>

    <!-- Right Column: Welcome Section -->
    <div class="flex-1 flex flex-col justify-between">
        <div>
        <h2 class="text-2xl font-bold text-gray-900 dark:text-gray-100">Welcome</h2>
        <p class="mt-4">
            I am an aspiring data scientist and current data analyst at the Allegheny County Department of Human Services in Pittsburgh, PA. My mission is to apply machine learning for the benefit of others, focusing on applications in public policy and research into algorithmic fairness.  
        </p>
        <p class="mt-4">
            The content on this website is solely the responsibility of my own and should not be
            interpreted as reflecting the views of Great Lakes Behavioral Research Institute or
            Allegheny County.
        </p>
        <p class="mt-6">
            <a
            href="/pdf/ethan_goode_resume.pdf"
            target="_blank"
            download="Ethan_Goode_Resume.pdf"
            class="text-teal-500 hover:text-teal-400 dark:text-teal-300 dark:hover:text-teal-200"
            >
            📄 Download my <span class="font-semibold">resume</span>.
            </a>
        </p>
        </div>

        <!-- Interests and Education Section -->
        <div class="grid grid-cols-1 md:grid-cols-2 gap-8 mt-12">
        <!-- Interests -->
        <div>
            <h3 class="text-xl font-bold text-gray-900 dark:text-gray-100">Interests</h3>
            <ul class="mt-4 space-y-2 list-disc list-inside">
            <li>Machine Learning</li>
            <li>Algorithmic Fairness</li>
            <li>Natural Language Processing</li>
            </ul>
        </div>

        <!-- Education -->
        <div>
            <h3 class="text-xl font-bold text-gray-900 dark:text-gray-100">Education</h3>
            <ul class="mt-4 space-y-4">
            <li>
                🎓 <span class="font-semibold">BSc in Economics, 2020</span><br />
                <span class="text-sm text-gray-600 dark:text-gray-400">University of Houston</span>
            </li>
            <li>
                🎓 <span class="font-semibold">MS in Data Science, Ongoing</span><br />
                <span class="text-sm text-gray-600 dark:text-gray-400">
                The University of Texas at Austin
                </span>
            </li>
            </ul>
        </div>
        </div>
    </div>
    </section>
    <section class="max-w-6xl mx-auto py-16">
    <h2 class="text-4xl font-bold text-gray-900 dark:text-gray-100 mb-8">Experience</h2>
    <div class="relative border-l-2 border-gray-300 dark:border-gray-700 ml-4">
        {#each experiences as exp}
        <div class="mb-8 ml-6">
            <span class="absolute w-6 h-6 bg-teal-500 dark:bg-teal-300 rounded-full mt-2.5 -left-3.5"></span>
            <div class="p-4 bg-white dark:bg-gray-800 rounded-lg shadow-md">
            <div class="flex items-center space-x-4">
                <img src={exp.logo} alt={exp.company} class="w-12 h-12 object-cover rounded-full" />
                <div>
                <h3 class="text-xl font-bold text-gray-900 dark:text-gray-100">{exp.title}</h3>
                <p class="text-gray-600 dark:text-gray-400">{exp.company}</p>
                </div>
            </div>
            <p class="text-sm text-gray-500 dark:text-gray-400 mt-2">{exp.date} · {exp.location}</p>
            </div>
        </div>
        {/each}
    </div>
    </section>

  </main>
</div>
