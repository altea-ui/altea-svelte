<script>
	import { FileTree, Folder, File } from '$lib';
	import '$lib/styles/globals.css';
	import 'inter-ui/inter.css'; // for inter font
	import { goto } from '$app/navigation';

	/**
	 * @param {string | URL} route
	 */
	function routeToPage(route) {
		goto(route);
	}
</script>

<div class="sidenav">
	<FileTree style="margin-left: 45px;">
		<File name="home" depthTest={0} href="/" />
		<Folder open="true" name="components" depthTest={0}>
			<File name="button" depthTest={1} href="/components/button" />
			<File name="action" depthTest={1} href="/components/action" />
			<File name="card" depthTest={1} href="/components/card" />
			<File name="filetree" depthTest={1} href="/components/filetree" />
		</Folder>
		<Folder name="extras" depthTest={0}>
			<Folder name="ideas" depthTest={1} />
			<File name="roadmap" depthTest={1} />
		</Folder>
		<File
			name="license"
			depthTest={0}
			href="https://github.com/AlteaDesign/Altea/blob/main/LICENSE"
		/>
		<File name="npm" depthTest={0} type="lambda" href="https://www.npmjs.com/package/altea" />
	</FileTree>
</div>
<div class="altea-content">
	<slot />
</div>

<style>
	.altea-content {
		padding: 2rem;
		will-change: margin-left;
		margin-left: 200px; /* Same as the width of the sidebar */
	}
	.sidenav {
		background: var(--accents-1);
		width: 200px; /* Set the width of the sidebar */
		position: fixed; /* Fixed Sidebar (stay in place on scroll) */
		height: 100%;
		z-index: 1;
		padding-top: 55px;
		border-right: 1px solid #eaeaea; /* 1px solid #333 on dark mode */
	}
</style>
