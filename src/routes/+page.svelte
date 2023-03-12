<script>
	import '$lib/styles/globals.css';
	import { Button, Card } from '$lib/index.js';

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
		kind="primary"
		shape="default"
		variant="shadow"
		size="large"
		on:click={handleClick}>Button</Button
	>
	<br/>
	<Button
		kind="secondary"
		variant=""
		size="large"
		on:click={handleClick}>Button</Button
		>
	<br/>
	<Button
		kind="violet"
		variant=""
		size="large"
		on:click={handleClick}>Button</Button
	>
	<Card></Card>
	<p><strong>TODO</strong>: Add spinner to <a href="#button">Button</a></p>
</div>
