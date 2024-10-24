<script lang="ts">
	import { Combobox } from 'bits-ui';
	import { Badge } from '$lib/components/ui/badge/index.js';
	import { createEventDispatcher } from 'svelte';
	import { cn } from '$lib/utils.js';
	import { X } from 'lucide-svelte';

	const dispatch = createEventDispatcher();

	interface Option {
		value: string;
		label: string;
		hidden?: boolean;
		disable?: boolean;
		/** fixed option that can't be removed. */
		fixed?: boolean;
		/** Group the options by providing key. */
		[key: string]: string | boolean | undefined;
	}

	export let options: Option[];
	export let values: Option[] = [];
	export let placeholder: string = 'Select options';
	export let disabled: boolean = false;
	export let creatable: boolean = false;

	let displayOptions: Option[] = options;
	let inputValue = '';
	let touchedInput = false,
		open = false;

	function removeSelection(value: string) {
		values = values.filter((selectVal) => selectVal.value != value);
		displayOptions = options.filter(
			(item) => item.value === value || displayOptions.find((option) => option.value === item.value)
		);
	}

	function onClickItem(item: Option) {
		if (item.disable) return;
		values = [...values, item];
		displayOptions = displayOptions.filter((option) => option.value != item.value);
	}

	function handleFocusInput() {
		const comboboxInput = document.querySelector('[data-combobox-input]') as HTMLElement;
		comboboxInput.focus();
		open = true;
	}

	$: filteredOptions =
		inputValue && touchedInput
			? displayOptions.filter((item) => item.value.includes(inputValue.toLowerCase()))
			: displayOptions;
	$: inputWidth = placeholder.length * 8;
</script>

<div class="relative">
	<Combobox.Root
		items={filteredOptions}
		bind:touchedInput
		bind:inputValue
		bind:open
		preventScroll={false}
		{disabled}
		scrollAlignment="center"
		portal={null}
	>
		<!-- svelte-ignore a11y-click-events-have-key-events -->
		<div
			class={cn(
				'relative flex flex-wrap items-center rounded-md border border-input bg-background py-2 text-sm ring-offset-background placeholder:text-muted-foreground focus-within:outline-none focus-within:ring-2 focus-within:ring-ring focus-within:ring-offset-1 hover:cursor-text disabled:cursor-not-allowed disabled:opacity-50',
				{ 'pl-2': values.length > 0 }
			)}
			on:click={handleFocusInput}
			tabindex="0"
			role="button"
		>
			<div class="h-full">
				{#each values as selected}
					<Badge class="mr-1 !h-6">
						{selected.label}
						<button
							class="ml-1 hover:text-red-500"
							on:click={() => removeSelection(selected.value)}
						>
							<X size={16} />
						</button>
					</Badge>
				{/each}
			</div>
			<Combobox.Input
				class={cn(
					'h-6 rounded-md bg-background px-3 py-2 placeholder:truncate focus:outline-none',
					{
						'pl-1': values.length > 0
					}
				)}
				style="width: {inputWidth}px;"
				{placeholder}
				value=""
			/>
		</div>

		<Combobox.Content
			class="!left-0 mb-5 max-h-[40vh] !w-full overflow-auto rounded-xl border bg-background px-1 py-3 shadow-popover outline-none"
			sideOffset={8}
		>
			{#each filteredOptions as option (option.value)}
				<Combobox.Item
					class={cn(
						'flex h-10 w-full select-none items-center py-3 pl-5 pr-1.5 text-sm outline-none transition-all duration-75 data-[highlighted]:bg-muted',
						option.disable ? 'opacity-50' : null
					)}
					value={option.value}
					label={option.label}
					disabled={option.disable}
					on:click={() => onClickItem(option)}
				>
					{option.label}
				</Combobox.Item>
			{:else}
				<slot name="empty">
					<span class="block px-5 py-2 text-sm text-muted-foreground">No results found.</span>
				</slot>
			{/each}
		</Combobox.Content>
		<Combobox.HiddenInput name="favoriteFruit" />
	</Combobox.Root>
</div>
