<script lang="ts">
	import HighlightCode from '$lib/components/common/HighlightCode.svelte';
	import * as Tabs from '$lib/components/ui/tabs/index.js';
	import { cn } from '$lib/utils.js';
	import type { HTMLInputAttributes } from 'svelte/elements';

	export let rawCode: string;
	export { className as class };

	let className: HTMLInputAttributes['class'] = '';
</script>

<Tabs.Root value="preview" class={cn('my-10 w-full', className)}>
	<Tabs.List class="grid w-1/4 grid-cols-2">
		<Tabs.Trigger value="preview">Preview</Tabs.Trigger>
		<Tabs.Trigger value="usage">Usage</Tabs.Trigger>
	</Tabs.List>
	<Tabs.Content value="preview">
		<div class="flex items-center justify-center rounded-lg border-2 border-primary/40 py-16">
			<slot />
		</div>
	</Tabs.Content>
	<Tabs.Content value="usage">
		<HighlightCode {rawCode} />
	</Tabs.Content>
</Tabs.Root>
