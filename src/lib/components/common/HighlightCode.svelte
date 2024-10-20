<script lang="ts">
	import * as Tabs from '$lib/components/ui/tabs/index.js';
	import { HighlightSvelte } from 'svelte-highlight';
	import atomOneDark from 'svelte-highlight/styles/atom-one-dark';

	export let rawCode: string;
</script>

<svelte:head>
	{@html atomOneDark}
</svelte:head>

<div class="max-h-[80vh] overflow-auto">
	<HighlightSvelte code={rawCode} />
</div>
