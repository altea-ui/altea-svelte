<script>
	import { depth } from './depth.js';
	import { onMount } from 'svelte';

	export let value = 0;

	onMount(() => {
		depth.set(value);
	});
</script>

<slot />