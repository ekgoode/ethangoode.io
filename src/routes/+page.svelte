<script>
  import { onMount } from "svelte";

  // Function to detect mobile devices
  const isMobile = () => {
    return /Android|webOS|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini/i.test(navigator.userAgent);
  };

  onMount(() => {
    const currentPath = window.location.pathname;

    // Redirect logic
    if (isMobile() && currentPath !== "/mobile") {
      window.location.href = "/mobile";
    } else if (!isMobile() && currentPath !== "/web") {
      window.location.href = "/web";
    }
  });
</script>

<!-- Optional Fallback Content for Non-JavaScript Users -->
<div class="min-h-screen flex items-center justify-center">
  <p class="text-gray-700 dark:text-gray-300">Redirecting to the appropriate version...</p>
</div>
