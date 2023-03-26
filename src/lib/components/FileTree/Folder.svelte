<script>
	import styles from './filetree.module.css';
	import clsx from 'clsx';
	import DepthProvider from './DepthProvider.svelte';
	import { depth } from './depth.js';
	import { get } from 'svelte/store';
	import { MinusSquareIcon, PlusSquareIcon, FolderIcon } from 'svelte-feather-icons';
	const localValue = get(depth);
	/**
	 * @type {string}
	 */
	export let name;
	/**
	 * @type {any}
	 */
	export let open = false;

	/**
	 * @type {number}
	 */
	export let depthTest = 0;
</script>

<li class={clsx(styles.folder, { open: open })}>
	<!-- svelte-ignore a11y-missing-attribute -->
	<a title={name}>
		{#each Array(depthTest) as _, i}
			<span key={i} data-tree-indent="" />
		{/each}
		<span class={styles.status}>
			{#if open}
				<MinusSquareIcon size="12" />
			{:else}
				<PlusSquareIcon size="12" />
			{/if}
		</span>
		<span class={styles.icon}
			><svg
				fill="none"
				height="22"
				shape-rendering="geometricPrecision"
				stroke="currentColor"
				stroke-linecap="round"
				stroke-linejoin="round"
				stroke-width="1.5"
				viewBox="0 0 24 24"
				width="22"
				style="color: currentcolor;"
				><path
					d="M2.707 7.454V5.62C2.707 4.725 3.469 4 4.409 4h4.843c.451 0 .884.17 1.204.474l.49.467c.126.12.296.186.473.186h8.399c.94 0 1.55.695 1.55 1.59v.737m-18.661 0h-.354a.344.344 0 00-.353.35l.508 11.587c.015.34.31.609.668.609h17.283c.358 0 .652-.269.667-.61L22 7.805a.344.344 0 00-.353-.35h-.278m-18.662 0h18.662"
				/></svg
			></span
		>
		<span class={styles.name} on:click={() => (open = !open)} {...$$restProps}>{name}</span>
		{#if open}
			<ul><slot /></ul>
		{/if}
	</a>
</li>
