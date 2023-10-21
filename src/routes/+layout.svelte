<script lang="ts">
	import { setContext } from 'svelte';
	import { goto } from '$app/navigation';
	let imageUrls: string[] = [];
	setContext('imageUrls', imageUrls);
	function backToTop() {
		goto('/');
	}
</script>

<!-- ナビゲーションバー -->
<div class="bg-blue-500 p-4 text-white flex justify-between items-center">
	<div class="text-lg font-semibold">Your App Name</div>
	<button
		on:click={backToTop}
		class="bg-white text-blue-500 px-4 py-2 rounded hover:bg-blue-200 transition-colors"
	>
		トップページへ戻る
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
