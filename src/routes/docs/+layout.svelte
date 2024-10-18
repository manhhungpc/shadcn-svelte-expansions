<script lang="ts">
	const components = [
		{ label: 'Blockquote', route: '/docs/blockquote' },
		{ label: 'Input Selector', route: '/docs/input-selector' },
		{ label: 'File Drop', route: '/docs/file-drop' },
		{ label: 'Andchor Header', route: '/docs/anchor-header' },
		{ label: 'Floating Label', route: '/docs/floating-label' }
	];
</script>

<div class="grid min-h-80 grid-cols-6">
	<div>
		<h1 class="text-lg font-bold">Getting started</h1>
		<ul class="indent-5">
			<li class="hover:bg-slate-300 hover:dark:bg-slate-700">
				<a href="/docs">Introduction</a>
			</li>
		</ul>
		<h1 class="text-lg font-bold">Components</h1>
		<ul class="indent-5">
			{#each components as component}
				<li class="hover:bg-slate-300 hover:dark:bg-slate-700">
					<a href={component.route}>{component.label}</a>
				</li>
			{/each}
		</ul>
	</div>
	<div class="col-span-5">
		<slot />
	</div>
</div>
