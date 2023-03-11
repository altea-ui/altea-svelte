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
	 * @type {"default" | "shadow" | "ghost" | "unstyled"}
	 */
	export let variant = 'default';

	/**
	 * Specify the shape of button
	 * @type { "default" | "square" | "circle"}
	 */
	export let shape = 'default';

	/**
	 * Specify the alignment of button
	 * @type { "start" | "grow"}
	 */
	export let align = 'grow';

	export let isDisabled = false;

	let svgOnly = false;

	let isFocused = false;
	let isPressed = false;
	let isHovered = false;
	/**
	 * @type {null}
	 */
	let suffix = null;

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
	<span
		class={clsx(styles.content, {
			[styles.grow]: align === 'grow',
			[styles.start]: align === 'start',
			[styles.flex]: svgOnly
		})}
	>
		<slot />
	</span>
</button>
