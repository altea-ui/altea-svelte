<script>
	import '$lib/styles/globals.css';
	import Button from '$lib/components/Button/Button.svelte';

	function handleClick() {
		alert('Button Clicked');
	}
</script>

<div style="margin: 50px;">
	<h1>Welcome Altea</h1>
	<p>A Work in progress Svelte based ui library.</p>
	<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation.</p>
	<br />
	<Button
		style="width: 200px;"
		kind="primary"
		shape="default"
		variant="shadow"
		size="large"
		on:click={handleClick}>Button</Button
	>
	<br/>
	<Button
		style="width: 200px;"
		kind="secondary"
		variant=""
		size="large"
		on:click={handleClick}>Button</Button
		>
	<br/>
	<Button
		style="width: 200px;"
		kind="violet"
		variant=""
		size="large"
		on:click={handleClick}>Button</Button
	>
	<p><strong>TODO</strong>: Add spinner to <a href="#button">Button</a></p>
</div>
