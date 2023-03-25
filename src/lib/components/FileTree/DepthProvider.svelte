<script>
	import { writable, get } from 'svelte/store';

	export let depth = 0;
	const depthStore = writable(depth);

	export function useDepth() {
		let value;
		const unsubscribe = depthStore.subscribe((newValue) => {
			value = newValue;
		});
		const returnValue = get(depthStore);
		unsubscribe();
		return value !== undefined ? value : returnValue;
	}
</script>
