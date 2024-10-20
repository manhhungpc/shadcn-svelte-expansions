<script lang="ts">
	import HighlightCode from '$lib/components/common/HighlightCode.svelte';
	import * as Tabs from '$lib/components/ui/tabs/index.js';

	export let rawCode: string;
</script>

<Tabs.Root value="preview" class="my-10 w-full">
	<Tabs.List class="grid w-1/4 grid-cols-2">
		<Tabs.Trigger value="preview">Preview</Tabs.Trigger>
		<Tabs.Trigger value="usage">Usage</Tabs.Trigger>
	</Tabs.List>
	<Tabs.Content value="preview">
		<slot />
	</Tabs.Content>
	<Tabs.Content value="usage">
		<HighlightCode {rawCode} />
	</Tabs.Content>
</Tabs.Root>
