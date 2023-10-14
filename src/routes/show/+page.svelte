<script>
	import { getContext } from 'svelte';
	import { goto } from '$app/navigation';

	const imageUrls = getContext('imageUrls');

	function backToTop() {
		goto('/');
	}
</script>

<!-- トップページへ戻るボタンを上部に移動 -->
<button on:click={backToTop} class="back-button">トップページへ戻る</button>

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
		grid-template-rows: repeat(3, 1fr);
		width: 189mm;
		height: 264mm;
		margin-top: 20px; /* ボタンとのスペース */
	}

	img {
		width: 63mm;
		height: 88mm;
		object-fit: cover;
		border: 1px solid black;
		box-shadow: 2px 2px 5px rgba(0, 0, 0, 0.3);
	}

	.back-button {
		margin-bottom: 20px; /* グリッドとのスペース */
		padding: 10px 20px;
		cursor: pointer;
		background-color: #333;
		color: #fff;
		border: none;
		border-radius: 5px;
		transition: background-color 0.3s;
	}

	.back-button:hover {
		background-color: #555;
	}

	/* 印刷時のスタイル */
	@media print {
		.back-button {
			display: none; /* ボタンを非表示にする */
		}
		.grid {
			margin-top: 0; /* 余白を削除 */
		}
	}
</style>
