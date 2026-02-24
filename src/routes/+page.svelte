<script lang="ts">
	import AnimatedGrid from '$lib/AnimatedGrid.svelte';
</script>

<main>
  <AnimatedGrid />
  <h1 class="absolute top-10 left-10 text-black text-3xl font-normal">welcome.</h1>
  <div class="absolute top-10 right-10 flex gap-6">
    <a href="/projects" class="text-gray-400 text-base hover:text-black">projects</a>
    <a href="/about" class="text-gray-400 text-base hover:text-black">about me</a>
    <a href="/contact" class="text-gray-400 text-base hover:text-black">contact</a>
  </div>
</main>

<style>
  main {
    position: relative;
    height: 100vh;
    background-color: white;
    overflow: hidden;
  }
</style>

