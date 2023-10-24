<script lang="ts">
	import { setContext } from 'svelte';
	import { goto } from '$app/navigation';
	let imageUrls: string[] = [];
	setContext('imageUrls', imageUrls);
	function gotoTop() {
		goto('/');
	}
	function gotoHelp() {
		goto('/help');
	}
	import '../app.css';
</script>

<div class="bg-neutral-600 text-neutral-100 p-4 text-center flex items-center space-x-4">
	<button
		class="hover:text-neutral-400 text-lg font-semibold bg-transparent border-none p-0 m-0 cursor-pointer focus:outline-none"
		on:click={gotoTop}
	>
		Proxy Maker
	</button>
	<button
		class="hover:text-neutral-400 text-lg font-semibold bg-transparent border-none p-0 m-0 cursor-pointer focus:outline-none"
		on:click={gotoHelp}
	>
		使い方
	</button>
</div>

<slot />

<style>
	/* 印刷時のスタイル */
	@media print {
		.bg-neutral-600 {
			display: none; /* ナビゲーションを非表示にする */
		}
	}
</style>
