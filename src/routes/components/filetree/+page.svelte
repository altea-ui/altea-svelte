<script>
	import { FileTree, Folder, File } from '$lib';
</script>

<h2>FileTree</h2>
<FileTree>
	<Folder name="folder 1" depthTest={0}>
		<File name="file 1" depthTest={1} />
	</Folder>
	<File name="file 2" depthTest={0} />
	<File name="file 3" depthTest={0} />
	<Folder name="folder 2" depthTest={0}>
		<Folder name="folder 4" depthTest={1}>
			<File name="file 5" depthTest={2} />
		</Folder>
		<File name="file 4" depthTest={1} />
	</Folder>
	<File name="file 6" depthTest={0} />
</FileTree>
