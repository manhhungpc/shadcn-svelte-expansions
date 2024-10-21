<script lang="ts">
	import { Input } from '$lib/components/ui/input/index.js';
	import { Label } from '$lib/components/ui/label/index.js';
	import { cn } from '$lib/utils.js';

	export let id: string;
	export let type: InputTypes = 'text';
	export let label: string = 'Floating label';
	export let inputClass: string = 'w-72';
	export let labelClass: string = '';

	export let value: string = '';
</script>

<div class="group relative z-0 w-max">
	<Input
		placeholder=""
		class={cn(
			'peer block h-12 w-full border-gray-300 bg-transparent text-sm text-gray-900 !ring-transparent focus:outline-none focus:ring-0 dark:text-gray-200',
			inputClass
		)}
		{type}
		{id}
		bind:value
	/>
	<Label
		for={id}
		class={cn(
			'absolute top-3 z-10 ml-3 origin-[0] -translate-y-6 scale-75 transform bg-background px-2 text-base text-gray-500 duration-300 hover:cursor-text peer-placeholder-shown:translate-y-0 peer-placeholder-shown:scale-100 peer-focus:-translate-y-6 peer-focus:scale-75 dark:text-gray-200',
			labelClass
		)}
	>
		{label}
	</Label>
</div>
