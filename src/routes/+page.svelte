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
