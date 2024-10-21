<script lang="ts">
	export let data: PropDisplay[];
</script>

<div class="w-full">
	<div class="grid grid-cols-12 pb-2 font-bold text-primary/60">
		<span class="col-span-3">Property</span>
		<span class="col-span-2">Type</span>
		<span class="col-span-2">Default</span>
		<span class="col-span-5">Description</span>
	</div>
	{#each data as prop}
		<div class="grid grid-cols-12 border-t border-t-stone-200 py-5 dark:border-t-stone-800">
			<span
				class="col-span-3 h-min w-min rounded-md bg-muted px-2 py-1 font-jetbrain-mono text-sm font-bold"
			>
				{prop.name}
			</span>
			<span class="col-span-2">{prop.type}</span>
			<span class="col-span-2">{prop.default}</span>
			<span class="col-span-5">{prop.description}</span>
		</div>
	{/each}
</div>
