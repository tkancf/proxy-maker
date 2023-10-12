<script lang="ts">
	import { setContext } from 'svelte';
	let imageUrls: string[] = [];
	setContext('imageUrls', imageUrls);
</script>

<slot />
