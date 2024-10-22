<script lang="ts">
	import { Badge } from '$lib/components/ui/badge/index.js';
	import shadcnSvelteLogoSvg from '$assets/shadcn-svelte-logo.svg';
	import inputSelectorUsageRaw from './input-selector-usage.svelte?raw';
	import InputSelectorUsage from './input-selector-usage.svelte';
	import TabPreviewCode from '$lib/components/common/TabPreviewCode.svelte';

	const references = [
		{ label: 'shadcn-svelte Input', url: 'https://www.shadcn-svelte.com/docs/components/input' },
		{ label: 'shadcn-svelte Label', url: 'https://www.shadcn-svelte.com/docs/components/label' }
	];
</script>

<div class="mb-20">
	<h1 class="mb-5 text-4xl">Floating Label</h1>
	<h3 class="text-2xl">Allows input of multiple values.</h3>

	<div class="mt-2">
		{#each references as ref}
			<Badge href={ref.url} class="mr-2">
				<img
					src={shadcnSvelteLogoSvg}
					alt="Shadcn svelte logo"
					height="16"
					width="16"
					class="mr-1"
				/>
				{ref.label}
			</Badge>
		{/each}
	</div>

	<TabPreviewCode rawCode={inputSelectorUsageRaw}>
		<InputSelectorUsage />
	</TabPreviewCode>
</div>
