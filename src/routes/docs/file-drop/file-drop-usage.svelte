<script lang="ts">
	import FileDrop from '$lib/components/customize/FileDrop.svelte';

	let files: FileList;
</script>

<div>
	<FileDrop bind:files />
</div>
