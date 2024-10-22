<script lang="ts">
	import InputSelector from '$lib/components/customize/InputSelector.svelte';

	const OPTIONS = [
		{ label: 'nextjs', value: 'nextjs' },
		{ label: 'React', value: 'react', disable: true },
		{ label: 'Remix', value: 'remix' },
		{ label: 'Vite', value: 'vite' },
		{ label: 'Nuxt', value: 'nuxt' },
		{ label: 'Vue', value: 'vue' },
		{ label: 'Svelte', value: 'svelte' },
		{ label: 'Angular', value: 'angular' },
		{ label: 'Ember', value: 'ember', disable: true },
		{ label: 'Gatsby', value: 'gatsby', disable: true },
		{ label: 'Astro', value: 'astro' },
		{ label: 'Bitui', value: 'bitui' },
		{ label: 'Shadcn', value: 'shadcn' }
	];
</script>

<div class="w-1/3">
	<InputSelector
		options={OPTIONS}
		placeholder="Type something that does not exist in dropdowns..."
		creatable
	/>
</div>
