<script lang="ts">
	import { page } from '$app/stores';
	import { cn } from '$lib/utils.js';
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
			<a
				href="/docs"
				class={cn(
					'indent-5 hover:text-[#EA4F27] hover:underline',
					$page.url.pathname === '/docs' ? 'text-[#EA4F27]' : ''
				)}
			>
				Introduction
			</a>
		</div>
		<h1 class="text-lg font-bold">Components</h1>
		<div class="flex flex-col">
			{#each components as component}
				<a
					href={component.route}
					class={cn(
						'indent-5 hover:text-[#EA4F27] hover:underline',
						$page.url.pathname.includes(component.route) ? 'text-[#EA4F27]' : ''
					)}
				>
					{component.label}
				</a>
			{/each}
		</div>
	</div>
	<div class="col-span-5">
		<slot />
	</div>
</div>
