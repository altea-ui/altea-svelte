<script>
	import '$lib/styles/globals.css';
	import "inter-ui/inter.css"; // for inter font
	import { Button, Card, Action, FileTree, Folder, File } from '$lib/index.js';
	import { DownloadIcon, ArrowDownIcon } from 'svelte-feather-icons'

	function handleClick() {
		console.log('Button Clicked');
	}
</script>

<div style="margin: 50px;">
	<h1>Welcome Altea</h1>
	<p>A Work in progress Svelte based ui library.</p>
	<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation.</p>
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
	<h2>Action</h2>
	<Action header="The Action component" hoverable>Get Started</Action>
	<br/>
	<Action header="Header Text" shadow>Shadow Enabled</Action>
	<br/>
	<Action header="Accented Header Text" accent>Accented</Action>
	<h2>FileTree</h2>
	<FileTree>
		<Folder name="folder 1" depthTest={0}>
			<File name="file 1" depthTest={1}/>
		</Folder>
		<File name="file 2" depthTest={0}/>
		<File name="file 3" depthTest={0}/>
		<Folder name="folder 2" depthTest={0}>
			<Folder name="folder 4" depthTest={1}>
				<File name="file 5" depthTest={2}/>
			</Folder>
			<File name="file 4" depthTest={1}/>
		</Folder>
		<File name="file 6" depthTest={0}/>
	</FileTree>
</div>


<!-- <style>
	.altea-content {
		padding: 2rem;
		will-change: margin-left;
	}
</style> -->
