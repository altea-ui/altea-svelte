<script>
	import '$lib/styles/globals.css';
	import { Button, Card } from '$lib/index.js';
	import { DownloadIcon, ArrowDownIcon } from 'svelte-feather-icons'
	function handleClick() {
		console.log('Button Clicked');
	}
</script>

<div style="margin: 50px;">
	<h1>Welcome Altea</h1>
	<p>A Work in progress Svelte based ui library.</p>
	<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation.</p>
	<br />
	<h2>Button</h2>
	<Button
		kind="primary"
		shape="default"
		variant="shadow"
		size="large"
		on:click={handleClick}>Button</Button
	>
	<br/>
	<Button
		kind="primary"
		shape="default"
		size="large"
		prefix={ArrowDownIcon}
		on:click={handleClick}>Button</Button
	>
	<br/>
	<Button
		kind="secondary"
		variant=""
		size="large"
		suffix={DownloadIcon}
		on:click={handleClick}>Download</Button
		>
	<br/>
	<Button
		kind="violet"
		variant=""
		size="large"
		on:click={handleClick}>Large</Button
	>
	<br/>
	<Button
		kind="success"
		variant=""
		on:click={handleClick}>Default</Button
	>
	<br/>
	<Button
		kind="alert"
		size="small"
		variant=""
		on:click={handleClick}>small</Button
	>
	<p><strong>TODO</strong>: Add spinner to <a href="#button">Button</a></p>
	<h2>Card</h2>
	<Card>Hello</Card>
	<br />
	<Card accent hoverable>Hoverable and Accent</Card>
	<br />
	<Card shadow>Shadow</Card>
	<p><strong>TODO</strong>: Add colors, footers, content frame and more.</p>
</div>
