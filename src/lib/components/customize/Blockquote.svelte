<script lang="ts">
	import { cn } from '$lib/utils.js';

	export let contentClass: string = '';
	export let authorClass: string = '';
</script>

<div
	class={cn(
		"relative rounded-lg border-l-8 border-l-gray-700 bg-gray-100 py-5 pl-16 pr-5 font-sans text-lg italic leading-relaxed text-gray-500 before:absolute before:left-3 before:top-3 before:font-serif before:text-6xl before:text-gray-700 before:content-['“']",
		contentClass
	)}
>
	<slot name="content" />
	<div class={cn('mt-5 pr-4 text-right font-bold not-italic text-gray-700', authorClass)}>
		<slot name="author" />
	</div>
</div>
