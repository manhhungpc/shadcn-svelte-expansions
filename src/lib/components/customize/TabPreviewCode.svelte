<script lang="ts">
	import * as Tabs from '$lib/components/ui/tabs/index.js';
	import { HighlightSvelte } from 'svelte-highlight';
	import atomOneDark from 'svelte-highlight/styles/atom-one-dark';

	export let rawCode: string;
</script>

<svelte:head>
	{@html atomOneDark}
</svelte:head>

<Tabs.Root value="preview" class="my-10 w-full">
	<Tabs.List class="grid w-1/4 grid-cols-2">
		<Tabs.Trigger value="preview">Preview</Tabs.Trigger>
		<Tabs.Trigger value="usage">Usage</Tabs.Trigger>
	</Tabs.List>
	<Tabs.Content value="preview">
		<slot />
	</Tabs.Content>
	<Tabs.Content value="usage">
		<HighlightSvelte code={rawCode} />
	</Tabs.Content>
</Tabs.Root>
