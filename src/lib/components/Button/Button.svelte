<script>
	import styles from './Button.module.css';
	import reset from '$lib/styles/reset/reset.module.css';
	import clsx from 'clsx';

	/**
	 * Specify the kind of button
	 * @type {"primary" | "secondary" | "success" | "error" | "warning" | "alert" | "violet"}
	 */
	export let kind = 'primary';

	/**
	 * Specify the size of button
	 * @type { "large" | "small"}
	 */
	export let size = 'small';

	/**
	 * Specify the variant of button
	 * @type {"" | "shadow" | "ghost" | "unstyled"}
	 */
	export let variant = '';

	/**
	 * Specify the shape of button
	 * @type { "default" | "square" | "circle"}
	 */
	export let shape = 'default';

	/**
	 * Specify the alignment of button
	 * @type { "" | "start" | "grow"}
	 */
	export let align = '';

	/**
	 * Prefix any component (for example icons) to the button
	 * @type {any}
	 */
	export let prefix = null;

	/**
	 * Set the button in a disabled state
	 */
	export let isDisabled = false;

	/**
	 * Suffix any component (for example icons) to the button
	 * @type {any}
	 */
	export let suffix = null;

	let svgOnly = true;

	let isFocused = false;
	let isPressed = false;
	let isHovered = false;

	function setFocus() {
		if (isPressed == false) {
			isFocused = true;
		}
	}

	function leaveClick() {
		isPressed = false;
		isFocused = false;
	}

	// export type ButtonAlign = 'start' | 'grow';
	// export type ButtonShape = 'square' | 'circle';
</script>

<button
	{...$$restProps}
	type="submit"
	on:mouseenter={() => (isHovered = true)}
	on:mouseleave={() => (isHovered = false)}
	on:focus={setFocus}
	on:blur={() => (isFocused = false)}
	on:mousedown={() => (isPressed = true)}
	on:mouseup={leaveClick}
	on:click
	on:mouseover
	on:mouseenter
	on:mouseleave
	on:focus
	data-focus={isFocused ? '' : null}
	data-active={isPressed ? '' : null}
	data-hover={isHovered ? '' : null}
	disabled={isDisabled ? true : false}
	class={clsx([
		reset.reset,
		styles.base,
		{ [styles.button]: variant !== 'unstyled' },
		!variant && styles.invert,
		{
			[styles.ghost]: variant === 'ghost',
			[styles.shadow]: variant === 'shadow'
		},
		{
			[styles.shape]: shape === 'square',
			[styles.circle]: shape === 'circle'
		},
		{
			[styles.secondary]: kind === 'secondary',
			[styles[size]]: !!size,
			[styles.disabled]: isDisabled
		},
		kind === 'success' && ['geist-themed', 'geist-success', 'geist-success-fill'],
		kind === 'error' && ['geist-themed', 'geist-error', 'geist-error-fill'],
		kind === 'warning' && ['geist-themed', 'geist-warning', 'geist-warning-fill'],
		kind === 'alert' && ['geist-themed', 'geist-alert', 'geist-alert-fill'],
		kind === 'violet' && ['geist-themed', 'geist-violet', 'geist-violet-fill']
	])}
>
	{#if prefix}
		<span class={styles.prefix}>
			<svelte:component this={prefix} size="20"/>
		</span>
	{/if}
	<span
		class={clsx(styles.content, {
			[styles.grow]: align === 'grow',
			[styles.start]: align === 'start',
			[styles.flex]: svgOnly
		})}
	>
		<slot />
	</span>
	{#if suffix}
		<span class={styles.suffix}>
			<svelte:component this={suffix} size="20"/>
		</span>
	{/if}
</button>
