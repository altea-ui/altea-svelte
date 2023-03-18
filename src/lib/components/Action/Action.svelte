<script>
	import clsx from 'clsx';
	import Button from '../Button/Button.svelte';
	import styles from './Action.module.css';
	export let header = "";
	export let accent = false;
	export let hoverable = false;
	export let shadow = false;
</script>

<div
	class={clsx([
		styles.card,
		{ [styles.accent]: accent },
		{ [styles.hoverable]: hoverable },
		{ [styles.shadow]: shadow },
		styles.gridcontainer
	])}
>
	<div class={clsx([styles.griditem, styles.content])} style="display: flex; flex-direction: column; align-items: center; justify-content: center;">
        <h2 style="font-weight: bold; margin:-4px; font-size: 20px; color: var(--geist-foreground);">{header}</h2>
	</div>
	<div class={clsx([styles.griditem])}>
		<Button style="height: 100% !important; border-radius: 0 var(--geist-radius) var(--geist-radius) 0;" kind="success" shape="square"><slot/></Button>
	</div>
</div>
