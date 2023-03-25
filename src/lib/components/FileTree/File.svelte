<script>
	import styles from './filetree.module.css';
	import clsx from 'clsx';
    import { BoxIcon, FileIcon } from 'svelte-feather-icons';

	/**
	 * @type {"lambda" | undefined}
	 */
	export let type = undefined;

	/**
	 * @type {any}
	 */
	let depth;

	/**
	 * @type {boolean | undefined}
	 */
	export let active = undefined;
    /**
	 * @type {string}
	 */
     export let name;
</script>

<li class={clsx(styles.file, { [styles.active]: active })}>
	<!-- svelte-ignore a11y-missing-attribute -->
	<a {...$$restProps}>
		{#each Array(depth) as _, i}
			<span key={i} data-tree-indent="" />
		{/each}
        <span class={styles.icon}>
            {#if type == "lambda"}
            <BoxIcon size="22" />
            {:else}
              <FileIcon size="22" />
            {/if}
          </span>
          <span class={styles.name}>{name}</span>
	</a>
</li>

<!-- 
<li className={clsx(styles.file, { [styles.active]: active })}>
    <a style={style}>
      {Array.from(Array(depth)).map((_e, i) => {
        return <span key={i} data-tree-indent=""></span>;
      })}
      <span className={styles.icon}>
        {type === "lambda" ? (
          <LambdaIcon size={22} />
        ) : (
          <FileIcon size={22} />
        )}
      </span>
      <span className={styles.name}>{name}</span>
    </a>
  </li> -->
