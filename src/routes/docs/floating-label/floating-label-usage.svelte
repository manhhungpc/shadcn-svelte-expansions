<script lang="ts">
	import FloatingLabelInput from '$lib/components/customize/FloatingLabelInput.svelte';

	let value = '';
</script>

<div class="flex flex-col gap-2">
	<FloatingLabelInput id="demo" label="Fill your name" bind:value />
	<p>Input value: "{value}"</p>
</div>
