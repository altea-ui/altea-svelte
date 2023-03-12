<script>
	import clsx from 'clsx';
	import styles from './Card.module.css';
</script>

<div class={clsx([styles.card])}>
	<div class={clsx([styles.content])}>
		<slot />
	</div>
</div>
