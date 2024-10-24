<script lang="ts">
	import { Badge } from '$lib/components/ui/badge/index.js';
	import shadcnSvelteLogoSvg from '$assets/shadcn-svelte-logo.svg';
	import inputSelectorUsageRaw from './input-selector-usage.svelte?raw';
	import InputSelectorUsage from './input-selector-usage.svelte';
	import componentRawCode from '$lib/components/customize/InputSelector.svelte?raw';
	import TabPreviewCode from '$lib/components/common/TabPreviewCode.svelte';
	import HighlightCode from '$lib/components/common/HighlightCode.svelte';
	import StepBlock from '$lib/components/customize/StepBlock.svelte';
	import bash from 'svelte-highlight/languages/bash';
	import { Highlight } from 'svelte-highlight';
	import { ExternalLink } from 'lucide-svelte';

	const references = [
		{ label: 'shadcn-svelte Input', url: 'https://www.shadcn-svelte.com/docs/components/input' },
		{ label: 'shadcn-svelte Label', url: 'https://www.shadcn-svelte.com/docs/components/label' }
	];
</script>

<div class="mb-20">
	<h1 class="mb-5 text-4xl">Input Selector</h1>
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

	<h3 class="mt-10 text-2xl font-bold">Installation</h3>
	<div class="my-3">
		<StepBlock step={1}>
			<div slot="label">Install necessary package if you haven't</div>
			<div slot="content">
				<div class="text-lg">
					This component using Combobox Input from Bits-UI.
					<a
						href="https://www.bits-ui.com/docs/getting-started"
						class="flex items-center gap-1 text-[#EA4F27] hover:underline"
					>
						Install it
						<ExternalLink size={18} color="#EA4F27" />
					</a>
				</div>
				<div class="my-2 text-lg">Then install necessary components from shadcn-svelte</div>
				<Highlight language={bash} code="npx shadcn-svelte@latest add input label" />
			</div>
		</StepBlock>
		<StepBlock step={2}>
			<div slot="label">Copy this code</div>
			<div slot="content">
				<HighlightCode rawCode={componentRawCode} />
			</div>
		</StepBlock>
		<StepBlock step={3}>
			<div slot="label">Adjust the import to match your project</div>
		</StepBlock>
	</div>
</div>
