<script lang="ts">
	import { cn } from '$lib/utils.js';

	export let files: FileList | undefined = undefined;

	let isDragFile = false;

	function onDragFile(event: DragEvent) {
		if (event.dataTransfer?.types) {
			for (var i = 0; i < event.dataTransfer.types.length; i++) {
				if (event.dataTransfer.types[i] == 'Files') {
					isDragFile = true;
				}
			}
		}
	}

	function onDragEnd() {
		isDragFile = false;
	}
</script>

<div class="relative h-32 w-1/2">
	<!-- Input: File (hidden) -->
	<input
		type="file"
		bind:files
		class="absolute left-0 top-0 z-10 h-full w-full cursor-pointer opacity-0 file:border-0 file:bg-transparent file:text-sm file:font-medium disabled:!opacity-0"
		on:change
		on:dragenter
		on:click
		on:keydown
		on:keyup
		on:keypress
		on:focus
		on:focusin
		on:focusout
		on:dragover={(e) => onDragFile(e)}
		on:dragleave={onDragEnd}
		on:drop={onDragEnd}
	/>
	<!-- Dropzone -->
	<div
		class={cn(
			'flex h-full w-full flex-col items-center justify-center rounded-md border-2 border-dashed bg-primary-foreground text-center',
			{ 'bg-border': isDragFile }
		)}
	>
		{#if $$slots['title']}
			<div class="mb-3 text-xl">
				<slot name="title" />
			</div>
		{/if}
		<div>
			{#if files}
				{files[0].name}
			{:else}
				<slot name="content"><strong>Upload a file</strong> or drag and drop</slot>
			{/if}
		</div>
		{#if $$slots['metadata']}
			<div class="mt-1 text-xs">
				<slot name="metadata" />
			</div>
		{/if}
	</div>
</div>
