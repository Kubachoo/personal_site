<script lang="ts">
	const rows = 6;
	const cols = 9;
	
	let cells = []
	for (let r = 0; r < rows; r++) {
		for (let c = 0; c < cols; c++){
			cells.push({row: r, col: c, color:'#eee' });
			}
		}
	import { onMount } from 'svelte';

	let time = $state(0);

	onMount(() => {
	  const interval = setInterval(() => {
	    time += 0.05;
	  }, 16);

	  return () => clearInterval(interval);
	});

	
	function getColor(row: number, col: number) {
		const wave1 = Math.sin(row * 0.6 + col * 0.4 + time * 2);
		const wave2 = Math.sin(row * 0.3 - col * 0.7 + time * 1.5);
		const combined = (wave1 + wave2) / 2; // overlapping waves create varied patterns

		const lit = combined > 0.2 ? 1 : 0; // snap to white or color — no in-between

		const baseHue = (time * 4) % 360;
		const saturation = lit * 75;
		const lightness = 100 - lit * 38;
		return `hsl(${baseHue}, ${saturation}%, ${lightness}%)`;
	}
	</script>

<div class="grid-container">
	{#each cells as cell}
		<div class="cell" style="background-color: {getColor(cell.row, cell.col)}"></div>
	{/each}
</div>

<style>
  .grid-container {
    display: grid;
    grid-template-columns: repeat(9, 100px);
    grid-template-rows: repeat(6, 100px);
    gap: 4px;
    justify-content: center;
    margin-top: 130px;
  }

  .cell {
    width: 100px;
    height: 100px;
    background-color: #eee;
    transition: none;
  }
</style>
