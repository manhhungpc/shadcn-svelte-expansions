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
</script>

<div class="w-2/5">
	<InputSelector options={OPTIONS} placeholder="Select favourite JS framework..." creatable />
</div>
