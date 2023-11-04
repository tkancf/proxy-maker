<script lang="ts">
	import { getContext, onMount } from 'svelte';
	import { goto } from '$app/navigation';

	const imageUrls: string[] = getContext('imageUrls');
	let imageUrlInput: string = '';

	const goImages = () => {
		imageUrls.splice(0, imageUrls.length);
		imageUrls.push(...imageUrlInput.trim().split('\n'));
		goto('/images');
	};

	onMount(() => {
		if (imageUrls.length > 0) {
			imageUrlInput = imageUrls.join('\n');
		}
	});
</script>

<head:meta>
	<title>Proxy Maker</title>
	<meta name="description" content="カードの画像URLからプロキシを作成するためのツールです。" />
	<meta name="keywords" content="Proxy Maker,プロキシ,画像,URL" />
</head:meta>

<div class="bg-white p-9 rounded">
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
		class="cursor-pointer bg-neutral-600 text-white border-0 py-2 px-5 rounded text-lg transition-colors hover:text-gray-300"
	>
		プロキシ画像を表示
	</button>
</div>
