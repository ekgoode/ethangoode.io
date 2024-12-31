<script>
	import '../app.css';
	import Footer from '$lib/Footer.svelte';
</script>

<div class="min-h-screen flex flex-col">
  <slot /> <!-- This automatically renders page content -->
  <Footer />
</div>
