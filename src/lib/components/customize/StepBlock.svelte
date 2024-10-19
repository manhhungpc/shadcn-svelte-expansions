<script lang="ts">
	import { cn } from '$lib/utils.js';

	export let step: number;
	export let labelClass: string = '';
</script>

<div>
	<div class="flex flex-row items-center gap-3">
		<p class="flex h-6 w-6 items-center justify-center rounded-full bg-stone-200 dark:bg-stone-800">
			{step}
		</p>
		<p class={cn('text-xl font-bold', labelClass)}>
			<slot name="label" />
		</p>
	</div>
	<div class="my-1 ml-3 border-l-2 border-stone-200 dark:border-stone-800">
		{#if $$slots.content}
			<div class="ml-6 py-4">
				<slot name="content" />
			</div>
		{/if}
	</div>
</div>
