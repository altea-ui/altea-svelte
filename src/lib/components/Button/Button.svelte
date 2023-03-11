<script>
  import styles from './Button.module.css';
  import reset from '$lib/styles/reset/reset.module.css';
	
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
	 * @type { "shadow" | "ghost" | "unstyled"}
	 */
	export let variant = 'unstyled';

	/**
	 * Specify the shape of button
	 * @type { "square" | "circle"}
	 */
	export let shape = 'square';

  /**
	 * Specify the alignment of button
	 * @type { "start" | "grow"}
	 */
	export let align = 'start';

	export let isDisabled = false;


  let svgOnly = false;
	let isFocused = false;
	let isPressed = false;
	let isHovered = false;
  /**
	 * @type {null}
	 */
  let suffix = null;
	//  export type ButtonAlign = 'start' | 'grow';
	// export type ButtonShape = 'square' | 'circle';
</script>

<button
	{...$$restProps}
	type="submit"
	data-geist-button=""
	data-focus={isFocused ? '' : null}
	data-active={isPressed ? '' : null}
	data-hover={isHovered ? '' : null}
	
>
	
</button>


<!-- <span
		class={`${styles.content} ${align === 'grow' && styles.grow} ${
			align === 'start' && styles.start
		} ${svgOnly && styles.flex}`}
	>
		<slot />
	</span>

	{#if suffix}
		<span class={styles.suffix}>{suffix}</span>
	{/if} -->