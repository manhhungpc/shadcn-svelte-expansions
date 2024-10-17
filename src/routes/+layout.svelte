<script lang="ts">
	import '../app.css';
	import { ModeWatcher, toggleMode } from 'mode-watcher';
	import { Button } from '$lib/components/ui/button/index.js';
</script>

<ModeWatcher />
<div class="mx-6 mt-4 flex justify-between py-1">
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
<div class="mx-6">
	<slot />
</div>
