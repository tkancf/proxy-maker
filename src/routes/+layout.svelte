<script lang="ts">
	import { setContext } from 'svelte';
	import { goto } from '$app/navigation';
	let imageUrls: string[] = [];
	setContext('imageUrls', imageUrls);
	function backToTop() {
		goto('/');
	}
</script>

<div class="bg-blue-500 p-4 text-white flex justify-between items-center">
	<button
		class="text-lg font-semibold bg-transparent border-none p-0 m-0 cursor-pointer focus:outline-none"
		on:click={backToTop}
	>
		Your App Name
	</button>
</div>

<slot />

<style>
	/* 印刷時のスタイル */
	@media print {
		.bg-blue-500 {
			display: none; /* ナビゲーションを非表示にする */
		}
	}
</style>
