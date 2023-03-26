<script>
	import { FileTree, Folder, File } from '$lib';
	import '$lib/styles/globals.css';
	import 'inter-ui/inter.css'; // for inter font

    import { goto } from '$app/navigation';
</script>

<div class="sidenav">
	<FileTree style="margin-left: 45px;">
		<File name="Home" depthTest={0} on:click={() => alert('23')}/>
		<Folder open="true" name="components" depthTest={0}>
			<File name="file 1" depthTest={1} />
		</Folder>
		<Folder name="folder 2" depthTest={0}>
			<Folder name="folder 4" depthTest={1}>
				<File name="file 5" depthTest={2} />
			</Folder>
			<File name="file 4" depthTest={1} />
		</Folder>
		<File name="file 6" depthTest={0} />
	</FileTree>
</div>
<div class="altea-content">
	<slot />
</div>

<style>
	.altea-content {
		padding: 2rem;
		will-change: margin-left;
		margin-left: 180px; /* Same as the width of the sidebar */
		background: var(--accents-2);
	}
	.sidenav {
		width: 180px; /* Set the width of the sidebar */
		position: fixed; /* Fixed Sidebar (stay in place on scroll) */
		height: 100%;
		z-index: 1;
		padding-top: 55px;
		border-right: 1px solid #eaeaea; /* 1px solid #333 on dark mode */
	}
</style>
