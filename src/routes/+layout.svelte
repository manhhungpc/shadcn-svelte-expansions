<script lang="ts">
	import '../app.css';
	import { ModeWatcher, toggleMode } from 'mode-watcher';
	import { Button } from '$lib/components/ui/button/index.js';
</script>

<ModeWatcher />
<div class="mx-0 mt-4 flex justify-between border-b border-b-stone-500 px-6 py-1">
	<a href="/">LOGO</a>
	<div class="">
		<a href="/docs" class="mr-4 bg-stone-300 px-3 py-1 dark:bg-stone-600">Docs</a>

		<Button on:click={toggleMode} variant="outline" size="icon" class="w-max px-1">
			<p class="block dark:hidden">Light mode</p>
			<p class="hidden dark:block">Dark mode</p>
			<span class="sr-only">Toggle theme</span>
		</Button>
	</div>
</div>
<div class="mx-20 mt-3">
	<slot />
</div>

<style>
	:global(::-webkit-scrollbar) {
		width: 8px;
		background-color: #1f1f1f;
	}

	:global(::-webkit-scrollbar-thumb) {
		background-color: #444;
		border-radius: 4px;
	}
</style>
