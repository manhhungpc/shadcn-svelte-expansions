<script lang="ts">
	import TabPreviewCode from '$lib/components/common/TabPreviewCode.svelte';
	import FileDrop from '$lib/components/customize/FileDrop.svelte';
	import componentCode from '$lib/components/customize/FileDrop.svelte?raw';
	import usageCode from './file-drop-usage.svelte?raw';
	import StepBlock from '$lib/components/customize/StepBlock.svelte';
	import HighlightCode from '$lib/components/common/HighlightCode.svelte';
	import PropsDisplay from '$lib/components/common/PropsDisplay.svelte';

	const data: PropDisplay[] = [];
</script>

<div class="mb-20">
	<h1 class="mb-5 text-4xl font-bold">File Dropzone</h1>
	<h3 class="text-2xl">Allow upload of files with drag and drop.</h3>
	<TabPreviewCode rawCode={usageCode}>
		<FileDrop />
	</TabPreviewCode>

	<h3 class="mt-10 text-2xl font-bold">Installation</h3>
	<p class="my-3 rounded-md bg-primary-foreground px-5 py-4">
		Set up
		<a href="https://www.shadcn-svelte.com/docs/installation" class="text-[#EA4F27] underline">
			shadcn-svelte
		</a>
		if you haven't
	</p>
	<div class="my-3">
		<StepBlock step={1}>
			<div slot="label">Copy this code</div>
			<div slot="content">
				<HighlightCode rawCode={componentCode} />
			</div>
		</StepBlock>
		<StepBlock step={2}>
			<div slot="label">Adjust the import to match your project</div>
		</StepBlock>
	</div>

	<h3 class="mb-3 mt-10 text-2xl font-bold">Props</h3>
	<PropsDisplay {data} />
</div>
