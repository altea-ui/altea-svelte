<script>
	import '$lib/styles/globals.css';
	import Button from '$lib/components/Button/Button.svelte';

	function handleClick() {
		console.log('Button Clicked');
	}
</script>

<h1>Welcome to your library project</h1>
<p>Create your package using @sveltejs/package and preview/showcase your work with SvelteKit</p>
<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p>
<br/>
<Button style="margin: 20px;" kind="primary" variant="ghost" size="large" on:click={handleClick}>Hallo</Button>
