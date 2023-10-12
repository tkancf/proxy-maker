<script>
	import { getContext } from 'svelte';

	const imageUrls = getContext('imageUrls');
</script>

<div class="grid">
	{#each imageUrls as imageUrl, index (index)}
		{#if imageUrl}
			<img src={imageUrl} alt="User uploaded" />
		{/if}
	{/each}
</div>

<style>
	.grid {
		display: grid;
		grid-template-columns: repeat(3, 1fr);
		gap: 10px;
	}

	img {
		width: 100%;
		height: auto;
		border: 1px solid black;
		box-shadow: 2px 2px 5px rgba(0, 0, 0, 0.3);
	}
</style>
