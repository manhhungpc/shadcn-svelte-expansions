<script lang="ts">
	import { Input } from '$lib/components/ui/input/index.js';
	import { Label } from '$lib/components/ui/label/index.js';

	export let type: InputTypes = 'text';
	export let id: string;
	export let label: string = 'Floating label';
</script>

<div class="group relative z-0 mb-6 w-full">
	<Input
		placeholder=""
		class="peer block h-11 w-full border-gray-300 bg-transparent text-sm text-gray-900 !ring-transparent focus:outline-none focus:ring-0"
		{type}
		{id}
	/>
	<Label
		for={id}
		class="absolute top-3 z-10 ml-3 origin-[0] -translate-y-5 scale-75 transform bg-white px-1 text-sm text-gray-500 duration-300 hover:cursor-text peer-placeholder-shown:translate-y-0 peer-placeholder-shown:scale-100 peer-focus:-translate-y-5 peer-focus:scale-75"
	>
		{label}
	</Label>
</div>
