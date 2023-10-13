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

<svelte:head>
	<style>
		body,
		html {
			margin: 0;
			padding: 0;
		}
	</style>
</svelte:head>

<style>
	.grid {
		display: grid;
		grid-template-columns: repeat(3, 63mm);
		width: 189mm;
		height: 264mm;
	}

	img {
		width: 63mm;
		height: 88mm;
		object-fit: cover;
		border: 1px solid black;
		box-shadow: 2px 2px 5px rgba(0, 0, 0, 0.3);
	}
</style>
