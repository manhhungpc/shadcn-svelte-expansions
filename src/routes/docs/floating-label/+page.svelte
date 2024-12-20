<script lang="ts">
	import HighlightCode from '$lib/components/common/HighlightCode.svelte';
	import TabPreviewCode from '$lib/components/common/TabPreviewCode.svelte';
	import StepBlock from '$lib/components/customize/StepBlock.svelte';
	import FloatingLabelUsage from './floating-label-usage.svelte';
	import floatingLabelRawCode from '$lib/components/customize/FloatingLabelInput.svelte?raw';
	import floatingLabelUsageRaw from './floating-label-usage.svelte?raw';
	import { Badge } from '$lib/components/ui/badge/index.js';
	import { Highlight } from 'svelte-highlight';
	import bash from 'svelte-highlight/languages/bash';
	import shadcnSvelteLogoSvg from '$assets/shadcn-svelte-logo.svg';
	import PropsDisplay from '$lib/components/common/PropsDisplay.svelte';

	const references = [
		{ label: 'shadcn-svelte Input', url: 'https://www.shadcn-svelte.com/docs/components/input' },
		{ label: 'shadcn-svelte Label', url: 'https://www.shadcn-svelte.com/docs/components/label' }
	];

	const componentProps = [
		{
			name: 'id',
			type: 'string',
			default: '-',
			description: 'The unique identifier for the input element.'
		},
		{
			name: 'type',
			type: 'InputTypes',
			default: "'text'",
			description: 'Defines the type of the input (e.g., text, password, etc.).'
		},
		{
			name: 'label',
			type: 'string',
			default: "'Floating label'",
			description: 'The label that will be displayed for the input field.'
		},
		{
			name: 'inputClass',
			type: 'string',
			default: "'w-72'",
			description: 'Additional classes to style the input element.'
		},
		{
			name: 'labelClass',
			type: 'string',
			default: '-',
			description: 'Additional classes to style the label element.'
		},
		{
			name: 'bind:value',
			type: 'string',
			default: '-',
			description: 'The value bound to the input element.'
		}
	];
</script>

<div class="mb-20">
	<h1 class="mb-5 text-4xl">Floating Label</h1>
	<h3 class="text-2xl">
		A label tag which floats just above the input field when it is being focused or already has
		content inside.
	</h3>

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

	<TabPreviewCode rawCode={floatingLabelUsageRaw}>
		<FloatingLabelUsage />
	</TabPreviewCode>

	<h3 class="mt-10 text-2xl font-bold">Installation</h3>
	<div class="my-3">
		<StepBlock step={1}>
			<div slot="label">Install necessary package if you haven't</div>
			<div slot="content">
				<Highlight language={bash} code="npx shadcn-svelte@latest add input label" />
			</div>
		</StepBlock>
		<StepBlock step={2}>
			<div slot="label">Copy this code</div>
			<div slot="content">
				<HighlightCode rawCode={floatingLabelRawCode} />
			</div>
		</StepBlock>
		<StepBlock step={3}>
			<div slot="label">Adjust the import to match your project</div>
		</StepBlock>
	</div>

	<h3 class="mb-3 mt-10 text-2xl font-bold">Props</h3>
	<PropsDisplay data={componentProps} />
</div>
