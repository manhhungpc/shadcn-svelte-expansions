<script lang="ts">
	export let files: FileList | undefined = undefined;

	/** Provide arbitrary styles for lead slot container. */
	export let slotLead: string = 'mb-4';
	/** Provide arbitrary styles for message slot container. */
	export let slotMessage: string = '';
	/** Provide arbitrary styles for meta text slot container. */
	export let slotMeta: string = 'opacity-75';
</script>

<div class="relative h-32 w-1/2">
	<!-- Input: File (hidden) -->
	<input
		type="file"
		bind:files
		class="absolute left-0 top-0 z-10 h-full w-full cursor-pointer opacity-0 file:border-0 file:bg-transparent file:text-sm file:font-medium disabled:!opacity-0"
		on:change
		on:dragenter
		on:dragover
		on:dragleave
		on:drop
		on:click
		on:keydown
		on:keyup
		on:keypress
		on:focus
		on:focusin
		on:focusout
	/>
	<!-- Dropzone -->
	<div
		class="flex h-full w-full items-center justify-center rounded-md border-2 border-dashed bg-primary-foreground text-center hover:bg-red-300"
	>
		<div class="">
			<!-- Lead -->
			{#if $$slots.lead}
				<div class={slotLead}>
					<slot name="lead" />
				</div>{/if}
			<!-- Message -->
			<div class="dropzone-message {slotMessage}">
				{#if files}
					{files[0].name}
				{:else}
					<slot name="message"><strong>Upload a file</strong> or drag and drop</slot>
				{/if}
			</div>
			<!-- Meta Text -->
			{#if $$slots.meta}
				<small class="dropzone-meta {slotMeta}">
					<slot name="meta" />
				</small>
			{/if}
		</div>
	</div>
</div>
