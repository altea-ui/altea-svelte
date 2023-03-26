<script>
	import { DownloadIcon, ArrowDownIcon } from 'svelte-feather-icons'
	import { Button } from "$lib";
    function handleClick() {
		console.log('Button Clicked');
	}
</script>
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