<script>
	import '$lib/styles/globals.css';
	import Button from '$lib/components/Button/Button.svelte';

	function handleClick() {
		console.log('Button Clicked');
	}
</script>

<div style="margin: 50px;">
	<h1>Welcome Altea</h1>
	<p>A Work in progress Svelte based ui.</p>
	<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p>
	<br />
	<Button
		style="width: 200px;"
		kind="secondary"
		variant=""
		size="large"
		on:click={handleClick}>Upload</Button
	>
	<br/>
	<Button
		style="width: 200px;"
		kind="primary"
		shape="default"
		variant="shadow"
		size="large"
		on:click={handleClick}>Upload</Button
	>
	<br/>
	<Button
		style="width: 200px;"
		kind="violet"
		variant=""
		size="large"
		on:click={handleClick}>Upload</Button
	>
</div>
