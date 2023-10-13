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
		grid-template-columns: repeat(3, 63mm);
		width: 189mm; /* 3画像 x 63mm = 189mm */
		height: 264mm; /* 3画像 x 88mm = 264mm */
		margin: 0; /* 余白を削除 */
		padding: 0; /* 余白を削除 */
		box-sizing: border-box;
	}

	img {
		width: 63mm;
		height: 88mm;
		object-fit: cover; /* 画像のアスペクト比を保持しながら、指定されたサイズに収める */
		border: 1px solid black;
		box-shadow: 2px 2px 5px rgba(0, 0, 0, 0.3);
	}
</style>
