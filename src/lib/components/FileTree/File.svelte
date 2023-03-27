<script>
	import styles from './filetree.module.css';
	import clsx from 'clsx';
	import { BoxIcon, FileIcon } from 'svelte-feather-icons';

	/**
	 * @type {"lambda" | undefined}
	 */
	export let type = undefined;

	import { depth } from './depth.js';
	import { get } from 'svelte/store';

	/**
	 * @type {boolean | undefined}
	 */
	export let active = undefined;
	/**
	 * @type {string}
	 */
	export let name;
	/**
	 * @type {number}
	 */
	export let depthTest = 0;

	
	/**
	 * @type {string | undefined}
	 */
	 export let href = undefined;
</script>

<li class={clsx(styles.file, { [styles.active]: active })}>
	<!-- svelte-ignore a11y-missing-attribute -->
	<a href={href}>
		{#each Array(depthTest) as _, i}
			<span key={i} data-tree-indent="" />
		{/each}
		<span class={styles.icon}>
			{#if type == 'lambda'}
				<BoxIcon size="22" />
			{:else}
				<svg
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
					><path d="M13 2H6a2 2 0 00-2 2v16a2 2 0 002 2h12a2 2 0 002-2V9z" /><path
						d="M13 2v7h7"
					/></svg
				>
			{/if}
		</span>
		<span class={styles.name} {...$$restProps}>{name}</span>
	</a>
</li>
