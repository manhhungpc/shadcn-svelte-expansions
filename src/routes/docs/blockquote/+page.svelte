<script lang="ts">
	import Usage from './Usage.svelte';
	import usageRawCode from './usage.svelte?raw';
	import TabPreviewCode from '$lib/components/customize/TabPreviewCode.svelte';
	import StepBlock from '$lib/components/customize/StepBlock.svelte';
</script>

<div class="mb-20">
	<h1 class="mb-5 text-4xl font-bold">Blockquote</h1>
	<h3 class="text-2xl">Display a quote or a component that looks like a quote.</h3>
	<TabPreviewCode rawCode={usageRawCode}>
		<Usage />
	</TabPreviewCode>

	<h3 class="mt-10 text-2xl font-bold">Installation</h3>
	<div class="my-3">
		<StepBlock step={1}>
			<div slot="label">Copy this code</div>
			<div slot="content">
				<p>Some content</p>
				<p>Some content</p>
				<p>Some content</p>
				<p>Some content</p>
				<p>Some content</p>
				<p>Some content</p>
			</div>
		</StepBlock>
		<StepBlock step={2}>
			<div slot="label">Adjust the import to match your project</div>
		</StepBlock>
	</div>

	<h3 class="mt-10 text-2xl font-bold">Props</h3>
	<p>Some text here</p>
</div>
