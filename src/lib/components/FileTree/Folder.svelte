<script>
	import styles from './filetree.module.css';
	import clsx from 'clsx';
	import { MinusSquareIcon, PlusSquareIcon, FolderIcon } from 'svelte-feather-icons';

	/**
	 * @type {string}
	 */
	export let name;
    /**
	 * @type {any}
	 */
    export let depth = 0;
	export let open = false;
</script>

<li class={clsx(styles.folder, { open: open })}>
	{#each Array(depth) as _, i}
		<span key={i} data-tree-indent="" />
	{/each}
	<!-- svelte-ignore a11y-missing-attribute -->
	<a title={name} on:click|stopPropagation|preventDefault={() => (open = !open)} {...$$restProps}>
		{#if open}
			<MinusSquareIcon size="12" />
		{:else}
			<PlusSquareIcon size="12" />
		{/if}
		<span class={styles.icon}><FolderIcon size="22" /></span>
		<span class={styles.name}>{name}</span>
		{#if open}
			<ul><slot /></ul>
		{/if}
	</a>
</li>