<script lang="ts">
	const components = [
		{ label: 'Blockquote', route: '/docs/blockquote' },
		{ label: 'Input Selector', route: '/docs/input-selector' },
		{ label: 'File Drop', route: '/docs/file-drop' },
		{ label: 'Anchor Header', route: '/docs/anchor-header' },
		{ label: 'Floating Label', route: '/docs/floating-label' }
	];
</script>

<div class="grid min-h-80 grid-cols-6 gap-5">
	<div>
		<h1 class="text-lg font-bold">Getting started</h1>
		<div class="flex flex-col">
			<a href="/docs" class="indent-5 hover:bg-slate-300 hover:dark:bg-slate-700">Introduction</a>
		</div>
		<h1 class="text-lg font-bold">Components</h1>
		<div class="flex flex-col">
			{#each components as component}
				<a href={component.route} class="indent-5 hover:bg-slate-300 hover:dark:bg-slate-700">
					{component.label}
				</a>
			{/each}
		</div>
	</div>
	<div class="col-span-5">
		<slot />
	</div>
</div>
