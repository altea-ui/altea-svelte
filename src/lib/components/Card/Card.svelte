<script>
	import clsx from 'clsx';
	import styles from './Card.module.css';

	export let accent = false;
	export let hoverable = false;
	export let shadow = false;
</script>

<div
	{...$$restProps}
	class={clsx([
		styles.card,
		{ [styles.accent]: accent },
		{ [styles.hoverable]: hoverable },
		{ [styles.shadow]: shadow }
	])}
>
	<div class={clsx([styles.content])}>
		<slot />
	</div>
</div>
