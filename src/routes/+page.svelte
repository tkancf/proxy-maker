<script lang="ts">
	import { getContext } from 'svelte';
	import { goto } from '$app/navigation';

	const imageUrls: string[] = getContext('imageUrls');
	let imageUrlInput: string = '';

	const goImages = () => {
		imageUrls.push(...imageUrlInput.trim().split('\n'));
		goto('/images');
	};
	import '../app.css';
</script>

<div class="bg-white p-10 rounded">
	<textarea
		bind:value={imageUrlInput}
		rows="12"
		placeholder="1行に1つの画像URLを入力してください
例:
https://example.com/image1.jpg
https://example.com/image2.jpg"
		class="w-full p-2 text-lg border rounded mb-5 resize-none"
	/>
	<button
		on:click={goImages}
		class="cursor-pointer bg-blue-500 text-white border-0 py-2 px-5 rounded text-lg transition-colors hover:bg-blue-700"
	>
		プロキシ画像を表示
	</button>
</div>
