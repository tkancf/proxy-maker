<script>
	import { getContext } from 'svelte';
	import { goto } from '$app/navigation';

	const imageUrls = getContext('imageUrls');
	let imageUrlInput = '';

	function goToDisplay() {
		imageUrls.push(...imageUrlInput.trim().split('\n'));
		goto('/show');
	}
</script>

<div>
	<textarea bind:value={imageUrlInput} rows="9" placeholder="画像のURLを入力してください..." />
	<button on:click={goToDisplay}>画像を表示</button>
</div>

<style>
	div {
		background: white;
		padding: 20px 40px;
		border-radius: 15px;
		box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
	}

	textarea {
		width: 100%;
		padding: 10px;
		font-size: 16px;
		border: 1px solid #ddd;
		border-radius: 5px;
		box-sizing: border-box;
		margin-bottom: 20px;
		resize: none;
	}

	button {
		cursor: pointer;
		background-color: #f67280;
		color: white;
		border: none;
		padding: 10px 20px;
		border-radius: 5px;
		font-size: 16px;
		transition: background-color 0.3s ease;
	}

	button:hover {
		background-color: #c06c84;
	}
</style>
