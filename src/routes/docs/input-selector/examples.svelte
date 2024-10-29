<script lang="ts">
	import TabPreviewCode from '$lib/components/common/TabPreviewCode.svelte';
	import disabledRawCode from './examples/input-selector-disabled.svelte?raw';
	import InputSelectorDisabled from './examples/input-selector-disabled.svelte';
	import disableOptionRawCode from './examples/input-selector-disable-option.svelte?raw';
	import InputSelectorDisableOptions from './examples/input-selector-disable-option.svelte';
</script>

<div>
	<h3 class="mt-2 text-xl font-bold">Disabled</h3>
	<TabPreviewCode rawCode={disabledRawCode} class="mb-5 mt-2">
		<InputSelectorDisabled />
	</TabPreviewCode>

	<h3 class="mt-2 text-xl font-bold">Disabled options</h3>
	<TabPreviewCode rawCode={disableOptionRawCode} class="mb-5 mt-2">
		<InputSelectorDisableOptions />
	</TabPreviewCode>
</div>
