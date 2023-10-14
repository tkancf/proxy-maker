<script>
	import { getContext } from 'svelte';
	import { goto } from '$app/navigation';

	const imageUrls = getContext('imageUrls');
	let imageUrlInput = '';

	function goToDisplay() {
		imageUrls.push(...imageUrlInput.trim().split('\n'));
		goto('/show');
	}
	import '../app.css';
</script>

<div class="bg-white p-10 rounded shadow-md">
	<textarea
		bind:value={imageUrlInput}
		rows="9"
		placeholder="画像のURLを入力してください..."
		class="w-full p-2 text-lg border rounded mb-5 resize-none"
	/>
	<button
		on:click={goToDisplay}
		class="cursor-pointer bg-blue-500 text-white border-0 py-2 px-5 rounded text-lg transition-colors hover:bg-blue-700"
	>
		画像を表示
	</button>
</div>
