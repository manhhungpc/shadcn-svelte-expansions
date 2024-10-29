<script lang="ts">
	import InputSelector from '$lib/components/customize/InputSelector.svelte';

	const OPTIONS = [
		{ label: 'nextjs', value: 'nextjs' },
		{ label: 'React', value: 'react' },
		{ label: 'Remix', value: 'remix' },
		{ label: 'Vite', value: 'vite' },
		{ label: 'Nuxt', value: 'nuxt' },
		{ label: 'Vue', value: 'vue' },
		{ label: 'Svelte', value: 'svelte' },
		{ label: 'Angular', value: 'angular' },
		{ label: 'Ember', value: 'ember' },
		{ label: 'Gatsby', value: 'gatsby' },
		{ label: 'Astro', value: 'astro' },
		{ label: 'Bitui', value: 'bitui' },
		{ label: 'Shadcn', value: 'shadcn' },
		{ label: 'Solid', value: 'solid' },
		{ label: 'Deno', value: 'deno' },
		{ label: 'Bun', value: 'bun' }
	];

	let selected = [
		{ label: 'React', value: 'react' },
		{ label: 'Vite', value: 'vite' },
		{ label: 'Svelte', value: 'svelte' }
	];
</script>

<div class="w-2/5">
	<InputSelector
		bind:values={selected}
		id="disabled"
		options={OPTIONS}
		placeholder="Select favourite JS framework..."
		creatable
		disabled
	/>
</div>
