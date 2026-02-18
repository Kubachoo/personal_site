<script lang="ts">
	const rows = 6;
	const cols = 9;
	
	let cells = []
	for (let r = 0; r < rows; r++) {
		for (let c = 0; c < cols; c++){
			cells.push({row: r, col: c, color:'#eee' });
			}
		}
	</script>

<div class="grid-container">
	{#each cells as cell}
		<div class="cell" style="background-color: {cell.color}"></div>
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
    transition: background-color 0.3s;
  }
</style>
