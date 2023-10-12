<script lang="ts">
	let imageUrlInput = '';
	let imageUrls: string[] = [];

	function showImages() {
		imageUrls = [...new Set(imageUrlInput.trim().split('\n'))];
	}
</script>

<div>
	<textarea bind:value={imageUrlInput} rows="9" placeholder="画像のURLを入力してください..." />
	<button on:click={showImages}>画像を表示</button>

	{#if imageUrls.length}
		<div class="grid">
			{#each imageUrls as imageUrl (imageUrl)}
				{#if imageUrl}
					<img src={imageUrl} alt="User uploaded" />
				{/if}
			{/each}
		</div>
	{/if}
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
